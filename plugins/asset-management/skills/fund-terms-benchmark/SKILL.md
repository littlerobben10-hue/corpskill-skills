---
name: fund-terms-benchmark
description: Compare a fund's proposed terms — fees, carry, hurdle, waterfall, governance and investor protections — with market practice and comparable funds, and identify which terms investors are likely to push back on. Use when the user is designing or reviewing a private equity, venture, credit or hedge fund term sheet, limited partnership agreement or prospectus and asks whether the terms are market, how they compare, or what investors will negotiate.
license: Apache-2.0
metadata:
  industry: finance
  scenario: pe/fundraising-ir
  author: CorpSkill
  version: 0.1.0
---

# Fund Terms Benchmark

Show where a fund's terms sit against what investors see elsewhere: in line, manager-friendly or investor-friendly, term by term, and which departures will cost goodwill in fundraising.

A benchmark needs data. Do not state "market" figures from memory as if they were current statistics — fund terms shift with the fundraising climate and differ by strategy, size and region. Use the comparables and surveys the user supplies or that you can retrieve and cite; where there is no data, describe general practice and label it as that.

## Workflow

1. **Define the fund**: strategy, target size, structure (closed-end partnership, open-end, listed), domicile, target investors, the manager's track record and fund number. Terms a first-time manager can obtain differ from an oversubscribed established one.
2. **Extract the proposed terms** into the table below from the term sheet or draft agreement, quoting sections.
3. **Assemble the reference set**: the manager's own prior funds; comparable funds' terms where the user has them (from investors, placement agents, public pension disclosures, regulatory filings); published terms surveys with their year; investor-body guidance on preferred terms. Record the source and date of each.
4. **Compare term by term** and rate each: in line · manager-friendly · investor-friendly · unusual. Give the reference.
5. **Estimate economic effect** for the terms that move money: model the difference in total fees and carry over the fund's life between the proposal and the reference under one stated return scenario.
6. **Predict negotiation**: which terms large investors will raise first, what they will ask for, and what the manager could offer instead (fee breaks for size or early close, co-investment rights, enhanced reporting).
7. **Summarise** the five or so terms that matter.

## Terms to cover

- **Fees** — management fee rate and base in the investment period and after; step-down; fee offsets for transaction and monitoring fees (percentage offset); organisational expense cap; what the fund bears as expenses
- **Carry** — rate; preferred return and whether compounding; catch-up; whole-fund or deal-by-deal waterfall; clawback, its guarantees and any escrow; treatment of tax distributions
- **Commitment and term** — manager commitment (amount and whether cash); investment period; fund term and extensions; recycling; subsequent closings and equalisation interest
- **Governance** — key person triggers and consequences; removal of the manager with and without cause and the vote required; advisory committee powers; conflicts and successor fund restrictions
- **Investment limits** — concentration, geography, leverage and borrowing (including subscription lines), cross-fund investments
- **Investor rights** — reporting, co-investment, most-favoured-nation, transfer, excuse rights
- **Open-end funds additionally** — liquidity terms, lock-ups, gates, side pockets, performance fee crystallisation and high-water mark

## Output format

```
## Fund profile and reference set (with sources and dates)
## Term comparison
| Term | Proposed | Reference range / practice | Rating | Source | Comment |

## Economic effect
Scenario · fees and carry under proposed vs reference terms

## Likely investor pushback and options
## Summary
```

## Rules

- Separate data from impression. A rating without a cited reference is marked "general practice".
- Consider terms together: a lower fee with weaker offsets may cost investors more.
- Do not present the investor-friendly end as the only acceptable answer; the right terms depend on the manager's position and strategy.

## Limits

Commercial benchmarking only. Fund counsel advises on drafting and on legal and tax consequences in each jurisdiction.
