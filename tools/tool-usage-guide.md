# Hypatia Technologies — eMMА Solicitation Intelligence Tool Usage Guide

**Version:** 1.0 | **Last Updated:** April 15, 2026 | **Maintained by:** Hypatia Technologies BD Intelligence Unit

---

## PURPOSE

This guide documents every tool available to the eMMА Solicitation Intelligence research agent, including when to use each tool, how to use it correctly, and common failure modes to avoid.

For the phase-by-phase tool sequence, see `process/research-process.md` Appendix B.

---

## TOOL INVENTORY

| Tool | Primary Function | Phase Used |
|------|-----------------|------------|
| `navigate` | Open URLs, move between pages | All phases |
| `get_page_text` | Extract full text from loaded pages | 1, 3 |
| `read_page` | Read DOM structure, find interactive elements | 1, 3, 4 |
| `search_web` | Run keyword searches across the internet | 2, 3 |
| `find` | Locate specific elements on a page by description | 3, 4 |
| `computer` | Click, type, scroll, take screenshots | 3, 4 |
| `form_input` | Fill form fields using element refs | 4 |
| `todo_write` | Track tasks, plan phases, mark completion | All phases |
| `tabs_create` | Open new browser tabs | All phases |

---

## TOOL REFERENCE

### navigate

**Purpose:** Load a URL or move forward/back in browser history.

**When to use:**
- Opening the eMMА solicitation portal
- Going directly to a solicitation detail page
- Navigating to BPM, GovTribe, or agency websites
- Moving between pages in a research workflow

**Correct usage:**
```
navigate(url="https://emma.maryland.gov/...", tab_id=TAB_ID)
```

