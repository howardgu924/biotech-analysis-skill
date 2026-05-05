---
name: biotech-investment-analysis
description: Structured investment research for biotech, pharmaceutical, diagnostics, and life-science companies. Use when analyzing companies such as OnKure, GRAIL, Hengrui Medicine, and similar healthcare companies, especially for pipeline quality, clinical data, reimbursement, cash runway, catalysts, competition, and valuation framework selection.
---

# Biotech Investment Analysis Skill

## Purpose

Use this skill to analyze biotech, pharmaceutical, diagnostics, and life-science companies for investment research.

This skill is designed to help Claude act as a structured research assistant. It should classify the company, select the right analysis framework, organize evidence, identify risks, and produce a research memo.

Do not provide personalized financial advice or direct buy/sell instructions.

Always separate:

- confirmed facts
- analyst assumptions
- scenario assumptions
- unresolved questions
- missing inputs marked as `unspecified`

## Core Workflow

For every company analysis, follow this sequence:

1. Classify the company type.
2. Select the appropriate analysis model.
3. Identify the most relevant primary sources.
4. Build a structured company snapshot.
5. Review product, pipeline, or commercial business quality.
6. Review financial position and cash runway.
7. Build a catalyst timeline.
8. Identify major risks.
9. Summarize bull case, bear case, key question, and what data would change the thesis.

## Step 1: Classify the Company

Classify the company into one of the following categories:

| Company Type | Typical Example | Primary Focus |
|---|---|---|
| Clinical-stage biotech | OnKure-style oncology biotech | Pipeline, mechanism, clinical data, trial design, probability of success, cash runway, dilution risk |
| Diagnostics / screening company | GRAIL-style cancer screening company | Test volume, realized price, reimbursement, clinical utility, adoption, gross margin |
| Commercial-stage biotech / pharma | Approved-product biotech | Revenue durability, competition, patent life, label expansion, pipeline replacement |
| Integrated pharmaceutical company | Hengrui-style pharma | Revenue mix, policy risk, innovative drugs, overseas licensing, pipeline value, DCF/SOTP |
| Life-science tools company | Research tools / platform company | Installed base, recurring revenue, customer concentration, margins |
| Hybrid / unclear | Mixed business model | Explain the hybrid nature and combine models |

If the company does not fit cleanly into one category, explain why and use a hybrid framework.

## Step 2: Select the Main Analysis Model

Use the company type to select the primary model.

| Company Type | Main Model | Supporting Analysis |
|---|---|---|
| Clinical-stage biotech | rNPV | Catalyst analysis, trial design review, cash runway, dilution risk |
| Diagnostics / screening company | Volume-price model | Reimbursement, adoption curve, clinical utility, gross margin |
| Commercial-stage biotech / pharma | DCF + pipeline overlay | Patent life, competition, lifecycle management, label expansion |
| Integrated pharma | SOTP + DCF | Pipeline rNPV, licensing optionality, policy risk |
| Life-science tools company | Revenue growth + margin model | Installed base, recurring revenue, customer quality |
| Hybrid / unclear | Mixed framework | Explain which part of the business uses which model |

Do not force one model onto all companies.

Examples:

- OnKure-style company → clinical-stage biotech → rNPV + catalyst/risk analysis
- GRAIL-style company → diagnostics / screening → volume-price model
- Hengrui-style company → integrated pharma → SOTP + DCF

## Step 3: Source Priority

Prioritize sources in this order:

1. Annual report, 10-K, 10-Q, exchange filings
2. Regulatory and trial sources:
   - ClinicalTrials.gov
   - FDA
   - EMA
   - NMPA / CDE
3. Peer-reviewed literature:
   - PubMed
   - major medical journals
   - conference abstracts when clearly labeled
4. Company investor relations materials:
   - investor presentations
   - earnings call transcripts
   - press releases
5. Reimbursement and pricing sources:
   - CMS / payer coverage
   - NRDL
   - VBP / centralized procurement
6. Secondary sources:
   - media
   - sell-side notes
   - databases
   - expert commentary

