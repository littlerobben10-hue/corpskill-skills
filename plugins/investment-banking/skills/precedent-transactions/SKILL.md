---
name: precedent-transactions
description: Build a precedent transactions analysis — screen comparable M&A deals, compute transaction multiples and premiums paid, and derive an implied value range for a target. Use when the user asks for precedent transactions, deal comps, transaction comps, M&A multiples for a sector, or the precedents bar of a football field.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/valuation
  author: CorpSkill
  version: 0.1.0
---

# Precedent Transactions

Value a company by what acquirers have actually paid for similar businesses. The output is a table of comparable deals with their multiples and premiums, and the value range those imply for the target.

The analysis is only as good as the deal data. Do not produce deal values, multiples or dates from memory — they will be plausible and some will be wrong. Every figure must come from a source the user supplies or one you retrieve (company filings, press releases, a deal database export), and the source goes in the table.

## Workflow

1. **Define the target and the purpose.** Sector, business model, size, geography, growth and margin profile; whether the range is for a sell-side pitch, a buy-side bid or a fairness analysis.
2. **Set the screen**, widest first, then tighten until 8–15 deals remain:
   - same sector and business model
   - size band (commonly 0.25× to 4× the target's enterprise value)
   - last 3–5 years, extended if the sector has few deals; note where market conditions differed
   - control transactions only, unless minority deals are the purpose
   - geography where it affects valuation
   State every criterion. A reader must be able to see why a deal is in or out.
3. **Collect per deal**: announcement date, target, acquirer, acquirer type (strategic / financial), % acquired, consideration (cash / stock / mix), equity value, net debt and other bridge items, enterprise value, target's last-twelve-months revenue, EBITDA and (where relevant) EBIT or net income at announcement, source.
4. **Compute**:
   - EV / LTM revenue, EV / LTM EBITDA; forward multiples only if consensus at the time is available
   - for listed targets, premium to the undisturbed share price 1 day, 1 week and 1 month before the first public sign of the deal (leak or announcement, whichever came first)
   - adjust EBITDA for one-offs only where the source discloses them; say when you did
5. **Summarise**: mean, median, high, low, and 25th / 75th percentiles. Show strategic and financial buyers separately if there are enough of each.
6. **Select a range and apply it.** Choose the range from the most comparable deals, not mechanically from the quartiles, and say which deals drove it and why. Apply to the target's metric to get implied enterprise value, then bridge to equity value and per-share value if the bridge items are known.
7. **State the caveats** that apply to this set.

## Judgement points

- Control premiums and synergies are embedded in these multiples; they normally sit above trading comps. If they do not, explain why.
- Earn-outs and contingent payments: show headline value and value excluding contingent amounts.
- Distressed sales, minority stakes, mergers of equals and deals with heavy stock consideration distort multiples — exclude or footnote them.
- Sector-specific metrics may matter more than EBITDA (price / book for banks, EV / subscribers, EV / reserves). Use what acquirers in that sector use.
- "n/a" beats a guessed multiple. A private target with undisclosed financials stays in the list for reference and out of the statistics.

## Output format

```
## Screening criteria
## Transactions
| Date | Target | Acquirer | Type | EV | EV/Rev | EV/EBITDA | Premium 1d / 1m | Source |

## Summary statistics
| | EV/Rev | EV/EBITDA | Premium |   (mean, median, 25th, 75th, high, low)

## Selected range and implied value
| Metric | Target figure | Multiple range | Implied EV | Implied equity value |

## Deals considered and excluded (with reason)
## Caveats
```

## Limits

This skill structures and computes; it does not have a deal database. Without sourced data it should return the screen and an empty table to fill, not invented deals.
