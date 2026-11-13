---
name: funds-flow
description: Build the sources-and-uses table and the closing funds flow memo for an M&A or buyout closing — who pays whom, how much, to which account, in what order. Use when a deal is approaching closing and the user asks for a funds flow, flow of funds memo, sources and uses, closing payments schedule or wire schedule.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/mna
  author: CorpSkill
  version: 0.1.0
---

# Funds Flow

Produce the document everyone signs off before money moves at closing: every payment, its payer, its recipient, its amount and its basis in the deal documents. On closing day there is no time to discover that the numbers do not add up.

Work in a spreadsheet or code. Every amount must trace to a document clause or a third-party statement, and total sources must equal total uses to the cent.

## Workflow

1. **Collect the documents and figures**: purchase agreement (price, adjustments, escrows, holdbacks), estimated closing statement (cash, debt, working capital, transaction expenses), debt commitment and fee letters, equity commitment, payoff letters for existing debt, adviser invoices, management rollover and option cash-out schedules, any tax withholding.
2. **Compute the purchase price at closing**, step by step as the agreement defines it:
   base price ± estimated net debt / cash ± estimated working capital against target − seller transaction expenses − other defined deductions = closing payment to sellers, before escrows.
   Use the agreement's definitions, not general accounting ones. Quote the clause for each line.
3. **Build sources**: new debt by tranche (gross, and net of original issue discount and fees if deducted at funding), equity from each investor, rollover equity (non-cash), cash on the target's balance sheet used at closing.
4. **Build uses**: payment to sellers (by seller, per the allocation schedule), repayment of existing debt (principal, accrued interest, prepayment premium, per payoff letters as of the closing date — include the per-day amount in case closing slips), escrow and holdback deposits, option and bonus payments through payroll, financing fees, adviser fees and expenses, taxes, cash to balance sheet.
5. **Check**: sources = uses; each seller's amount = their percentage × distributable proceeds; payoff amounts are for the right date; non-cash items (rollover, net-funded fees) are shown but excluded from wires.
6. **Write the payment schedule**: one row per wire.
7. **List open items** and who must confirm each before the memo is final.

## Output format

```
## Sources and uses
| Sources | Amount |   | Uses | Amount |
(totals equal)

## Purchase price calculation
| Line | Amount | Agreement reference |

## Payment schedule
| # | Payer | Recipient | Amount | Currency | Purpose | Basis (document) | Bank details status |

## Sequence and conditions
Order of steps on the day; what must be confirmed before each release.

## Non-cash movements
## Open items
| Item | Owner | Needed by |
```

## Rules

- Never type or infer bank account details. Record only whether verified wire instructions have been received and confirmed by call-back to a known number — payment fraud targets closings.
- Estimated figures are labelled as estimates; the post-closing true-up is a separate exercise.
- Where currencies differ, state the rate, its source and who bears the difference.
- Round only in presentation; carry full precision in the calculation.
- If sources and uses differ by any amount, stop and find it. Do not add a balancing line.

## Limits

The paying agent, the lenders' agent and counsel run the closing; their figures govern. This skill prepares and reconciles the memo from the documents provided.
