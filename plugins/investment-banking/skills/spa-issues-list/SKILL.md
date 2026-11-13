---
name: spa-issues-list
description: Turn a purchase agreement draft or markup into an issues list — each open point, both sides' positions, its value or risk impact, and a recommended position — ranked so the principals can decide. Use when the user shares an SPA, APA or merger agreement draft, a counterparty's markup or a redline and asks for an issues list, key points summary or negotiation priorities.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/mna
  author: CorpSkill
  version: 0.1.0
---

# SPA Issues List

Reduce a long contract markup to the points that need a commercial decision. Lawyers negotiate the words; the deal team needs to know which points move money or risk, by how much, and what to trade.

## Workflow

1. **Establish the side and the context**: buyer or seller; auction or bilateral; who drafted and who marked up; whether there is warranty and indemnity insurance; the price mechanism agreed in the offer; what the client cares about most (price, certainty, speed, clean exit).
2. **Go through the agreement by topic**, not by clause number, and record each point where the drafts differ or where the draft departs from the agreed offer:
   - **Price mechanism** — locked box or closing accounts; definitions of cash, debt and working capital; leakage and permitted leakage; target working capital; interest or ticker
   - **Deferred and contingent consideration** — earn-out metric, period, operating covenants, acceleration; escrow or holdback size and release
   - **Conditions and certainty** — conditions to closing, regulatory efforts standard and remedies the buyer must accept, material adverse change, financing condition, long-stop date, termination rights and fees
   - **Period to closing** — conduct of business covenants, access, consents
   - **Warranties** — scope, knowledge and materiality qualifiers, disclosure (general or specific; data room disclosed or not), repetition at closing
   - **Liability** — caps, baskets and de minimis, time limits, specific indemnities, tax covenant, recourse (escrow, insurance, seller)
   - **Restrictive covenants** — non-compete and non-solicit scope and duration
   - **Other** — management arrangements, guarantees, governing law and disputes, assignment
3. **Size each issue.** Where it can be quantified, estimate the value at stake (e.g. the difference in definition of debt × the items affected; cap at 10% against 30% of price). Where it cannot, rate the risk high / medium / low and say what event it bites on.
4. **Recommend a position**: hold · trade (and for what) · concede. Note what is usual in comparable deals only as context and say it is general practice, not data.
5. **Rank** by value and risk, not by clause order. Pull the five or so points that need the principals to the top.
6. **Flag gaps**: things neither draft addresses that this deal needs.

## Output format

```
## Decisions needed from principals (top issues)
## Issues list
| # | Topic | Clause | Our draft / position | Their markup | Impact (value or risk) | Recommendation | Priority |

## Departures from the agreed offer letter
## Points for lawyers only (no commercial decision needed)
## Gaps and questions
```

## Rules

- Quote or cite the clause for every issue so the lawyers can find it.
- Link related points: a tight cap matters less with insurance; a wide debt definition and a low working capital target can double count.
- Do not label a point "market" without basis. If the user has precedent data, use it; otherwise describe it as general practice and move on.
- Report what the document says. Do not smooth over a provision that is bad for the client.

## Limits

This is a commercial summary, not legal advice. The lawyers' reading of the drafting governs.
