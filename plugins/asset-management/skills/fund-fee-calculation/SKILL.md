---
name: fund-fee-calculation
description: Calculate a fund's management and performance (incentive) fees under its offering documents — fee base, rates, crystallisation, high-water mark, hurdle, equalisation or series accounting — and show the working per share class or investor. Use when the user asks to calculate or check management fees, performance fees, incentive allocation, a high-water mark, or a fee invoice for a hedge fund, mutual fund or managed account.
license: Apache-2.0
metadata:
  industry: finance
  scenario: am/ops
  author: CorpSkill
  version: 0.1.0
---

# Fund Fee Calculation

Compute what the manager is owed for a period under the fund's own terms, in a form the administrator, the auditor and an investor can each check. The offering memorandum or the investment management agreement governs every choice below.

Calculate in a spreadsheet or code. Fee errors compound: a wrong high-water mark this period is wrong every period after.

## Workflow

1. **Extract the fee terms**, quoting the document:
   - *Management fee*: rate; base (net asset value, gross assets, committed or invested capital); whether the base is before or after accrued fees; calculation frequency (daily / monthly accrual) and payment frequency; in advance or in arrears; day-count; differences by share class; any rebates or side-letter rates
   - *Performance fee*: rate; measurement period and crystallisation date; high-water mark and whether it ever resets; hurdle (none, fixed rate, benchmark) and whether hard (fee only on the excess) or soft (fee on all gains once cleared); whether calculated before or after management fee; treatment of subscriptions and redemptions within the period; method for fairness between investors (equalisation credits / depreciation deposits, series or tranche accounting, or none)
   - any cap, deferral or clawback
2. **Collect the data**: net asset values and shares outstanding at each valuation point, by class or series; subscriptions and redemptions with dates; prior high-water marks; fees already accrued and paid; the hurdle or benchmark returns for the period.
3. **Management fee**: for each accrual period, base × rate × period fraction. Sum to the payment period. Apply class and side-letter differences.
4. **Performance fee**, per class, series or investor as the method requires:
   - gross NAV per share before performance fee for the period
   - reference level = the higher of the high-water mark and (if a hurdle applies) the hurdle-adjusted level
   - gain above reference × rate = fee per share; zero if below
   - on redemptions within the period, crystallise the fee attributable to the redeemed shares
   - at period end, crystallise, pay, and reset the high-water mark to the NAV per share after fees (only if a fee was earned)
5. **Check**:
   - no performance fee while NAV per share is below the high-water mark
   - an investor who subscribed mid-period pays fees only on their own gain (this is what equalisation or series accounting is for — if the fund has neither, state the resulting unfairness rather than hiding it)
   - recompute total fee as a percentage of average assets and compare with prior periods
   - accrued fee in the NAV equals the calculation
6. **Report** with the working visible.

## Output format

```
## Terms applied
| Term | Value | Document reference |

## Management fee
| Class | Period | Fee base | Rate | Fraction | Fee |

## Performance fee
| Class / series | Opening HWM | Hurdle level | Gross NAV/share | Excess | Rate | Fee/share | Shares | Fee | New HWM |

## Crystallised on redemptions
## Totals, amounts payable now, accruals carried forward
## Assumptions and points of interpretation
```

## Rules

- When the document is ambiguous (for example, whether the hurdle compounds or resets annually), show the fee under each reading and flag it; do not choose the one that pays more.
- Never restate a prior high-water mark without evidence.
- Side-letter terms apply only to the investors who have them.

## Limits

The administrator's calculation, as audited, is the official one. This skill prepares or checks it; it does not interpret documents with legal authority or handle tax.
