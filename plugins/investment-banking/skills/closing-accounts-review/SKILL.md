---
name: closing-accounts-review
description: Review a post-closing purchase price adjustment — check the closing statement (cash, debt, working capital) against the purchase agreement's definitions and accounting hierarchy, quantify differences from the estimate, and list items to dispute or defend. Use when the user has a closing statement, completion accounts, working capital true-up, dispute notice or earn-out statement to review.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/mna
  author: CorpSkill
  version: 0.1.0
---

# Closing Accounts Review

After closing, one side prepares a statement of the target's actual cash, debt and working capital at the closing date, and the price is trued up against the estimate paid at closing. This skill checks that statement line by line against what the agreement says, and turns the differences into a position.

The agreement's definitions and stated accounting policies govern — not general accounting standards and not what seems fair. Most disputes are won or lost on that point.

## Workflow

1. **Extract the mechanism from the purchase agreement**, quoting clauses:
   - definitions of cash, indebtedness, working capital, transaction expenses; anything specifically included or excluded
   - target working capital, any collar or de minimis threshold, any cap
   - the accounting hierarchy (typically: specific policies in the agreement → consistent past practice → the applicable accounting standards)
   - who prepares the statement, deadlines for delivery, review period, form of a dispute notice, access rights, expert determination and its scope
   - whether adjustment is dollar-for-dollar and how it is settled (escrow first?)
2. **Set out the timeline** with dates: statement due, review period ends, dispute notice deadline, negotiation period, referral to expert. A missed dispute deadline usually makes the statement final.
3. **Build the bridge** from the estimated closing statement to the actual one, by line. Rank differences by amount.
4. **Test each material difference**:
   - Is the item within the definition? (e.g. is this accrual "indebtedness", "working capital", or neither — and is it counted twice?)
   - Was the policy the one the hierarchy requires? Was it applied as in the reference accounts?
   - Is the change a matter of fact (new information about conditions at closing) or of judgement (a new estimate or method)?
   - Was hindsight used beyond the cut-off the agreement allows?
   - Common areas: provisions and reserves (inventory, receivables, warranty, litigation), revenue cut-off, accrued bonuses and holiday pay, deferred revenue, tax balances, leases and debt-like items, cash that is trapped or not freely available, intercompany balances.
5. **Classify each item**: accept · query (need information) · dispute (with basis and amount). For the side defending the statement, the same classes read: firm · needs support · exposed.
6. **Quantify** the net adjustment under the statement as delivered and under your position.
7. **List the information requests** and draft the points for the dispute notice or the response.

## Output format

```
## Mechanism summary and key dates
## Bridge: estimate → actual
| Line | Estimate | Actual | Difference |

## Item review
| Item | Amount | Agreement basis | Assessment | Class | Position amount |

## Net adjustment
| | As delivered | Our position | Difference |

## Information requests
## Draft points for notice / response
```

For an earn-out statement, apply the same method to the earn-out metric: definition, permitted adjustments, covenants on how the business was to be run, and the calculation.

## Rules

- Tie every argument to a clause. "Unreasonable" is not a basis; "inconsistent with the policy in Schedule X as applied in the reference balance sheet" is.
- Do not raise items below any threshold the agreement sets; do preserve every item above it in the notice, since items not raised are usually lost.
- Keep price adjustment claims separate from warranty or indemnity claims; the same facts may support either, but not double recovery.

## Limits

This review supports the deal team and its accountants and lawyers. It does not replace forensic accounting work or legal advice on the dispute process.
