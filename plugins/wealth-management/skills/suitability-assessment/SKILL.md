---
name: suitability-assessment
description: Assess whether an investment product or recommendation is suitable for a specific client — against their classification, objectives, time horizon, risk tolerance, capacity for loss, knowledge and experience, and existing portfolio — and write the suitability record. Use when the user describes a client and a proposed product, portfolio or structured note and asks for a suitability check, appropriateness test, suitability report or the rationale for a recommendation.
license: Apache-2.0
metadata:
  industry: finance
  scenario: wealth/advisory
  author: CorpSkill
  version: 0.1.0
---

# Suitability Assessment

Decide whether this product fits this client, and record the reasoning so that it would stand up if the investment later loses money. A suitability record is written for the day someone asks "why did you sell them this?".

The assessment uses the facts on the client file. If a needed fact is missing or out of date, the answer is "cannot assess until…", not an assumption that favours the sale.

## Workflow

1. **Establish the framework**: jurisdiction and the firm's policy; service type (advice, discretionary management, or execution-only — where only an appropriateness test of knowledge and experience may apply); client classification (retail, professional, eligible counterparty or the local equivalents) and what it changes. Ask rather than assume.
2. **Collect the client profile**, with the date each item was last confirmed:
   - objectives: growth, income, preservation; specific goals and amounts
   - time horizon and liquidity needs
   - risk tolerance (attitude) — from the firm's questionnaire
   - capacity for loss — income, expenditure, assets, liabilities, dependants; what loss would change their life
   - knowledge and experience — products held before, how long, how often, relevant profession or education
   - existing portfolio and wealth held elsewhere
   - constraints and preferences: tax position, currency, ethical or sustainability preferences, restrictions
   - vulnerability indicators: age, health, recent bereavement, reliance on others, limited financial literacy
3. **Profile the product**: what it is and how it pays; risk rating; worst-case outcome and what causes it; capital at risk and any protection (and whose credit backs it); liquidity and exit cost; term; complexity; all costs; leverage; currency; the manufacturer's target market and negative target market.
4. **Test the match**, one line each, with the evidence:
   - meets a stated objective
   - term and liquidity fit the horizon and cash needs
   - risk is within tolerance **and** within capacity for loss (the lower of the two governs)
   - the client can understand it — knowledge and experience cover this product type, or the gap has been addressed by explanation that is documented
   - effect on the portfolio: concentration in issuer, asset class, currency; overall risk after the trade
   - costs are justified against simpler or cheaper alternatives that would meet the same need
   - within the target market; not in the negative target market
   - any switch: costs and benefits of leaving the existing holding
5. **Conclude**: suitable · suitable with conditions (smaller size, specific warnings) · not suitable · cannot assess. Give the reason in two sentences.
6. **Write the record** in language the client could read.

## Output format

```
## Client profile (with dates confirmed)
## Product summary
## Suitability tests
| Test | Client | Product | Result | Evidence |

## Portfolio effect
Before / after: allocation, concentration, risk level

## Alternatives considered
## Conclusion and rationale
## Risks explained to the client
## Conditions, warnings and follow-up
## Missing or stale information
```

## Rules

- Never infer a higher risk tolerance or more experience than the file shows because the client asked for the product. A client's insistence is recorded as such and handled under the firm's policy for insistent clients.
- Capacity for loss is a fact about finances, not a preference; a client cannot choose to have more of it.
- A complex product needs evidence of understanding specific to that product, not general investing experience.
- Signs of vulnerability raise the standard of care; flag them.
- If the result is "not suitable", say so plainly. Do not look for the size at which it scrapes through unless a smaller holding fits on its own merits.

## Limits

This supports the adviser's judgement and the firm's process. Regulatory definitions, required disclosures and record-keeping differ by jurisdiction; the firm's compliance policy governs.
