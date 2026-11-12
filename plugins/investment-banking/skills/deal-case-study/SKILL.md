---
name: deal-case-study
description: Turn a completed transaction into a one-page case study (credential) for use in future pitches. Use when the user says a deal has closed or priced and asks for a case study, credential slide, tombstone text, deal write-up or "lessons learned" — for M&A, IPOs, bond issues or structured transactions.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/pitch
  author: CorpSkill
  version: 0.1.0
---

# Deal Case Study

Write the one-page account of a finished deal that goes into the credentials section of the next pitch. Its job is to make a prospective client think "they solved a problem like mine". A list of deal facts does not do that; a short story of problem, approach and result does.

Two versions come out of the same facts: an **external credential** that may be shown to clients, and an **internal note** on what the team learned. Keep them separate. Nothing from the internal note goes into the external one.

## Workflow

1. **Check what may be said.** Before writing, ask:
   - Has the deal been publicly announced? If not, stop at an internal note.
   - Which terms are public (value, multiple, pricing, counterparties)? Only public terms, or terms the client has approved for disclosure, go in the external version.
   - Does the engagement letter allow the firm to cite the deal and use the client's name and logo?
   Mark anything unconfirmed as `[CHECK DISCLOSURE]` rather than leaving it out silently or putting it in.
2. **Collect the facts** listed under "Inputs". Take numbers from the announcement, the final terms or the pricing sheet, not from memory of the pitch. If two sources differ, ask.
3. **Find the angle.** In one sentence: what was difficult here, and what did the team do about it? Examples: a carve-out with no standalone accounts; a volatile window for pricing; a single credible buyer who needed competitive tension; a first-time issuer. If the user cannot name a difficulty, the case study will read as a tombstone — say so and offer the tombstone format instead.
4. **Write the external credential** in the format below. Past tense, plain verbs, numbers with units and dates.
5. **Write the internal note.** What worked, what did not, what to do differently, who the useful contacts were.
6. **Suggest where it fits**: which client situations and which sector or product pitches this credential supports.

## Inputs

- Client, counterparty, the firm's role (sole / joint, sell-side / buy-side, bookrunner / co-manager)
- Dates: mandate, announcement or launch, signing or pricing, closing or settlement
- Size and the headline terms that are public
- Result measures, by deal type:
  - *M&A* — value, multiple, premium to undisturbed price, number of parties contacted / bids received, time from launch to signing
  - *IPO / follow-on* — size, pricing against the range, times covered, quality of the book, trading after one day and one month
  - *Bonds* — size, tenor, coupon, spread at pricing against initial guidance, book size, new issue concession
  - *Structured* — the client's objective, the structure in one line, the economic result against the alternative
- The client's situation and objective at the start
- What the team did that mattered

## Output format

```
# [Client] — [what happened, in under twelve words]
[Month Year] · [Firm's role] · [Size]

**Situation.** Two or three sentences: who the client is, what they wanted, why it was not straightforward.

**What we did.** Three bullets at most. Each one an action and its reason, not a job title or a process step.

**Result.** Two or three numbers that show the outcome against a reference point
(the range, the guidance, the undisturbed price, the prior round, the alternative).

**Why it matters for you.** One sentence that generalises — the kind of client this applies to.

---
Tombstone line: [Client] · [Transaction] · [Size] · [Role] · [Month Year]
```

Then, separately and clearly labelled **Internal — not for clients**:

```
- What worked
- What did not, and why
- What we would do differently
- Contacts and counterparties worth remembering
- Useful for pitching: [situations / sectors / products]
```

## Rules

- A result needs a reference point. "Priced at 4.25%" tells the reader nothing; "priced 15 bp inside initial guidance" does.
- Do not claim credit for what the market did. If the window was simply good, say what the team did to use it.
- Do not disparage the counterparty, other advisers or the client's earlier decisions, in either version.
- No superlatives without a source ("largest", "first", "record"). If the claim is sourced, name the source and the date.
- Keep the external version to one page, roughly 150–200 words.

## Limits

This skill writes from the facts supplied. It cannot verify what is public or what the engagement letter permits; the deal team and compliance decide what may be shown to clients.
