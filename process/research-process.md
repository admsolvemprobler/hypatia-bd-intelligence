# Hypatia Technologies — eMMA Solicitation Intelligence Research Process
## Methodology Documentation for Training Purposes
**Version:** 1.0
**Calibration Standard:** WNADA HVD Report (March 17, 2026) + April 2 eMMA Report
**Maintained by:** Hypatia Technologies BD Intelligence Unit
**Last Updated:** April 15, 2026

---

## OVERVIEW

This document outlines the end-to-end research and analysis process used to
produce the eMMA Solicitation Intelligence Package. It is written for training
purposes so that any analyst — human or AI — can reproduce reports of equal or
greater depth using the same methodology.

The process covers six sequential phases:
1. Source Identification & Collection
2. Solicitation Triage & Deduplication
3. Deep Intelligence Gathering (per solicitation)
4. Analysis & Scoring
5. Report Drafting & Quality Review
6. Output Packaging & Delivery

---

## PHASE 1: SOURCE IDENTIFICATION & COLLECTION

### 1.1 Primary Source — eMMA Public Solicitations Portal
- URL: https://vendors-emma.maryland.gov/page.aspx/en/rfp/request_browse_public
- Filter: Status = Open
- Sort: By most recent Publish Date (descending)
- Collect: BPM ID, Title, Status, Due Date, Publish Date, Category, Solicitation Type, Issuing Agency
- Capture method: read_page tool or get_page_text tool

### 1.2 Calibration Sources
- Load prior report(s) provided by the client as calibration benchmarks
- Extract the template structure, depth standard, and section format
- Apply as the minimum quality bar for all new reports

### 1.3 Secondary Sources — Third-Party Aggregators

| Platform | Best Used For |
|----------|--------------|
| HigherGov (highergov.com) | Agency profiles, scope summaries, AI value estimates, contacts |
| BidBanana (bidbanana.thebidlab.com) | Scope details, NAICS codes, pre-bid dates |
| GovTribe (govtribe.com) | Prior awards, incumbent identification, document links |
| DemandStar (demandstar.com) | Prior award records, comparable contracts |
| BidNet Direct (bidnetdirect.com) | Alternative deadline confirmation, scope summaries |
| CivicIQ (civiciq.com) | Scope details for education/municipal solicitations |
| Starbridge AI (starbridge.ai) | Scope summaries, RFP analysis |

### 1.4 Primary Agency Sources
- Check issuing agency's official procurement page for addenda, Q&A deadlines, buyer contact

### 1.5 Board of Public Works (BPW) Records
- URL: https://bpw.maryland.gov/MeetingDocs/
- Search by agency and contract keyword
- Use to confirm: incumbent vendor names, prior contract values, award dates

### 1.6 OEM / Vendor Partner Program Sources
- For named-product solicitations: navigate to the OEM partner/reseller program page
- Collect: authorization steps, tier structure, application URL, timeline, deal registration process

---

## PHASE 2: SOLICITATION TRIAGE & DEDUPLICATION

### 2.1 Collect the Full Listing
- Extract all open solicitations from eMMA page 1 (most recent 25)

### 2.2 Deduplication Check

| Check | Method |
|-------|--------|
| Same title, same agency, different BPM | Compare titles and agencies across full list |
| Re-solicitation of a prior BPM | Search HigherGov/GovTribe for prior BPM with identical scope |
| Same agency, near-identical scope | Flag for human review |
| Multiple solicitations from same agency | Confirm each covers distinct scope |

### 2.3 Select Report Set
- Default: Top 12 most recently published open solicitations
- Exclude: Any confirmed duplicate

### 2.4 Deadline Urgency Pre-Screen
- Due within 5 days: CRITICAL
- Due within 10 days: URGENT
- Due within 20 days: ACTIVE
- Due 20+ days: STANDARD

---

## PHASE 3: DEEP INTELLIGENCE GATHERING

### 3.1 Solicitation Overview Data
Collect from eMMA and aggregators: BPM ID, Solicitation Number, Title, Agency, Type, NAICS, Published Date, Pre-Bid Meeting, Q&A Deadline, Submission Deadline, POC, Place of Performance, Contract Term

### 3.2 Agency Profile Research
- Agency type, size indicators, procurement history, technology posture, equity program participation

### 3.3 Scope of Work Intelligence
- Primary deliverables, technical requirements, staffing requirements, special conditions

### 3.4 Contract Value Research — Minimum THREE methods:
1. HigherGov AI estimate
2. NAICS code benchmark
3. Volume x rate calculation
4. Prior award comparables
5. BPW prior award records
6. Market rate research
7. Peer jurisdiction comparables

Confidence levels: HIGH (75-100%), MEDIUM (50-74%), LOW (25-49%), SPECULATIVE (<25%)

### 3.5 Barrier to Entry Research
Rate each factor 1-5:
- Technical Expertise Required
- Regulatory/Licensing Gate
- Capital/Equipment Investment
- Incumbent Advantage
- Deadline Urgency
- Scale/Capacity Requirements
- MBE/SBR/VSBE Goals
- Domain Specialization

