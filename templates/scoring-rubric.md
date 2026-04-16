# Hypatia Technologies — eMMА Solicitation Intelligence Scoring Rubric

**Version:** 1.0 | **Last Updated:** April 15, 2026 | **Maintained by:** Hypatia Technologies BD Intelligence Unit

---

## PURPOSE

This rubric provides detailed scoring guidance for each of the 8 dimensions used to evaluate eMMА solicitations. Each dimension is scored 1–5. The composite score (out of 40) drives the Bid / No-Bid recommendation.

For the scoring table used in reports, see `templates/report-template.md` Section 7.
For full dimension definitions, see `analysis/scoring-dimensions.md`.

---

## DIMENSION 1: STRATEGIC ALIGNMENT

*Does this solicitation align with Hypatia's core service areas and target agencies?*

| Score | Criteria |
|-------|----------|
| 5 | Perfect match: agency is a named target, NAICS is primary, scope is core service |
| 4 | Strong match: 2 of 3 alignment factors present |
| 3 | Moderate: adjacent service area or secondary NAICS |
| 2 | Weak: tangential scope, outside primary focus but performable |
| 1 | Misaligned: outside capabilities or agency is deprioritized |

**Scoring Notes:**
- Primary NAICS codes: [populate from BD strategy]
- Target agencies: [populate from BD strategy]
- Core service areas: [populate from BD strategy]

---

## DIMENSION 2: TECHNICAL CAPABILITY MATCH

*Can Hypatia credibly deliver the required scope with current staff and tools?*

| Score | Criteria |
|-------|----------|
| 5 | Full capability: all requirements met with existing staff, past performance exists |
| 4 | Strong: 90%+ of requirements met, minor gaps fillable via subcontract |
| 3 | Moderate: 70–89% of requirements met, teaming likely needed |
| 2 | Weak: 50–69% match, significant teaming or hiring required |
| 1 | Unable: <50% match, capability does not exist |

**Scoring Notes:**
- Evaluate against SOW line by line
- Note any certifications, clearances, or specialized tools required
- Document gaps and proposed mitigations

---

## DIMENSION 3: VALUE ESTIMATION CONFIDENCE

*How confident are we in the contract value estimate?*

| Score | Criteria |
|-------|----------|
| 5 | Value stated in solicitation documents |
| 4 | Value confirmed via BPM or prior award data |
| 3 | Value triangulated from 2+ market sources |
| 2 | Single indirect source (NAICS average, agency budget line) |
| 1 | No reliable value data; pure estimate |

**Scoring Notes:**
- Always check: solicitation itself, BPM award history, GovTribe
- Document all sources and amounts found
- Flag if stated value seems anomalous vs. scope

---

## DIMENSION 4: COMPETITIVE POSITIONING

*How strong is Hypatia's position relative to likely competitors?*

| Score | Criteria |
|-------|----------|
| 5 | Clear differentiator; incumbent relationship or unique capability |
| 4 | Strong position; competitive with 2–3 peer firms |
| 3 | Competitive field; 4–6 capable firms, no clear advantage |
| 2 | Disadvantaged; stronger incumbents or better-positioned primes |
| 1 | Unlikely to win; dominant incumbent or restricted competition |

**Scoring Notes:**
- Research incumbent via BPM and GovTribe
- Check if any set-aside creates preferential access
- Assess if teaming could shift position

---

## DIMENSION 5: COMPLIANCE / ELIGIBILITY

*Does Hypatia meet all mandatory requirements to bid?*

| Score | Criteria |
|-------|----------|
| 5 | Fully compliant; all requirements met with documentation ready |
| 4 | Compliant; minor items need updating (e.g., insurance cert) |
| 3 | Conditionally compliant; 1 gap fillable before submission |
| 2 | Partially compliant; 2–3 gaps requiring significant action |
| 1 | Non-compliant; disqualifying requirement not met |

**Scoring Notes:**
- Hard disqualifiers: missing required certifications, wrong business size, wrong state registration
- VSBE status is an asset — note if it conveys preference
- Never score above 2 if a disqualifier exists

