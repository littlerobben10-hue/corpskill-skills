---
name: research-compliance-check
description: Pre-review an investment research report before it goes to the supervisory analyst or compliance — required disclosures, rating and price-target support, unsupported or promissory statements, sourcing, selective disclosure and restricted-list issues. Use when the user has a draft research note, initiation, rating change or sector report and asks for a compliance check, supervisory review, disclosure check, or what will get flagged before publication.
license: Apache-2.0
metadata:
  industry: finance
  scenario: research/company
  author: CorpSkill
  version: 0.1.0
---

# Research Compliance Check

Read a draft research report the way a supervisory analyst does and list what must be fixed before publication. The aim is to shorten the formal review, not to replace it.

Rules on research differ by jurisdiction and firm (disclosure wording, quiet periods, who may see drafts). Apply the firm's policy and checklist where the user supplies them; otherwise use the general standards below and say so.

## Workflow

1. **Identify the report**: issuer(s), type (initiation, update, rating or target change, sector piece, desk commentary), analyst, intended distribution and jurisdictions. Ask whether the issuer is on the firm's restricted or watch list and whether the firm has a current banking mandate — this skill cannot see those lists.
2. **Check the fixed elements are present and current**:
   - rating, price target, time horizon; previous rating and target where changed
   - rating definitions and distribution of ratings
   - price as of a stated date; price chart with rating and target history where required
   - valuation methodology and the basis for the target
   - risks to the rating and target — specific to the company, on both sides
   - analyst certification
   - conflict disclosures: firm and analyst holdings, investment banking relationships and compensation, market making, other material conflicts
   - legal entity, distribution restrictions, date and time of production
3. **Test the reasoning**:
   - the rating follows from the target and the firm's rating definitions (e.g. implied return against the threshold)
   - the target can be reproduced from the stated method and inputs; multiples and discount rates are stated and justified
   - forecasts tie between text, tables and model; changes from prior estimates are explained
   - the conclusion matches the body — no "Buy" on an analysis that reads neutral
4. **Read every sentence for language**:
   - promissory or absolute statements — "will", "guaranteed", "cannot lose", "sure to" — replace with supported expectation
   - exaggeration and superlatives without evidence
   - opinion presented as fact; fact without a source
   - disparaging or defamatory statements about a company or individual
   - statements that read as personal investment advice to the reader
5. **Check sources and information**:
   - every fact and figure attributed (company filings, data provider, the analyst's estimates) with dates
   - anything that looks like material non-public information — specific unreleased numbers, guidance "from management" not given publicly, knowledge of a pending transaction — is a stop: flag it and do not proceed to stylistic points
   - rumours and speculation about takeovers handled under policy
   - whether the draft was shared with the issuer, and if so only the factual sections, with no rating or target
   - third-party content used with permission and attribution
6. **Check fairness and balance**: bear case and risks given real weight; past recommendations not cherry-picked; charts not truncated to mislead; hypothetical or back-tested performance labelled.
7. **Report** findings by severity, each with the location and a proposed fix.

## Output format

```
## Verdict
Ready for supervisory review / needs changes first / STOP — possible MNPI or restricted-list issue

## Must fix before publication
| # | Location | Issue | Rule or standard | Suggested wording / action |

## Should fix
## Disclosures checklist
| Element | Present | Current | Note |

## Consistency checks (numbers, rating vs target)
## Questions for the analyst
## Checks this review could not perform
(restricted list, holdings, banking relationships, model audit — unless data was supplied)
```

## Rules

- Quote the exact phrase at issue and offer a replacement; "tone down page 4" is not a finding.
- Do not weaken a supported, strongly held view; the test is whether it is supported, not whether it is bold.
- Do not alter the analyst's rating, target or estimates. Flag inconsistencies and leave the decision to the analyst and the supervisory analyst.

## Limits

A pre-check. Approval to publish comes from the firm's supervisory analyst or compliance function, who have the restricted list, the conflict data and the applicable rulebook.
