---
name: new-issue-allocation
description: Propose allocations for an equity or bond new issue from the order book under stated allocation principles, and document the rationale. Use when a deal is priced or about to price and the user asks for an allocation proposal, allocation run, scaling of orders, or an allocation justification record.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/ecm-dcm
  author: CorpSkill
  version: 0.1.0
---

# New Issue Allocation

Produce a first allocation proposal that the syndicate desk and the issuer can adjust: every order, what it gets, and why. Regulators expect allocations to follow a stated policy and to be recorded; the rationale column is as important as the numbers.

Do the arithmetic in a spreadsheet or code. Allocations must sum exactly to the deal size.

## Workflow

1. **Get the inputs**: final deal size (and any over-allotment), final price or spread, the order book with limits and the desk's quality grades, minimum allocation and denomination or lot size, any tranches (institutional / retail, by currency or region), cornerstone or directed allocations already agreed.
2. **Get the principles** — ask; do not assume. Typically the issuer's objectives ranked (long-term holders, a diversified register, specific target investors, a stable aftermarket, some liquidity) plus the firm's allocation policy. Record them at the top of the output.
3. **Remove orders that are not good** at the final price or that fail a condition. List them.
4. **Fix the protected amounts**: cornerstones, agreed minimums, retail tranche.
5. **Tier the remaining orders** by the principles — for example: (A) high-quality long-term investors who engaged early and gave price leadership; (B) good investors with smaller or later orders; (C) trading-oriented accounts and orders that look inflated.
6. **Set fill rates by tier**, highest for A, so that the total equals the size. Then adjust individual orders:
   - cap any single investor at a stated share of the deal
   - lift very small allocations to the minimum, or zero them, per policy
   - round to lot or denomination; fix the rounding residue on the largest allocations
7. **Test the result**: sum = deal size; top-10 concentration; split by investor type and region against the issuer's objectives; proportion to trading accounts (enough for liquidity, not enough to flood the market); no order allocated more than it asked for.
8. **Write the rationale** for each tier and for every exception — any order treated differently from its tier.

## Output format

```
## Allocation principles applied
## Summary
Deal size · demand · average fill · number allocated / zeroed
| By tier / type / region | Demand | Allocated | Fill % | % of deal |

## Allocation table
| Investor | Type | Tier | Order | Limit | Allocation | Fill % | % of deal | Rationale |

## Exceptions
| Investor | Treatment | Reason |

## Orders not allocated
## Checks
```

## Rules — conduct

- Allocation must not be influenced by: the investor's commission or other business with the firm, a promise of future business, an agreement to buy in the aftermarket, or personal relationships. If the user states such a reason, do not apply it; say it cannot be a basis.
- Firm, staff and connected accounts follow the firm's restrictions — flag any that appear in the book.
- The issuer's preferences are legitimate inputs; record that they were the issuer's.
- Keep the record: principles, proposal, each change made by the desk or issuer and why.

## Limits

A starting proposal. The final allocation is decided by the bookrunners with the issuer under the firm's allocation policy and local regulation, which this skill does not replace.
