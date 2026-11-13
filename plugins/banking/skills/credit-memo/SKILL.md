---
name: credit-memo
description: Draft a credit memo (credit application / credit paper) for a loan to a company or a secured loan to a private client — borrower, request, repayment sources, financial analysis, risks and mitigants, structure and recommendation — for a credit committee. Use when the user has borrower financials and a proposed facility and asks for a credit memo, credit write-up, credit approval paper, annual review or loan proposal.
license: Apache-2.0
metadata:
  industry: finance
  scenario: bank/credit
  author: CorpSkill
  version: 0.1.0
---

# Credit Memo

Write the paper a credit committee decides on. The committee's question is simple — will we be repaid, from what, and what happens if the first answer fails — and the memo must answer it in the first half page.

Analysis must rest on the financial statements and documents supplied. Do not fill gaps with assumed figures; a missing number is reported as missing.

## Workflow

1. **Establish the request**: borrower and group structure (who borrows, who guarantees, where the cash and assets sit); facility type, amount, purpose, tenor, repayment profile, pricing, security, covenants; new money, renewal, increase or amendment; existing exposure to the group. If the bank has a template or a rating model, follow them.
2. **Collect the information**: three or more years of financial statements (audited?) and the latest interim figures; management accounts and projections; debt schedule with maturities; details of collateral and its valuation; ownership and management; account conduct and history with the bank; KYC status.
3. **Analyse the business**: what it sells, to whom, how it competes; concentration of customers and suppliers; cyclicality; management and owners; what has changed recently.
4. **Analyse the financials.** Spread the statements and compute, with trends:
   - growth and margins; quality of earnings (one-offs, capitalised costs, related parties)
   - cash flow: operating cash flow after working capital, capital expenditure, free cash flow before debt service
   - leverage: total debt / EBITDA (and net); adjust for leases and other debt-like items
   - coverage: EBITDA / interest; debt service coverage = cash available for debt service / (interest + scheduled principal)
   - liquidity: cash, undrawn facilities, current ratio, upcoming maturities
   - balance sheet: tangible net worth, gearing
5. **Identify repayment sources** in order: primary (normally operating cash flow — show that it covers scheduled debt service over the tenor), secondary (collateral — value, basis and date of valuation, haircut, loan-to-value, how it would be realised), tertiary (guarantor or sponsor support — and what it is actually worth).
6. **Stress it.** Run a downside on the projections — for example revenue down, margin down, rates up — and show coverage, leverage and covenant headroom. State what level of decline breaks debt service.
7. **Set out risks and mitigants**, each specific to this borrower. A risk with no real mitigant is said to be accepted, with the reason.
8. **Structure**: explain how tenor, amortisation, covenants, security and conditions respond to the risks found. Propose covenant levels with headroom against the base case.
9. **Recommend**: approve, approve with conditions, or decline; proposed risk rating with the drivers.

For a **secured loan to a private client** (lending against a portfolio or property): replace steps 3–4 with the client's wealth, income and liquidity; make collateral the centre — eligibility, lending value by asset, concentration, volatility, margin-call and close-out levels, currency mismatch — and test a market fall.

## Output format

```
# Credit memo — [Borrower] — [date]
## 1. Summary and recommendation
Request · purpose · rating · key strengths (3) · key risks (3) · recommendation
## 2. Facility terms
| Facility | Amount | Tenor | Repayment | Pricing | Security | Covenants |
## 3. Borrower and group
## 4. Business and industry
## 5. Financial analysis
| Metric | Y-2 | Y-1 | Y0 | Interim | Projection |
## 6. Repayment sources and collateral
## 7. Downside case and sensitivity
## 8. Risks and mitigants
| Risk | Assessment | Mitigant |
## 9. Structure rationale and conditions
## 10. Exposure, profitability and compliance status
## Information gaps
```

## Rules

- Lead with repayment, not with company history.
- Projections are management's unless stated; say what you changed and why.
- Lend against cash flow; treat collateral as the fallback, and value it as it would sell in a default.
- Show the bad facts. An omitted weakness discovered later ends the relationship manager's credibility.

## Limits

A draft for the credit officer. Ratings, policy exceptions and approval belong to the bank's credit function and its models.