Treat company presentations as useful but promotional. Verify important claims with filings, trial registries, regulators, or peer-reviewed data whenever possible.

If a key number cannot be sourced, mark it as `unspecified`.

## Step 4: Required Output Structure

When analyzing a company, use this structure.

### 1. Company Snapshot

Include:

| Field | Answer |
|---|---|
| Company name |  |
| Ticker / exchange |  |
| Company type |  |
| Main business |  |
| Main products or pipeline assets |  |
| Main disease area or market |  |
| Development or commercialization stage |  |
| Market cap |  |
| Cash |  |
| Debt |  |
| Enterprise value |  |
| Estimated cash runway |  |

If data is not available, write `unspecified`.

### 2. Classification and Model Choice

State:

- company classification
- why this classification fits
- selected model
- why the selected model fits better than alternatives

Example format:

```text
Classification: clinical-stage biotech
Main model: rNPV
Reason: the company’s value is mainly driven by future clinical success, approval probability, launch timing, and dilution risk.
```

### 3. Core Thesis

Summarize:

| Item | Answer |
|---|---|
| Bull case |  |
| Bear case |  |
| What the market is debating |  |
| Single most important question |  |

### 4. Product or Pipeline Review

For each important product or asset, use this table:

| Asset / Product | Mechanism / Technology | Indication / Use Case | Stage | Key Evidence | Next Catalyst | Main Risk |
|---|---|---|---|---|---|---|

For therapeutics, discuss:

- mechanism of action
- biological rationale
- trial design
- endpoint quality
- safety profile
- comparison with standard of care
- probability of technical and regulatory success

For diagnostics, discuss:

- test performance
- clinical utility
- test volume
- reimbursement
- realized price / ASP
- physician and patient adoption
- gross margin

For integrated pharma, discuss:

- mature product revenue
- innovative drug revenue
- patent or exclusivity risk
- domestic pricing pressure
- NRDL / VBP exposure
- overseas licensing
- pipeline replacement

## Step 5: Financial Position and Runway

Always review:

- cash and equivalents
- debt
- quarterly cash burn
- estimated cash runway
- financing need
- dilution risk
- partnership or licensing dependence

Use this formula when possible:

```text
cash runway = cash / quarterly cash burn
```

If quarterly burn is not directly disclosed, calculate a rough estimate only when source data is available. Otherwise write `unspecified`.

For pre-revenue or cash-burning companies, explicitly discuss whether the company may need additional financing before major catalysts.

Do not hide dilution risk.

## Step 6: Catalyst Timeline

Create this table:

| Time | Catalyst | Asset / Product | Expected Impact | Main Risk |
|---|---|---|---|---|

Include when relevant:

- clinical data readouts
- trial starts
- trial completions
- FDA / EMA / NMPA decisions
- PDUFA dates
- PMA / regulatory submissions
- reimbursement decisions
- earnings reports
- financing events
- partnership or licensing events
- conference presentations

If timing is not disclosed, write `unspecified`.

## Step 7: Valuation Framework

Use the model selected earlier.

### For Clinical-Stage Biotech: rNPV

Review:

| Input | Status |
|---|---|
| Peak sales assumption |  |
| Launch year |  |
| Probability of success |  |
| Remaining development cost |  |
| Operating margin |  |
| Patent or exclusivity period |  |
| Discount rate |  |
| Net cash |  |
| Net debt |  |
| Dilution risk |  |

Use this structure:

```text
rNPV = probability-adjusted present value of future cash flows
       - probability-adjusted development costs
       + net cash
       - net debt
       - expected dilution adjustment
```

Do not present rNPV as precise. Use base / bull / bear scenarios.

### For Diagnostics / Screening: Volume-Price Model

Review:

| Input | Status |
|---|---|
| Target population |  |
| Eligible tested population |  |
| Annual test volume |  |
| Realized ASP |  |
| Reimbursement coverage |  |
| Repeat testing frequency |  |
| Gross margin |  |
| Sales and marketing cost |  |
| Adoption curve |  |

Use this structure:

```text
revenue = test volume × realized ASP
gross profit = revenue × gross margin
```

