---
name: advisory-fee-calculation
description: Calculate an investment bank's M&A advisory fee from the engagement letter and the final transaction terms — transaction value as defined, success fee scale, retainer and opinion fee credits, expenses — and prepare the invoice support. Use when a deal has signed or closed and the user asks to calculate the success fee, check an adviser's invoice, or work out what is owed under an engagement letter.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/mna
  author: CorpSkill
  version: 0.1.0
---

# Advisory Fee Calculation

Work out the fee the engagement letter actually provides for. Disputes over advisory fees almost always come from the definition of transaction value, not from the percentage. Read the definition before touching the numbers.

## Workflow

1. **Extract the fee terms from the engagement letter**, quoting each clause:
   - definition of the transaction and of transaction value / aggregate consideration
   - fee formula: flat percentage, minimum fee, tiered scale, incentive ratchet above a threshold price
   - when the fee is earned and payable (signing, closing, on receipt of deferred amounts)
   - retainers, milestone or announcement fees, fairness opinion fee — and whether each is credited against the success fee
   - expenses: what is reimbursable, any cap, any approval requirement
   - tail period and any break-up fee sharing
   - taxes (VAT / sales tax) and currency
2. **Build transaction value as defined.** Go through each component and decide in or out by the letter's wording:
   cash paid · stock consideration (valued how and on which date) · debt assumed or repaid · preferred stock · deferred payments and seller notes · escrow and holdback amounts · earn-outs (at maximum, expected value, or only when paid) · amounts for non-compete or consulting agreements · special dividends · minority interests · cash on the balance sheet (deducted or not) · for partial sales, whether value is grossed up to 100%.
   Take figures from the signed agreement and the closing statement.
3. **Apply the formula.** For a tiered scale, compute each band separately and show it. Apply any minimum. Apply credits. Add reimbursable expenses within the cap. Add tax.
4. **Handle contingent consideration**: state what is payable now and what becomes payable later, with the trigger.
5. **Check**: recompute a second way (effective percentage × value); compare with any fee estimate previously given to the client; confirm the payer entity and whether any co-adviser split applies.
6. **Produce** the calculation and the invoice support.

## Output format

```
## Fee terms
| Term | Provision | Clause |

## Transaction value
| Component | Amount | Included? | Basis in letter | Source of figure |
| Total transaction value | |

## Fee calculation
| Step | Calculation | Amount |
(bands, minimum test, credits, net success fee, expenses, tax, total due now)

## Payable later
| Amount | Trigger | Expected date |

## Points of interpretation
Any component where the letter is unclear — show the fee under each reading.
```

## Rules

- Where the letter is ambiguous, do not choose the reading that favours whoever is asking. Show both and flag it for the banker and legal.
- An invoice that differs from what the client was led to expect should be discussed before it is sent.
- Do not assume market terms for anything the letter does not say.

## Limits

This is a calculation aid. The engagement letter governs, and its interpretation where contested is a legal question.
