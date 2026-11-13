---
name: ddq-response
description: Answer an investor's due diligence questionnaire (DDQ) or request for proposal (RFP) for an asset manager or private fund, using the firm's approved answer library and source documents, and flag every question that has no approved answer. Use when the user shares a DDQ, RFP, operational due diligence questionnaire or consultant questionnaire and asks to complete it, draft answers, or map it to existing answers.
license: Apache-2.0
metadata:
  industry: finance
  scenario: am/ops
  author: CorpSkill
  version: 0.1.0
---

# DDQ Response

Complete an investor questionnaire accurately and consistently with everything the firm has said before. Every answer becomes a representation an investor relies on; a fluent answer that is not true is worse than a blank.

**Core rule: answer only from approved sources.** If the library and the supplied documents do not contain the answer, do not write one from general knowledge of how firms usually operate. Mark the question for the owner.

## Workflow

1. **Collect the sources**: the firm's approved answer library or the most recent completed DDQs; offering documents; regulatory filings; compliance manual and policies; latest audited financials; performance and assets-under-management data with their as-of dates; organisation chart and biographies. Note the date of each.
2. **Parse the questionnaire**: number every question, including sub-parts and requests for attachments. Record any word limits, format, and the deadline.
3. **Map each question** to a source:
   - *Match* — an approved answer addresses it directly
   - *Partial* — an approved answer covers part, or needs adapting to the question asked
   - *Data* — needs a current figure (assets, performance, headcount, fees)
   - *None* — no approved source
4. **Draft**:
   - *Match*: use the approved wording, trimmed to answer the question asked and nothing more.
   - *Partial*: adapt, mark what was changed, and send for owner review.
   - *Data*: insert the figure with its as-of date and source; if the figure supplied is stale, flag it.
   - *None*: leave a marked placeholder and route to the owner (compliance, operations, investor relations, portfolio management, legal, IT).
5. **Check consistency**: the same fact stated the same way everywhere (assets, staff numbers, dates, service providers, strategy capacity); consistent with the offering documents and regulatory filings; performance shown as the firm's policy and applicable rules require (net of fees, periods, benchmarks, disclosures).
6. **Handle the sensitive questions with care** — regulatory examinations and findings, litigation, breaches and errors, staff departures, valuation overrides, conflicts, cyber incidents. Use only approved language. Never answer "none" by default; a "no" must be confirmed by the owner.
7. **Produce** the completed questionnaire and the review tracker.

## Output format

The questionnaire in the investor's own format, with answers in place, plus:

```
## Review tracker
| Q# | Topic | Status (match / adapted / data / open) | Source and date | Owner | Note |

## Open questions needing an owner
## Adapted answers needing approval
## Figures and their as-of dates
## Attachments requested
## New answers to add to the library after approval
```

## Writing rules

- Answer the question in the first sentence; then support it. Yes / no questions get a yes or no.
- Be specific: names of systems, frequency of controls, who signs off. Remove marketing language.
- Do not volunteer beyond the question, and do not evade it.
- Keep one voice and one tense; write as the firm ("we").
- If a question does not apply, say so and why.

## Limits

Compliance or the designated approver must review before anything is sent. The skill does not verify that library answers are still true — owners do — but it should flag any answer older than twelve months or that conflicts with a newer document.
