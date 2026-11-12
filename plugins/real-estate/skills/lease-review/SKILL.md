---
name: lease-review
description: Review a commercial or residential lease and produce a structured abstract plus a risk list. Use when the user shares a lease, rental agreement, or LOI and asks to summarize it, find key terms (rent, term, escalations, renewal, CAM, assignment, termination), or flag risky clauses.
license: Apache-2.0
metadata:
  industry: real-estate
  scenario: leasing
  author: CorpSkill
  version: 0.1.0
---

# Lease Review

Turn a lease into (1) a lease abstract table and (2) a ranked risk list, citing the section for every fact.

## Workflow

1. **Identify the document.** Note parties (landlord, tenant, guarantor), premises, lease type (gross / modified gross / NNN), and whether it is residential or commercial. If pages or exhibits are missing, say so up front.
2. **Extract the abstract.** Fill every row below. Write `Not stated` instead of guessing. Always cite the section or page, e.g. `§4.2`.
3. **Flag risks.** Check each item in the risk checklist. Rank findings High / Medium / Low from the tenant's perspective unless the user says they represent the landlord.
4. **Compute the money.** Build a rent schedule for the full term including escalations and free-rent periods; state total base rent payable.
5. **Report** in the output format. Do not give legal advice; end by suggesting the user confirm High items with counsel.

## Abstract fields

| Field | Notes |
|---|---|
| Parties & guarantor | Full legal names |
| Premises | Address, suite, rentable / usable area |
| Term | Commencement, expiration, how commencement is triggered |
| Base rent | Amount, frequency, escalation method (fixed %, CPI, steps) |
| Free rent / TI allowance | Months, dollar amount, conditions |
| Operating expenses | Gross / NNN, CAM caps, base year, audit rights |
| Security deposit / LC | Amount, burn-down, return conditions |
| Renewal / expansion / ROFR | Notice windows, rent-setting method |
| Assignment & sublease | Consent standard, recapture, profit sharing |
| Termination & default | Early termination fees, cure periods, cross-default |
| Use & exclusivity | Permitted use, exclusives, co-tenancy |
| Maintenance & repairs | HVAC, roof, structure — who pays |
| Insurance & indemnity | Required coverage, waiver of subrogation |

## Risk checklist

- Uncapped or vaguely defined operating expenses / CAM
- Personal guarantee with no burn-off
- Landlord relocation right
- Short or missing cure periods for default
- Assignment consent "in landlord's sole discretion"
- Automatic renewal or evergreen clauses with short notice windows
- Holdover rent above 150%
- Restoration / removal obligations at lease end
- Mismatch between rent schedule and stated escalation
- Missing exhibits referenced in the body

## Output format

```
## Lease abstract — <premises>
<table of abstract fields with section citations>

## Rent schedule
<table: period | monthly rent | annual rent>; total base rent over term

## Risks (tenant view)
1. [High] <issue> — §x.x — <why it matters> — <suggested ask>
...

## Open questions
<anything missing or ambiguous>
```
