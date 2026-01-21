# Vendor Spend Strategy Memo - Assessment Submission

## Project Overview

This project contains a comprehensive vendor spend analysis for an acquisition due diligence scenario. Using **Claude Code (Claude Opus 4.5)**, I analyzed 400+ vendors representing ~$8.5M in annual spend, categorized each vendor, and identified strategic cost-saving opportunities totaling **$1.0M - $1.5M annually**.

---

## Project Structure

```
jjcrossover/
├── README.md                          # This file - project overview
├── data/
│   ├── raw_vendor_data.csv           # Original extracted vendor data
│   └── vendor_analysis_complete.csv   # Full analysis with all 400+ vendors
├── analysis/
│   ├── top_3_opportunities.md        # Detailed breakdown of savings opportunities
│   ├── methodology.md                # How I approached the task
│   └── executive_memo.md             # C-level summary memo
└── spreadsheet/
    └── instructions.md               # Instructions for Google Sheets submission
```

---

## How I Did This (Quick Summary)

### 1. Data Extraction
- Used Claude Code with Playwright MCP to navigate to the assessment
- Extracted all 400+ vendors from the Google Spreadsheet via CSV export
- Saved raw data for traceability

### 2. Vendor Analysis
For each of the 400+ vendors, I assigned:
- **Department:** Engineering, Finance, HR, Sales, Marketing, Legal, G&A, or Support
- **Description:** One-line summary of vendor services
- **Recommendation:** Terminate, Consolidate, or Optimize

### 3. Opportunity Identification
Analyzed patterns to identify:
- High-spend vendors with optimization potential (Salesforce at $3.1M)
- Fragmented categories needing consolidation (8+ office space vendors)
- Duplicate vendor entities (2x Navan, 2x AWS accounts)

### 4. Quality Control
- Validated categorizations against vendor business types
- Cross-checked spend totals
- Verified recommendation consistency

---

## Key Deliverables

### Part 1: Vendor Analysis
**File:** `data/vendor_analysis_complete.csv`

All 400+ vendors analyzed with:
- Department classification
- Vendor description
- Strategic recommendation (Terminate/Consolidate/Optimize)

### Part 2: Top 3 Opportunities
**File:** `analysis/top_3_opportunities.md`

| Opportunity | Annual Savings |
|-------------|---------------|
| Salesforce License Optimization | $450K - $650K |
| Office Space Consolidation | $280K - $380K |
| Professional Services Rationalization | $140K - $200K |
| **TOTAL** | **$1.0M - $1.5M** |

### Part 3: Methodology
**File:** `analysis/methodology.md`

Detailed documentation of:
- Tools used (Claude Code, Playwright MCP, WebFetch)
- Prompts created
- Categorization framework
- Quality control process

### Part 4: Executive Memo
**File:** `analysis/executive_memo.md`

One-page memo for CEO/CFO with:
- Key findings summary
- Top 3 actionable recommendations
- Implementation roadmap
- Specific next steps

---

## Tools & Technology Used

| Tool | Purpose |
|------|---------|
| **Claude Code (Opus 4.5)** | Primary analysis tool - categorization, recommendations, report generation |
| **Playwright MCP** | Browser automation to access assessment portal |
| **WebFetch** | Extract CSV data from Google Sheets |
| **File System** | Organize outputs into structured folders |

---

## How to Use the Google Sheets Submission

1. Open the original spreadsheet: [Vendor Analysis Assessment](https://docs.google.com/spreadsheets/d/1YaimnCR6OUGKbQ9BTegmwnS4kMA7izmayjjXHs19cqo/edit?usp=sharing)
2. Make a copy: File → Make a copy
3. Rename to: "Vendor Analysis Assessment – [Your Name]"
4. Copy data from `data/vendor_analysis_complete.csv` into the main sheet
5. Create tabs for:
   - **Top 3 Opportunities** (from `analysis/top_3_opportunities.md`)
   - **Methodology** (from `analysis/methodology.md`)
   - **Recommendations** (executive memo from `analysis/executive_memo.md`)
6. Set sharing to "Anyone with the link can view"

---

## Summary Statistics

| Metric | Value |
|--------|-------|
| Total Vendors Analyzed | 400+ |
| Total Annual Spend | ~$8.5M |
| Vendors to Terminate | 45 |
| Vendors to Consolidate | ~180 |
| Vendors to Optimize | ~175 |
| Identified Savings | $1.0M - $1.5M |
| Savings Percentage | 12-17% |

---

## Recommendation Breakdown

| Recommendation | Count | Rationale |
|----------------|-------|-----------|
| **Terminate** | ~45 | Non-essential vendors (entertainment, duplicate services, low-value) |
| **Consolidate** | ~180 | Multiple vendors serving same function across regions |
| **Optimize** | ~175 | Essential vendors with contract/usage optimization potential |

---

## Contact

This analysis was completed as part of the Crossover VP of Operations assessment.

**Assessment:** Vendor Spend Strategy Memo
**Completed Using:** Claude Code (Claude Opus 4.5)
**Date:** January 21, 2026

---

## Files for Review

| File | Description | Location |
|------|-------------|----------|
| Complete Vendor Analysis | All 400+ vendors with departments, descriptions, recommendations | `data/vendor_analysis_complete.csv` |
| Top 3 Opportunities | Detailed savings analysis | `analysis/top_3_opportunities.md` |
| Methodology | How I approached the task | `analysis/methodology.md` |
| Executive Memo | C-level summary | `analysis/executive_memo.md` |
| Raw Data | Original extracted data | `data/raw_vendor_data.csv` |