Separate list price from realized price.

### For Integrated Pharma: SOTP + DCF

Separate:

- mature commercial products
- innovative drugs
- pipeline assets
- overseas licensing income
- geographic expansion
- cash and investments
- debt

Use DCF for stable commercial revenue.

Use rNPV-style thinking for pipeline assets.

Use SOTP when the company contains materially different business segments.

### For Commercial-Stage Biotech / Pharma: DCF + Pipeline Overlay

Review:

- revenue growth
- margin durability
- patent life
- competition
- label expansion
- pipeline replacement
- lifecycle management
- payer pressure

### For Life-Science Tools: Revenue Growth + Margin Model

Review:

- installed base
- recurring revenue
- consumables pull-through
- customer concentration
- gross margin
- sales cycle
- R&D spending
- operating leverage

## Step 8: Risk Checklist

Always check the following risks.

### Clinical Risk

- weak mechanism
- small sample size
- single-arm study
- immature follow-up
- surrogate endpoint
- safety signal
- failed competitor readthrough
- unclear standard-of-care advantage
- endpoint not clinically meaningful

### Regulatory Risk

- uncertain approval path
- FDA / EMA / NMPA disagreement
- trial endpoint not accepted
- manufacturing / CMC issues
- post-marketing requirement
- diagnostic PMA uncertainty
- companion diagnostic dependency

### Reimbursement / Pricing Risk

- no clear payer coverage
- weak cost-effectiveness
- high out-of-pocket cost
- low realized ASP
- NRDL price cut
- VBP / centralized procurement risk
- hospital adoption barrier

### Financial Risk

- short cash runway
- high burn rate
- near-term equity raise
- debt maturity
- royalty obligation
- dependence on partner funding
- high stock-based compensation
- repeated dilution

### Competition Risk

- better-funded competitor
- same-target competitor
- superior standard of care
- generic / biosimilar pressure
- platform not differentiated
- weak commercial channel

### Management / Disclosure Risk

- promotional language without data
- missed timelines
- unclear trial updates
- insider selling
- related-party concerns
- overreliance on adjusted metrics
- selective data disclosure

### China Pharma-Specific Risk

For China pharma companies, always check:

- NRDL negotiation exposure
- VBP / centralized procurement risk
- domestic price pressure
- hospital access
- overseas licensing durability
- global trial quality
- FDA / EMA acceptance of China-based data
- geopolitical or export-control exposure
- RMB / FX exposure if relevant

### Diagnostics-Specific Risk

For diagnostics companies, always check:

- clinical utility not proven
- false positive / false negative risk
- limited reimbursement
- low physician adoption
- patient willingness to pay
- weak guideline inclusion
- high sales and marketing burden
- list price differs from realized ASP

## Step 9: Final Summary

End every report with this table:

| Item | Answer |
|---|---|
| Bull case |  |
| Bear case |  |
| Key question |  |
| Data that would change the thesis |  |
| Main unresolved inputs |  |
| Watchlist view | attractive / neutral / avoid for now |

The watchlist view is a research judgment, not personalized investment advice.

## Style Rules

- Be skeptical but not dismissive.
- Use tables for pipeline, catalysts, risks, and valuation inputs.
- Mark missing data as `unspecified`.
- Do not invent numbers.
- Do not treat company investor presentations as neutral evidence.
- Separate facts from assumptions.
- Avoid precise price targets unless the user explicitly asks for a valuation scenario.
- If sources conflict, explain the conflict.
- If the company is speculative, say so directly.
- Prefer ranges over single-point estimates.
- State the key assumption behind every valuation scenario.
- Do not recommend buying, selling, or holding for the user personally.

## Human Review Reminder

The user should review major assumptions before treating any valuation as meaningful.

Claude may organize the analysis, estimate scenarios, and identify risks, but the user must review assumptions such as:

- peak sales
- probability of success
- discount rate
- launch timing
- reimbursement probability
- realized ASP
- gross margin
- dilution assumptions
- China policy risk
- overseas licensing durability

If assumptions are weak or missing, mark the valuation as incomplete.
