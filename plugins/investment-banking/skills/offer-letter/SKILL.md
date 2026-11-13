---
name: offer-letter
description: Draft a non-binding offer for an acquisition — an indication of interest (IOI) in a first round or a letter of intent (LOI) — from agreed terms and the seller's process letter. Use when the user asks for an IOI, LOI, non-binding offer, first-round bid letter or indicative proposal for a company or asset.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/mna
  author: CorpSkill
  version: 0.1.0
---

# Offer Letter (IOI / LOI)

Write the letter a bidder sends to say what it would pay and on what basis. A good one answers every question the seller's process letter asks, makes the bidder look certain to close, and commits the bidder to as little as possible.

## Workflow

1. **Identify which letter.** An *indication of interest* is a first-round bid in an auction: short, a value range is acceptable, based on limited information. A *letter of intent* comes later or in a bilateral deal: one price, more terms, often asks for exclusivity. Ask if unclear.
2. **Read the process letter**, if there is one, and list every item it asks bidders to address. The reply follows that list in that order; a missing item reads as evasion.
3. **Collect the terms from the user**: bidder entity; price or range and what it is a price for (enterprise value on a cash-free, debt-free basis with normal working capital, or equity value); form of consideration; valuation basis and key assumptions; financing sources and status; diligence still required and time needed; approvals (internal, shareholder, regulatory); plans for management and employees; conditions; exclusivity sought; timetable; contacts and advisers. Do not supply a price or a financing status yourself.
4. **Draft** with the structure below.
5. **Mark the binding / non-binding split explicitly.** The offer is non-binding. Only the clauses named as binding are — normally confidentiality, exclusivity, costs, governing law.
6. **Review for accidental commitment** and for anything that weakens the bid without protecting the bidder.

## Structure

```
1. Introduction — who the bidder is, why it is a credible and motivated buyer (two or three sentences)
2. Purchase price — amount or range; basis (cash-free / debt-free, normalised working capital); form of consideration
3. Valuation basis and assumptions — the information relied on; what would change the price
4. Financing — sources; status; whether the offer is conditional on financing
5. Due diligence — remaining scope, advisers, time required
6. Approvals and conditions — internal, regulatory, third-party; expected timing
7. Management and employees
8. Transaction structure and key contract terms (LOI) — share or asset deal, key protections expected
9. Timetable to signing
10. Exclusivity (LOI) — period requested
11. Non-binding nature — and the list of binding clauses
12. Confidentiality · contacts
```

## Drafting rules

- State the price basis precisely. "USD 500 million" means nothing until the reader knows whether it is enterprise or equity value and what is assumed about cash, debt and working capital.
- A range in an IOI should be narrow enough to be taken seriously; the seller will read the bottom of it.
- Sellers rank bids on price and on certainty. Give specifics on financing, approvals and diligence scope rather than assurances.
- Conditions should be few and concrete. "Subject to satisfactory due diligence" is expected; a long list signals a bidder looking for exits.
- Avoid language that could be read as acceptance of terms or an agreement to agree: use "would", "proposes", "subject to contract".
- Keep an IOI to two or three pages; an LOI as long as its terms need.

## Output

The letter, followed by: a table mapping each process-letter request to where it is answered; the terms still marked `[TO CONFIRM]`; and points to raise with counsel (exclusivity wording, binding clauses, any disclosure obligation the offer may trigger for a listed bidder or target).

## Limits

A draft for the deal team and its lawyers. Whether a letter is binding depends on its wording and the governing law; counsel must review before it is sent.
