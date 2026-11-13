---
name: settlement-fails-tracker
description: Track and analyse failed securities settlements — age each fail, classify the cause, estimate the cost (penalties, funding, buy-in risk), prioritise what to chase and report the trend. Use when the user shares a list of unsettled or failed trades from a custodian, broker or settlement system and asks for a fails report, ageing, root-cause analysis, or what to chase today.
license: Apache-2.0
metadata:
  industry: finance
  scenario: am/ops
  author: CorpSkill
  version: 0.1.0
---

# Settlement Fails Tracker

Turn a raw list of trades that did not settle on time into a work list for today and a picture of why fails keep happening. A fail costs money in penalties and funding, ties up positions, and — repeated — damages the relationship with counterparties and custodians.

## Workflow

1. **Load the fails**: trade reference, security, side (deliver / receive), quantity, cash amount, currency, trade date, intended settlement date, counterparty, custodian or depository, account or fund, current status and reason code if the source gives one, last action and comment. Check for duplicates and for trades that have since settled.
2. **Age each fail** in business days past intended settlement date, using the calendar of the settlement market. Bucket: 1 · 2–3 · 4–7 · 8–20 · over 20.
3. **Classify the cause.** Use the source's reason code as a starting point and the comments to refine:
   - *Our side* — instruction late or missing; wrong standing settlement instructions; insufficient securities (short, pending recall from lending, unsettled purchase); insufficient cash; allocation or booking error
   - *Counterparty* — no instruction; lack of securities or cash; their allocation late
   - *Mismatch* — unmatched on quantity, amount, settlement date, place of settlement or account
   - *Market / infrastructure* — depository, custodian or agent delay; corporate action; holiday
   - *Unknown* — needs investigation
   Note chains: a delivery failing because the matching receipt failed is one problem, not two.
4. **Estimate the cost** of each fail, stating the method:
   - penalties under the applicable settlement discipline regime, where one applies — ask for the rate table or the depository's penalty report rather than assuming rates
   - funding cost or benefit: cash amount × rate × days (failing to deliver means cash not received; failing to receive may mean cash retained)
   - exposure to a buy-in or to counterparty claims, and market risk on the open position
5. **Prioritise today's actions**: rank by cost and risk — age, size, approaching buy-in or regulatory deadlines, fails blocking onward deliveries, fails on our side (fixable now). For each, the next action and the owner.
6. **Analyse the pattern** across the period: fail rate by count and value against trades due; by cause, counterparty, market, security type, fund and desk; repeat offenders; share caused internally. Compare with the previous period.
7. **Recommend fixes** for the top causes (standing instructions clean-up, earlier allocation cut-offs, pre-matching, lending recall timing, a specific counterparty to escalate).

## Output format

```
## Today — [date]
Open fails: [n], [value] · new · resolved since last run · oldest
| Priority | Trade | Security | Side | Amount | Counterparty | Age | Cause | Est. cost | Next action | Owner |

## Ageing
| Bucket | Count | Value |

## Causes
| Cause | Count | Value | % | Internal? |

## By counterparty / market / fund (top 10)
## Trend vs previous period
## Recurring issues and recommended fixes
## Items needing investigation (cause unknown)
```

## Rules

- A cause is recorded only when there is evidence for it; otherwise "unknown" with the question to ask.
- Do not net deliveries against receipts in the counts; do link chains.
- Cost figures are estimates and labelled so; the custodian's or depository's penalty statement is the actual.
- Comments carried forward should say what was done and when, not "chasing".

## Limits

The tracker depends on the status data supplied; it does not connect to settlement systems or contact counterparties. Penalty and buy-in rules differ by market and change — apply the rules the user provides.
