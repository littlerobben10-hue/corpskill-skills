---
name: dd-request-list
description: Build a tailored due-diligence request list (DRL) for a private equity or growth investment. Use when the user describes a target company or shares a CIM / teaser and asks for a diligence checklist, information request list, or what to ask management.
license: Apache-2.0
metadata:
  industry: finance
  scenario: private-equity
  author: CorpSkill
  version: 0.1.0
---

# Due-Diligence Request List

Produce a prioritized, deal-specific DRL that a deal team can send to the target, not a generic 400-line template.

## Workflow

1. **Frame the deal.** Capture: company, sector, business model (SaaS, manufacturing, services, marketplace…), deal type (buyout, minority growth, recap, add-on), approximate size, and the investment thesis in 1–2 sentences. Ask if the thesis is unknown — it drives prioritization.
2. **Identify thesis-critical questions.** List the 3–5 things that must be true for the thesis to work (e.g. "net revenue retention > 110%", "margin expansion from procurement"). Every P1 request must map to one of these.
3. **Build the list** across the workstreams below, adapting items to the business model. Drop items that do not apply; add sector-specific ones (e.g. cohort data for SaaS, capacity utilization for manufacturing, payer mix for healthcare).
4. **Prioritize.** P1 = needed before IOI / LOI, P2 = confirmatory, P3 = nice to have / pre-close.
5. **Output** as a table ready to paste into Excel, followed by the thesis-critical questions.

## Workstreams

- **Financial**: monthly P&L, BS, CF (3 yrs + YTD), revenue bridge, QoE adjustments, working capital seasonality, capex split (maintenance vs growth), budget vs actual
- **Commercial**: customer list with revenue by year, cohort / retention, top-20 concentration, pricing history, pipeline, churn reasons, market sizing support
- **Operational**: org chart, headcount by function, key supplier contracts, capacity, IT systems
- **Legal**: cap table, material contracts (change-of-control clauses), litigation, IP ownership, permits
- **HR**: comp & benefits, key-person agreements, equity plans, attrition
- **Tax**: filings by jurisdiction, open audits, transfer pricing, NOLs
- **ESG / Risk**: environmental liabilities, cybersecurity incidents, insurance coverage

## Output format

```
## Thesis-critical questions
1. <question> → requests #3, #7, #12

## Request list
| # | Workstream | Request | Priority | Thesis link | Format requested |
|---|---|---|---|---|---|
```