---

## DIMENSION 6: DEADLINE FEASIBILITY

*Can Hypatia prepare a quality proposal within the available time?*

| Score | Criteria |
|-------|----------|
| 5 | 3+ weeks to deadline; standard proposal; adequate resources |
| 4 | 2–3 weeks; manageable with current workload |
| 3 | 10–14 days; tight but achievable with prioritization |
| 2 | 5–9 days; requires dedicated sprint, other work deprioritized |
| 1 | <5 days; extremely high risk, not recommended unless strategic |

**Scoring Notes:**
- Count business days from today to submission deadline
- Factor in current proposal pipeline workload
- Consider if Q&A period is still open (extends effective time)

---

## DIMENSION 7: INCUMBENT RISK

*How entrenched is the current vendor?*

| Score | Criteria |
|-------|----------|
| 5 | No incumbent identified; new requirement or first procurement |
| 4 | Incumbent known but agency dissatisfied or contract ending naturally |
| 3 | Neutral; incumbent performed adequately, agency open to competition |
| 2 | Incumbent has strong relationship; re-bid likely a formality |
| 1 | Sole source or effectively wired; not genuine open competition |

**Scoring Notes:**
- Check BPM for prior awards to same vendor
- Look for multi-year extensions as evidence of entrenchment
- A score of 1 or 2 should trigger Bid/No-Bid discussion at leadership level

---

## DIMENSION 8: INTELLIGENCE COMPLETENESS

*How complete and reliable is the research supporting this report?*

| Score | Criteria |
|-------|----------|
| 5 | All sections complete; all sources verified; no open questions |
| 4 | 90%+ complete; minor gaps documented; confidence high |
| 3 | 75–89% complete; 1–2 unresolved items noted |
| 2 | 50–74% complete; significant gaps; decisions should wait |
| 1 | <50% complete; report is preliminary; do not use for Bid decision |

**Scoring Notes:**
- Self-assess honestly — this dimension catches incomplete research
- Required sources: eMMА portal, BPM, agency website, GovTribe
- Score drops to 1 if deadline is unconfirmed or scope is unclear

---

## COMPOSITE SCORE THRESHOLDS

| Score Range | Percentage | Recommendation |
|-------------|------------|----------------|
| 32–40 | 80–100% | **STRONG BID** — Pursue aggressively |
| 24–31 | 60–79% | **QUALIFIED BID** — Pursue with resource check |
| 16–23 | 40–59% | **MARGINAL** — Bid only if bandwidth available |
| <16 | <40% | **NO-BID** — Do not pursue |

### Override Conditions

Even with a high composite score, recommend **NO-BID** if:
- Dimension 5 (Compliance) scores 1 — disqualifying requirement present
- Dimension 6 (Deadline) scores 1 — insufficient time to produce quality proposal
- Dimension 7 (Incumbent) scores 1 — competition not genuine

Even with a low composite score, consider **STRATEGIC BID** if:
- Agency is on the priority target list AND this is relationship-building opportunity
- Must be approved by BD leadership

---

## SCORING LOG FORMAT

When recording scores, use this format:

```
Dimension 1 — Strategic Alignment: [Score] — [1-sentence rationale]
Dimension 2 — Technical Capability: [Score] — [1-sentence rationale]
Dimension 3 — Value Confidence: [Score] — [1-sentence rationale]
Dimension 4 — Competitive Position: [Score] — [1-sentence rationale]
Dimension 5 — Compliance: [Score] — [1-sentence rationale]
Dimension 6 — Deadline Feasibility: [Score] — [1-sentence rationale]
Dimension 7 — Incumbent Risk: [Score] — [1-sentence rationale]
Dimension 8 — Intelligence Completeness: [Score] — [1-sentence rationale]
COMPOSITE: [X/40] = [X%] — [BID / NO-BID / CONDITIONAL BID]
```

---

*Hypatia Technologies BD Intelligence Unit — Internal Use Only*
*Rubric Version 1.0 — April 15, 2026*
