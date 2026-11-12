---
name: distribution-waterfall
description: Compute how proceeds from a private equity or venture fund are split between investors and the manager under the fund's distribution waterfall, including preferred return, catch-up and carried interest. Use when the user has exit or distribution proceeds and asks for a waterfall calculation, carry calculation, LP/GP split, clawback check, or a distribution notice.
license: Apache-2.0
metadata:
  industry: finance
  scenario: pe/fundraising-ir
  author: CorpSkill
  version: 0.1.0
---

# Distribution Waterfall

Work out who gets what when a fund distributes cash. The fund's limited partnership agreement (LPA) decides the answer; this skill applies the LPA's terms to the cash flows and shows every step so that someone else can check it.

Do the arithmetic in a spreadsheet or code, never in your head. Waterfalls depend on dated cash flows and compounding; small errors move real money between investors and the manager.

## Workflow

1. **Read the terms from the LPA, not from memory of "standard" terms.** Ask for the distribution clause and extract the items under "Terms to pin down". Quote the clause next to each term you extract. If a term is not stated, ask; do not fill in a market default without saying so.
2. **Collect the cash flows**: every capital contribution and every prior distribution, with dates and, where the LPA requires it, split by investment. Collect the amount now being distributed and which investment it comes from.
3. **Choose the structure the LPA specifies:**
   - *Whole-fund (European)* — investors receive all contributed capital plus the preferred return across the whole fund before the manager receives any carry.
   - *Deal-by-deal (American)* — carry is calculated investment by investment, usually after returning capital on realised deals plus written-down amounts and allocated expenses. Needs a clawback test.
4. **Run the tiers in order** (the usual four; follow the LPA if it differs):
   1. *Return of capital* — to investors until contributions (as defined) are returned.
   2. *Preferred return* — to investors until they have received the hurdle rate on those contributions, computed from each contribution's date to each distribution's date.
   3. *Catch-up* — to the manager (at the catch-up percentage) until the manager has received its carry share of all profit distributed so far.
   4. *Split* — remaining proceeds shared at the carry percentage (for example 80 / 20).
5. **Check the result** using the tests below.
6. **Report**: the tier table, each party's amount, cumulative figures, and every assumption made.

## Terms to pin down

- Carry percentage and hurdle rate
- Hurdle basis: compound or simple; compounding frequency; day count; whether it accrues on capital contributed for fees and expenses
- Catch-up: percentage (100%, 80%, 50%, none) and what it catches up to
- Whether the hurdle is a true preferred return with catch-up, or a hard hurdle with carry only on the excess
- What counts as "capital" in tier 1: all contributions, or only those for realised investments plus write-downs and allocated fees
- Treatment of the manager's own commitment (it normally receives investor distributions and bears no carry)
- Recycling: whether returned amounts can be recalled and how that affects the tiers
- Tax distributions to the manager and whether they are advances against carry
- Clawback: test dates, whether net of tax, any escrow or holdback percentage
- Fee offsets and whether management fees are returned before carry

## Checks

- Total distributed across all tiers equals the proceeds exactly.
- After a full catch-up, manager carry ÷ (investor profit + manager carry) equals the carry percentage.
- Investor cumulative distributions imply an IRR at or above the hurdle whenever the manager has received carry (whole-fund structures).
- Re-run with proceeds 10% lower: carry should fall, never rise.
- For deal-by-deal structures, compute carry as if the fund were liquidated today at current valuations; if carry already paid exceeds that, report the clawback exposure.

## Output format

```
## Terms applied
| Term | Value | LPA reference |

## Waterfall for distribution of [amount] on [date]
| Tier | Rule | To investors | To manager | Remaining |
| 1 Return of capital | … |
| 2 Preferred return ([x]% [compound/simple]) | … |
| 3 Catch-up ([x]%) | … |
| 4 Split ([x]/[y]) | … |
| Total | | | | 0 |

## Cumulative position after this distribution
Contributed · Distributed to investors · Carry paid · Investor net multiple and IRR · Unreturned capital / unpaid preferred return

## Clawback test (if applicable)
## Assumptions and open questions
```

If asked for a distribution notice, add a per-investor allocation pro rata to commitments (or as the LPA specifies) and state the split of each investor's amount between return of capital and gain.

## Limits

LPA drafting varies and the words control. Where a clause is ambiguous, show the result under each reading and flag it for fund counsel; do not pick one silently. The fund administrator's and auditor's calculation is the official one, and tax treatment is outside this skill.