**Rules:**
- Always include the full URL with protocol (https://)
- Use `tab_id` from `tabs_context` if uncertain which tab to use
- For eMMА: navigate directly to solicitation detail URLs when available
- Do not use `navigate` to go to google.com — use `search_web` instead

**Common failures:**
- Navigating to login-protected pages without session — check if portal requires auth
- Using `navigate` instead of `search_web` for discovery queries

---

### get_page_text

**Purpose:** Extract all readable text from the current page in a single call.

**When to use:**
- Reading the full content of an eMMА solicitation listing
- Extracting scope of work, deadline, and requirements text
- Reading agency pages, BPM results, or search results
- Faster than `read_page` for text-heavy pages

**Correct usage:**
```
get_page_text(tab_id=TAB_ID)
```

**Rules:**
- Use this BEFORE `read_page` when the goal is to read content (not interact)
- Always use `get_page_text` as the primary source collection tool in Phase 1
- Check for truncation — very long pages may cut off; scroll and re-run if needed

**Common failures:**
- Using `read_page` when `get_page_text` would be faster
- Not checking if dynamic content has loaded before calling

---

### read_page

**Purpose:** Get the DOM accessibility tree — all elements including interactive ones.

**When to use:**
- Finding buttons, links, form fields, or dropdowns to interact with
- Locating element `ref_id` values needed for `form_input` or `computer`
- When `get_page_text` misses content rendered in interactive components
- Debugging why a page isn't showing expected content

**Correct usage:**
```
read_page(tab_id=TAB_ID, filter="interactive")  # for finding clickable elements
read_page(tab_id=TAB_ID, filter="all")           # for all content
read_page(tab_id=TAB_ID, ref_id="ref_42")        # to read a specific section
```

**Rules:**
- Use `filter="interactive"` to find buttons/links efficiently
- Use `ref_id` to focus on a subsection when output is too large
- Limit depth with `depth=5` for complex pages if output exceeds limits

**Common failures:**
- Not using `ref_id` on large pages causing truncation
- Using `read_page` when `get_page_text` would suffice for plain text

---

### search_web

**Purpose:** Search the internet using keyword queries. Returns results with titles, URLs, and snippets.

**When to use:**
- Phase 2 parallel research (agency background, incumbent, competition)
- Value benchmarking when contract value not stated
- OEM/partner program research
- Verifying deadlines via secondary sources

**Correct usage:**
```
search_web(queries=[
  "Maryland DGS IT contract award 2025",
  "NAICS 541512 Maryland state contract value",
  "incumbent vendor BPM solicitation 123456"
])
```

**Rules:**
- **Maximum 3 queries per call** — never exceed this limit
- Use short keyword phrases, not full sentences or questions
- Include year when recency matters
- Use quotes around exact phrases (solicitation numbers, agency names)
- Never use google.com via `navigate` — always use `search_web`

**Common failures:**
- Sending 4+ queries in one call (will error)
- Writing queries as questions instead of keyword phrases
- Not including year for competitive/incumbent queries

---

### find

**Purpose:** Locate specific elements on a page using natural language description.

**When to use:**
- When an element is NOT visible in the latest screenshot
- Finding a specific button or link when `read_page` output is too large
- Locating form fields described by their label or purpose

**Correct usage:**
```
find(query="submit proposal button", tab_id=TAB_ID)
find(query="solicitation deadline date field", tab_id=TAB_ID)
```

**Rules:**
- Only use `find` when the element is NOT already visible in a screenshot
- Try `read_page` first; use `find` only if `read_page` fails
- Returns up to 20 matching elements with refs and coordinates

**Common failures:**
- Using `find` redundantly when element is already visible in screenshot
- Queries too vague (e.g., "the button") — be specific

---

### computer

**Purpose:** Interact with the browser using mouse clicks, keyboard input, scrolling, and screenshots.

**When to use:**
- Clicking buttons, links, tabs, or navigation elements
- Typing into search boxes or form fields
- Scrolling to load more content
- Taking screenshots to verify page state
- Any interaction not possible via `form_input` or `navigate`

**Correct usage:**
```
computer(actions=[
  {"action": "left_click", "coordinate": [X, Y]},
  {"action": "type", "text": "search term"},
  {"action": "key", "text": "Return"}
], tab_id=TAB_ID)
```

**Rules:**
- Batch related actions into a single call when no wait is needed
- Always combine `left_click` on a field + `type` into one call
- Take a screenshot first if unsure of current page state
- Use `ref` instead of `coordinate` when DOM ref is known (more reliable)
- Always end scroll sequences with `get_page_text` to capture loaded content

**Common failures:**
- Separate tool calls for click + type (should be one call)
- Using incorrect coordinates — verify via screenshot first
- Not waiting for page load after navigation before interacting

---

### form_input

**Purpose:** Set values in form elements using DOM reference IDs.

**When to use:**
- Filling text inputs, dropdowns, checkboxes, or radio buttons
- More reliable than `computer` type for complex form fields
- When `read_page` has returned a `ref_id` for the target input

**Correct usage:**
```
form_input(ref="ref_42", value="search term", tab_id=TAB_ID)
form_input(ref="ref_17", value=True, tab_id=TAB_ID)  # for checkbox
form_input(ref="ref_9", value="Option Name", tab_id=TAB_ID)  # for select
```

**Rules:**
- Get `ref_id` from `read_page` before using `form_input`
- For dropdowns: use the option text or value exactly as it appears
- Always submit the form after filling (via `computer` click on submit button)

**Common failures:**
- Using `form_input` without first getting the ref via `read_page`
- Incorrect value format for select elements

---

### todo_write

**Purpose:** Create and update a structured task list to track research progress.

**When to use:**
- At the start of every research session
- After completing each phase or major task
- When pivoting strategy or adding new tasks
- Before delivering the final report

**Correct usage:**
```
todo_write(todos=[
  {"content": "Phase 1: Source collection", "status": "completed", "active_form": "Collecting sources"},
  {"content": "Phase 2: Parallel research", "status": "in_progress", "active_form": "Running parallel research"},
  {"content": "Phase 3: Deep intelligence", "status": "pending", "active_form": "Gathering deep intelligence"}
])
```

**Rules:**
- Mark tasks `completed` immediately upon finishing — do not batch
- Only one task should be `in_progress` at a time
- Include all 6 phases + quality audit + delivery as separate tasks
- Update todo list after every major tool call sequence

**Common failures:**
- Not marking tasks complete promptly
- Forgetting to initialize the todo list at session start

---

### tabs_create

**Purpose:** Open a new empty browser tab.

**When to use:**
- When parallel research requires multiple pages open simultaneously
- Opening a second tab for comparison or cross-reference

**Correct usage:**
```
tabs_create(url="https://bpm.maryland.gov")
```

**Rules:**
- Track tab IDs returned after creation
- Use `tabs_context` if unsure of current tab IDs
- Close or reuse tabs to avoid accumulation

---

## TOOL SELECTION DECISION TREE

```
Need to READ content from a page?
  └── Page is text-heavy (article, listing, results)?
        YES → get_page_text
        NO (complex UI, tables, dynamic content) → read_page

Need to FIND something on a page?
  └── Element visible in last screenshot?
        YES → computer (use coordinates)
        NO → read_page first; if fails → find

Need to SEARCH the internet?
  → search_web (max 3 queries per call)
  NEVER → navigate to google.com

Need to CLICK or TYPE?
  └── Have ref_id from read_page?
        YES, form field → form_input
        YES, button/link → computer with ref=
        NO → computer with coordinate from screenshot

Need to go to a URL?
  → navigate

Need to TRACK progress?
  → todo_write
```

---

*Hypatia Technologies BD Intelligence Unit — Internal Use Only*
*Tool Usage Guide Version 1.0 — April 15, 2026*
