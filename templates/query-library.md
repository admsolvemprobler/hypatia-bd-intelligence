# Hypatia Technologies — eMMА Solicitation Intelligence Query Library

**Version:** 1.0 | **Last Updated:** April 15, 2026 | **Maintained by:** Hypatia Technologies BD Intelligence Unit

---

## PURPOSE

This document is the master library of search queries used during the eMMА Solicitation Intelligence research process. Queries are organized by phase and research objective. Copy, adapt, and substitute bracketed variables for each engagement.

**Variable Reference:**
- `[Agency Name]` — Full agency name (e.g., "Maryland Department of General Services")
- `[Agency Abbreviation]` — e.g., "DGS", "MDOT", "DoIT"
- `[Short Title]` —  2–4 word description of the solicitation
- `[Solicitation Number]` — Official solicitation ID
- `[BPM ID]` — BPM system identifier
- `[NAICS Code]` — Primary NAICS code
- `[Product Name]` — Named product or brand
- `[Contract Keyword]` — Key service/product term from scope
- `[Year]` — Current or recent year

---

## PHASE 1: PARALLEL RESEARCH QUERIES

*Used during Phase 3: Deep Intelligence Gathering. Run 3 queries per search_web call.*

### 1.1 Agency Background

```
"[Agency Name]" procurement history Maryland [Year]
"[Agency Abbreviation]" Maryland annual IT budget [Year]
"[Agency Name]" vendor contracts awarded [Year]
```

### 1.2 Solicitation Context

```
"[Solicitation Number]" Maryland procurement
"[Short Title]" [Agency Name] contract award
"[Short Title]" Maryland government solicitation [Year]
```

### 1.3 Scope Research

```
"[Contract Keyword]" Maryland state government contract
"[Contract Keyword]" [Agency Name] requirements
[NAICS Code] Maryland state contract average value
```

### 1.4 Deadline Verification

```
"[Solicitation Number]" due date submission deadline
"[Agency Name]" [Short Title] proposal deadline [Year]
"[Solicitation Number]" Maryland eMMA portal
```

---

## PHASE 2: BPM (BUYER-PERFORMED MARKET) RESEARCH QUERIES

*Use these to search the Maryland BPM database at bpm.maryland.gov*

### 2.1 Award History by Agency

```
[Agency Name] + [Contract Keyword]
[Agency Abbreviation] + NAICS [NAICS Code]
[Agency Name] contracts awarded 2023 2024 2025
```

### 2.2 Incumbent Identification

```
[BPM ID] awarded vendor
"[Short Title]" prior award Maryland
[Agency Name] [Contract Keyword] incumbent [Year]
```

### 2.3 Contract Value Research

```
[Agency Name] [Contract Keyword] contract value
[NAICS Code] [Agency Abbreviation] award amount
"[Contract Keyword]" Maryland state contract award 2024
```

---

## PHASE 3: INCUMBENT RESEARCH QUERIES

*Run via search_web and GovTribe after BPM lookup*

### 3.1 BPM + GovTribe Incumbent Search

```
"[Agency Name]" "[Contract Keyword]" incumbent award [Year]
"[BPM ID]" [Short Title] [Agency Name]
[Agency Name] [Short Title] awarded contract winner
```

### 3.2 Incumbent Company Research

```
[Incumbent Company Name] Maryland government contracts
[Incumbent Company Name] [Agency Name] past performance
[Incumbent Company Name] VSBE MBE Maryland certification
```

### 3.3 Competitive Landscape

```
"[Contract Keyword]" Maryland government contractors [Year]
[NAICS Code] Maryland small business contractors
"[Short Title]" Maryland RFP bidders competitors
```

---

## PHASE 4: OEM / PARTNER PROGRAM QUERIES

*Use when solicitation names specific products or brands*

### 4.1 LOA (Letter of Authorization) Requirements

```
"[Product Name]" government partner program requirements
"[Product Name]" authorized reseller LOA requirements
"[Product Name]" VAR partner tier Maryland 2026
```

### 4.2 Partner Portal Navigation

```
[Product Name] partner portal login
[Product Name] authorized partner directory search
[Product Name] government reseller program apply
```

### 4.3 Sole Source / Brand Research

```
"[Product Name]" sole source justification Maryland
"[Product Name]" government LOA 2026
"[Product Name]" OEM authorized distributor Maryland
```

---

## PHASE 5: VALUE BENCHMARKING QUERIES

*Use when contract value is not stated in solicitation*

### 5.1 Direct Value Research

```
"[Agency Name]" [Contract Keyword] contract value award
"[Solicitation Number]" award amount
[Agency Name] [NAICS Code] contract awarded value [Year]
```

### 5.2 Market Benchmarking

```
[NAICS Code] Maryland state contract average value
"[Contract Keyword]" government contract typical cost
[NAICS Code] federal GSA schedule pricing [Year]
```

### 5.3 Budget Research

```
"[Agency Name]" [Year] budget [Contract Keyword]
"[Agency Abbreviation]" Maryland capital IT budget [Year]
[Agency Name] annual procurement spend [Year]
```

---

## PHASE 6: COMPLIANCE & ELIGIBILITY QUERIES

*Use to verify Hypatia's eligibility for specific requirements*

### 6.1 Set-Aside & Certification

```
[Agency Name] VSBE requirements Maryland
"[Solicitation Number]" MBE SBE set-aside requirements
Maryland VSBE certification eligible NAICS [NAICS Code]
```

### 6.2 Registration & Licensing

```
 Maryland vendor registration state procurement requirements
[Agency Name] contractor prequalification requirements
Maryland [Contract Keyword] contractor license requirements
```

### 6.3 Insurance & Bonding

```
[Agency Name] contractor insurance requirements Maryland
"[Solicitation Number]" bonding insurance minimum
Maryland state contract performance bond requirements
```

---

## QUERY CONSTRUCTION RULES

1. **3-query limit per search_web call** — never exceed 3 queries in one call
2. **Use quotes for exact phrases** — wrap solicitation numbers and agency names in quotes
3. **Include year when recency matters** — append [Year] or "2025 2026" to competitive queries
4. **Avoid yes/no questions** — frame queries as noun phrases, not sentences
5. **Iterate if results are poor** — try alternate keywords, abbreviations, or agency divisions
6. **Log all queries run** — record in Section 10.1 of the report template

---

## QUERY EFFECTIVENESS NOTES

| Query Type | High Value Sources | Common Failures |
|------------|-------------------|-----------------|
| Incumbent search | BPM, GovTribe | Google returns general news |
| Value benchmarking | BPM award history, USASpending | Ranges too wide for small contracts |
| LOA/partner research | OEM portal, NASPO | Portals require login |
| Deadline verification | eMMА direct URL, agency website | Google results may be stale |
| Scope research | eMMА attachment download | PDFs not crawled by search |

---

*Hypatia Technologies BD Intelligence Unit — Internal Use Only*
*Query Library Version 1.0 — April 15, 2026*
