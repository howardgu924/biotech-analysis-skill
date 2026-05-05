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

Classify the company by value driver, not by industry label alone.

Use one of the following categories:

| Company Type | Typical Example | Primary Value Driver |
|---|---|---|
| Clinical-stage biotech | OnKure-style oncology biotech | Unapproved pipeline assets, clinical data, probability of success, catalysts |
| Diagnostics / screening company | GRAIL-style cancer screening company | Test volume, realized ASP, reimbursement, clinical utility, adoption |
| Commercial-stage biotech / pharma | Approved-product biotech | Product revenue, patent life, competition, label expansion, pipeline replacement |
| Integrated pharmaceutical company | Hengrui-style pharma | Mature revenue, innovative pipeline, policy risk, overseas licensing, SOTP value |
| Life-science tools company | Research tools / platform company | Installed base, consumables pull-through, recurring service revenue, margins |
| CDMO / CMO | Contract manufacturing company | Capacity, utilization, backlog, pricing, customer concentration |
| Medical device / consumables company | Surgical device or hospital consumables company | Installed base, procedure volume, consumables pull-through, reimbursement |
| Digital health / SaMD company | Medical software or AI-enabled healthcare company | ARR, PMPM, user retention, utilization, reimbursement, regulatory classification |
| Rare disease / orphan drug company | Orphan drug developer | Diagnosed population, treatable population, pricing, access, exclusivity |
| Synthetic biology / platform company | Platform with service revenue and downstream economics | Service revenue, milestones, royalties, value-share, platform optionality |
| Hybrid / unclear | Mixed business model | Use SOTP and explain which segment uses which model |
| Other / unspecified | Not enough information | Mark classification as `unspecified` and identify missing information |

If the company does not fit cleanly into one category, classify it as hybrid and use SOTP.

Always explain why the classification fits.

## Step 2: Select the Main Analysis Model

Select the primary model based on where enterprise value comes from.

| Company Type | Main Model | Supporting Analysis |
|---|---|---|
| Clinical-stage biotech | rNPV | Trial design review, catalyst analysis, cash runway, dilution risk |
| Diagnostics / screening company | Volume-price model | Reimbursement, adoption curve, clinical utility, gross margin |
| Commercial-stage biotech / pharma | DCF + pipeline overlay | Patent life, LOE, competition, label expansion, lifecycle management |
| Integrated pharma | SOTP + DCF | Pipeline rNPV, policy risk, licensing optionality |
| Life-science tools company | Installed base + consumables model | Recurring revenue, service attach rate, customer quality |
| CDMO / CMO | Capacity-utilization model | Backlog, customer concentration, capex, utilization, pricing |
| Medical device / consumables company | Installed base + procedure / pull-through model | Procedure volume, capital equipment cycle, consumables ASP |
| Digital health / SaMD company | ARR / PMPM + cohort model | Churn, retention, utilization, regulatory classification, payer coverage |
| Rare disease / orphan drug company | rNPV with population-access overlay | Diagnosed population, treatable population, access, orphan exclusivity |
| Synthetic biology / platform company | Service revenue + milestone / royalty SOTP | Platform optionality, value-share, program-level probability |
| Hybrid / unclear | SOTP | Use the correct model for each segment |
| Other / unspecified | Temporary mixed framework | Identify missing inputs before valuation |

Do not force one model onto all healthcare companies.

Examples:

- OnKure-style company -> clinical-stage biotech -> rNPV + catalyst/risk analysis
- GRAIL-style company -> diagnostics / screening -> volume-price model
- Hengrui-style company -> integrated pharma -> SOTP + DCF
- CDMO company -> capacity-utilization model + DCF
- Medical device company -> installed base + procedure/pull-through model
- Digital health company -> ARR/PMPM + cohort model

## Step 2A: Identify the Revenue Architecture

Before building valuation, identify how the company actually makes money.

Answer these questions:

| Question | If Yes, Consider |
|---|---|
| Is most value from unapproved pipeline assets? | rNPV |
| Is most value from stable commercial products? | DCF |
| Does the company have multiple unrelated or mixed-maturity segments? | SOTP |
| Is revenue driven by test volume, procedures, or consumables? | Volume-price or installed base model |
| Is revenue driven by contracted manufacturing or services? | Capacity-utilization or unit-economics model |
| Is revenue subscription-like or PMPM-based? | ARR / PMPM cohort model |
| Is value driven by milestones, royalties, or value-share? | Probability-weighted SOTP or option-adjusted SOTP |

Operating models such as volume-price, installed base, capacity-utilization, and ARR/PMPM usually estimate revenue and margin first. Then connect them to DCF or SOTP.

Do not treat a revenue model as a complete valuation model by itself.

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
| Valuation completeness | complete / partial / incomplete |
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

## Uncertainty Tagging Rules

For every major valuation input, include uncertainty metadata.

Each important model input should include:

- Source Type
- Confidence
- Scenario
- As-of date, if available
- Whether the value is a confirmed fact, analyst assumption, or scenario assumption

Use these labels:

| Label | Allowed Values |
|---|---|
| Source Type | filing / regulator / trial registry / literature / company guidance / industry report / analyst assumption |
| Confidence | high / medium / low |
| Scenario | base / bull / bear |
| Input Type | confirmed fact / analyst assumption / scenario assumption / unspecified |

Rules:

- If a key input cannot be verified, write `unspecified`.
- If a key input is estimated rather than directly disclosed, label it as an assumption.
- If a key input is highly uncertain, provide a range instead of a single number.
- If two or more major valuation inputs are low-confidence, do not present a precise valuation result.
- If a valuation depends mainly on analyst assumptions, state that the valuation is assumption-sensitive.
- If sources conflict, explain the conflict rather than choosing one silently.

Use this valuation completeness label:

| Valuation Completeness | Meaning |
|---|---|
| complete | Most key inputs are sourced from filings, regulators, trial registries, or strong literature |
| partial | Some key inputs are missing or assumption-based, but the framework is still useful |
| incomplete | Too many key inputs are missing or low-confidence for a meaningful valuation |

If valuation completeness is `partial` or `incomplete`, emphasize scenario analysis over point estimates.

Do not present precise price targets when valuation completeness is `partial` or `incomplete`.

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
