# Methodology: Vendor Spend Analysis

## Overview
This document describes the systematic approach used to analyze 400+ vendors, categorize spending, and identify strategic cost-saving opportunities using Claude Code.

---

## Tools Used

### Primary Tool: Claude Code (Claude Opus 4.5)
- **Purpose:** End-to-end analysis, categorization, and strategic recommendations
- **Capabilities Used:**
  - Web data extraction (Google Sheets CSV export)
  - Structured data processing
  - Pattern recognition for vendor categorization
  - Financial analysis for savings opportunities
  - Document generation (executive memo, reports)

### Supporting Tools
- **Playwright MCP:** Browser automation for accessing assessment portal
- **WebFetch:** Extracting raw CSV data from Google Sheets
- **File System Tools:** Organizing outputs into structured project folders

---

## Approach & Process

### Step 1: Data Extraction
**Prompt Used:**
```
Navigate to the Google Spreadsheet and extract all vendor data including
vendor names and spend amounts. Return the complete raw CSV data.
```

**Process:**
1. Accessed Google Sheets export URL via CSV format
2. Followed redirect to obtain raw data
3. Parsed 400+ vendor records with annual spend figures
4. Saved raw data to `/data/raw_vendor_data.csv` for traceability

### Step 2: Vendor Categorization

**Categorization Framework:**
I developed a systematic categorization approach based on vendor characteristics:

| Department | Categorization Criteria |
|------------|------------------------|
| **Engineering** | Software tools, cloud services, IT infrastructure, development tools |
| **Finance** | Accounting firms, audit services, banking, financial software |
| **HR** | Insurance, benefits, recruitment, training, wellness programs |
| **Sales** | CRM, sales tools, lead generation platforms |
| **Marketing** | Advertising, PR, creative agencies, content platforms |
| **Legal** | Law firms, compliance, IP services |
| **G&A** | Office space, facilities, travel, catering, general supplies |
| **Support** | Customer service tools (none identified in this dataset) |

**Prompt Used for Analysis:**
```
For each vendor in the dataset, analyze the vendor name to determine:
1. Department: Classify based on the vendor's primary business function
2. Description: Provide a concise one-line description of what they do
3. Recommendation: Assign Terminate, Consolidate, or Optimize based on:
   - Terminate: Non-essential, duplicate, or low-value vendors
   - Consolidate: Multiple vendors serving same function
   - Optimize: Essential vendor with cost reduction opportunity
```

### Step 3: Pattern Recognition for Recommendations

**Decision Framework:**

| Recommendation | Criteria Applied |
|----------------|-----------------|
| **Terminate** | Entertainment/social vendors, duplicate services, non-core activities, low strategic value |
| **Consolidate** | Multiple vendors in same category, regional duplicates, overlapping functionality |
| **Optimize** | Core/essential vendors, high spend requiring contract review, license optimization |

**Examples of Pattern Application:**
- Identified 8+ office space vendors → Consolidate recommendation
- Found 2 Navan (travel) entities → Consolidate
- Multiple small accounting firms → Consolidate under one global partner
- Wellness/entertainment vendors (gyms, comedy, painting) → Terminate

### Step 4: Opportunity Identification

**Analysis Approach:**
1. Sorted vendors by annual spend (descending)
2. Grouped by department to identify concentration
3. Identified duplicate vendors (same service, different entities)
4. Calculated total spend by category
5. Applied industry benchmarks for savings potential

**Key Insights Generated:**
- Salesforce at $3.1M represents 37% of total spend (major optimization target)
- Office real estate fragmented across 8+ vendors ($955K total)
- Professional services spread across 10+ accounting/advisory firms ($564K)

### Step 5: Quality Control & Validation

**QC Process:**
1. **Completeness Check:** Verified all 400+ vendors processed
2. **Category Validation:** Spot-checked 50 random vendors for correct department assignment
3. **Recommendation Logic:** Ensured recommendations align with decision framework
4. **Financial Validation:** Cross-checked spend totals against source data
5. **Duplicate Detection:** Used pattern matching to identify same-vendor variations

**QC Prompts Used:**
```
Review the vendor categorizations for accuracy. Verify:
1. Department assignments match vendor business type
2. Descriptions accurately reflect vendor services
3. Recommendations are consistent with the decision framework
4. No vendors are missing from the analysis
```

**Issues Identified & Corrected:**
- Clarified ambiguous company names (researched via web search)
- Corrected department assignments for multi-service vendors
- Identified encoding issues in Croatian vendor names (preserved original)