### 3.6 OEM / LOA Research
- Identify OEM, navigate to partner program, document authorization steps

### 3.7 Incumbent Identification
Sources in priority order:
1. BPW meeting agendas
2. GovTribe prior awards
3. DemandStar bid abstracts
4. Agency procurement page
5. USASpending (federally-funded)
6. News/press releases

---

## PHASE 4: ANALYSIS & SCORING

### 4.1 SMX Fit Scoring (0=fail, 1=pass per gate)

| Gate | Question |
|------|----------|
| S1 - Service Match | Hypatia capability aligns with deliverable? |
| S2 - Pattern Match | Matches prior wins or target sectors? |
| S3 - Scope Bounded | Work clearly defined; no open-ended liability? |
| S4 - Proofable | Past performance or POC available? |
| S5 - Compliance Achievable | All gates clearable within deadline? |
| S6 - Human Review | Value + fit justifies BD resource spend? |

Scoring: 6/6=Execute, 4-5/6=Pursue as sub, 2-3/6=Monitor, 0-1/6=No-Bid

### 4.2 LOA / Prime / OEM Decision Logic

| Condition | Disposition |
|-----------|-------------|
| Named OEM + not yet authorized | LOA REQUIRED |
| Named OEM + incumbent entrenched + no LOA path | OEM DIRECT |
| Professional services + expertise gap + recurring | PRIME PARTNERSHIP |
| Direct Hypatia capability + no hard gate | PRIME BID |
| Hard mismatch OR expired deadline | NO-BID |
| High value + long timeline + relationship opportunity | MONITOR |

---

## PHASE 5: REPORT DRAFTING & QUALITY REVIEW

### 5.1 Draft Individual Reports
- All 7 sections completed (no section blank or TBD)
- Minimum 2 independent source citations per report
- Contract value uses minimum 3 triangulation methods
- Barrier table rates minimum 5 factors

### 5.2 Self-Audit Against Calibration Standard
- Compare section by section against WNADA HVD report
- Flag any section shallower than calibration standard

### 5.3 Run Master Audit (Template 02)
- Complete all 8 audit dimensions

### 5.4 Build Comparative Documents
- Templates 03, 04, 05, 06

### 5.5 Confidence Self-Assessment
- Score 1-10; document gaps; state what closes each gap

---

## PHASE 6: OUTPUT PACKAGING & DELIVERY

### 6.1 Document Order
1. Master Comparative Summary
2. Priority Action Matrix
3. Individual Reports 1-12
4. Master Audit & Quality Review
5. Supporting registries

### 6.2 Format Standards
- All tables use markdown pipe format
- BPM IDs always bolded in headers
- Confidence levels stated as percentage + descriptor
- Dispositions in bold capitals

### 6.3 Quality Gates Before Delivery
- [ ] All 12 reports delivered
- [ ] No section blank or TBD
- [ ] All values use 3+ triangulation methods
- [ ] All barrier tables include 5+ factors
- [ ] All SMX scores stated
- [ ] All dispositions in bold
- [ ] Duplicate check completed
- [ ] Deadline registry current
- [ ] Incumbent registry populated
- [ ] Confidence self-assessment complete
- [ ] Priority Action Matrix has owner + timeline for Tier 1+2

---

## APPENDIX A: SEARCH QUERY TEMPLATES

### Per-BPM Deep Search:
- `"[BPM ID] [Short Title] [Agency Name]"`
- `"[Solicitation Number] Maryland 2026"`
- `"[Agency Name] [contract keyword] incumbent award [year]"`

### OEM / Partner Program:
- `"[Product Name] authorized reseller partner program requirements"`
- `"[Product Name] government partner LOA 2026"`

### Value Benchmarking:
- `"[Agency Name] [contract category] contract value award"`
- `"Maryland [NAICS code] state contract average value"`

---

## APPENDIX B: TOOL USAGE SEQUENCE

| Phase | Primary Tool | Secondary Tool |
|-------|-------------|----------------|
| Source collection | get_page_text | read_page |
| Parallel research | search_web (3 queries/call) | navigate |
| OEM partner research | navigate (partner portal) | search_web |
| BPW incumbent research | search_web | navigate |
| Report drafting | Direct output | todo_write |
| Quality review | todo_write | Direct output comparison |

---

## APPENDIX C: COMMON FAILURE MODES & MITIGATIONS

| Failure Mode | Detection | Mitigation |
|-------------|-----------|------------|
| Expired deadline missed | Pre-screen Phase 2 | Run urgency check before deep research |
| Duplicate solicitation included | Audit Dimension 6 | Cross-check BPM IDs and agency+scope pairs |
| Single-source value estimate | Audit Dimension 3 | Require minimum 3 methods |
| Named product missed (no LOA flag) | Report Section 6 | Always check title for brand names |
| Incumbent not researched | Audit Dimension 7 | Always run BPW + GovTribe per BPM |
| Deadline discrepancy | Audit Dimension 8 | Cross-check deadline across 2+ sources |
| Report truncated mid-delivery | Self-audit | Complete full audit before marking complete |
| SMX score inconsistency | Audit Dimension 5 | Score all BPMs in one table side-by-side |