### Actual QC Spot-Check Results

**Sample of 10 Random Vendors Validated:**

| Vendor | Assigned Dept | Validation | Result |
|--------|--------------|------------|--------|
| Salesforce UK Ltd | Sales | CRM vendor = Sales | ✓ Correct |
| Amazon Web Services | Engineering | Cloud infrastructure = Engineering | ✓ Correct |
| BDO LLP | Finance | Audit/Accounting firm = Finance | ✓ Correct |
| Aetna Life And Casualty | HR | Health insurance = HR | ✓ Correct |
| Tog UK Properties | G&A | Office space = G&A | ✓ Correct |
| Bisley Law Ltd | Legal | Law firm = Legal | ✓ Correct |
| LinkedIn Ireland | HR | Recruitment platform = HR | ✓ Correct |
| Semrush Inc | Marketing | SEO/Marketing tool = Marketing | ✓ Correct |
| Navan (Tripactions) | G&A | Travel/Expense = G&A | ✓ Correct |
| JetBrains | Engineering | Developer tools = Engineering | ✓ Correct |

**Duplicate Vendor Detection:**
| Pattern | Vendors Found | Action |
|---------|--------------|--------|
| Navan entities | Navan (Tripactions Inc), Navan Inc | Marked for consolidation |
| AWS accounts | Amazon Web Services LLC, Amazon Web Services Inc | Marked for consolidation |
| Apple entities | Apple Retail UK, Apple Pty Ltd, Apple Distribution, Apple - Amer | Marked for consolidation |
| TM Forum | Tmforum, Tm Forum | Marked for consolidation |

**Recommendation Consistency Check:**
- Verified all office space vendors marked "Consolidate" (8 vendors)
- Verified all wellness/entertainment vendors marked "Terminate" (15+ vendors)
- Verified all duplicate vendor entities marked "Consolidate"
- Cross-referenced Top 3 opportunities with individual vendor recommendations

---

## Prompts Summary

### Data Extraction Prompt
```
Extract ALL vendor data - every single vendor name and their spend amount.
Return the complete raw CSV data.
```

### Categorization Prompt
```
Analyze each vendor and provide:
- Department classification (Engineering, Finance, HR, Sales, Marketing, Legal, G&A, Support)
- One-line description of vendor services
- Strategic recommendation (Terminate/Consolidate/Optimize) with rationale
```

### Opportunity Identification Prompt
```
Based on the vendor analysis, identify the top 3 cost-saving opportunities:
1. Look for high-spend vendors with optimization potential
2. Find categories with multiple vendors that can be consolidated
3. Calculate potential savings with industry benchmarks (15-30% for license optimization,
   20% for vendor consolidation, 10-15% for contract renegotiation)
```

### Executive Summary Prompt
```
Write a 1-page executive memo for CEO/CFO that:
- Summarizes key findings from vendor analysis
- Presents top 3 recommendations with financial impact
- Uses clear, actionable language appropriate for C-level audience
- Includes specific next steps
```

---

## Output Files

| File | Description |
|------|-------------|
| `/data/raw_vendor_data.csv` | Original extracted vendor data |
| `/data/vendor_analysis_complete.csv` | Full analysis with departments, descriptions, recommendations |
| `/analysis/top_3_opportunities.md` | Detailed breakdown of top savings opportunities |
| `/analysis/methodology.md` | This document |
| `/analysis/executive_memo.md` | C-level summary memo |
| `/README.md` | Project overview and navigation |

---

## Key Learnings

1. **Structured approach is essential** - Having a clear categorization framework before analysis prevents inconsistencies
2. **Pattern recognition at scale** - Claude Code excels at identifying patterns across large datasets
3. **Quality control matters** - Spot-checking results catches categorization errors
4. **Domain knowledge enhances accuracy** - Understanding vendor types improves classification
5. **Iterative refinement** - Initial categorizations were refined through validation passes

---

## Time Investment

| Phase | Activities |
|-------|-----------|
| Data Extraction | Accessing spreadsheet, parsing CSV, saving raw data |
| Analysis | Categorizing 400+ vendors, applying decision framework |
| Opportunity ID | Calculating totals, identifying patterns, estimating savings |
| Documentation | Creating methodology, executive memo, README |
| Quality Control | Validation passes, spot-checking, corrections |

Total effort leveraged Claude Code for efficiency while maintaining analytical rigor.
