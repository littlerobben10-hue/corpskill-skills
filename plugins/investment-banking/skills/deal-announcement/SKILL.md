---
name: deal-announcement
description: Draft the announcement package for a signed M&A transaction — press release, internal and external Q&A, and messages for employees, customers and investors — from the signed terms. Use when a deal is about to be announced and the user asks for a press release, announcement plan, communications package, stakeholder Q&A or key messages.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/mna
  author: CorpSkill
  version: 0.1.0
---

# Deal Announcement

Prepare what gets said on announcement day, to whom, and in what order. Every audience hears the same facts; the emphasis changes.

Announcements of material transactions are regulated disclosure when a listed company is involved. This skill drafts; the company's lawyers and, where relevant, its listing adviser decide what must be disclosed, when, and through which channel.

## Workflow

1. **Collect the signed facts**: parties, what is being bought, price and form of consideration, how it is financed, conditions and expected closing date, approvals needed, what happens to management, brand, headquarters and employees, the stated rationale, advisers. Use only terms the user confirms are final and may be disclosed. Mark the rest `[NOT FOR DISCLOSURE]` or `[TO CONFIRM]`.
2. **Establish the constraints**: is either party listed (disclosure obligations, timing against market hours, trading halt)? Is there a works council or employee consultation that must happen before or at announcement? Any regulator to be told first? Any restriction on forward-looking statements or on communications because securities are being offered?
3. **Write the three key messages** — what is happening, why it makes sense, what changes and what does not. Everything else is built from these. If the rationale cannot be said in two sentences, go back to the user.
4. **Draft the press release** (format below).
5. **Draft the Q&A**, hardest questions first. Cover: price and valuation, job losses and site closures, management changes, customers' contracts and pricing, competition approval risk, financing and leverage, what happens if it does not close, why now. Answer each in two or three sentences. Where the honest answer is "not decided", say that and say when it will be.
6. **Draft audience messages**: employees of each company, customers, suppliers, investors / lenders. Each: what this means for you, what happens next, who to ask.
7. **Build the run sheet**: who is told what, by whom, at what time, in which order, with the approvals needed before each step.

## Press release format

```
[HEADLINE: Acquirer to acquire Target — one fact, no adjectives]
[Sub-headline: the main reason or the main number]

[City, date] — First paragraph: who, what, price or terms (if disclosed), expected timing.
Second paragraph: strategic rationale in concrete terms.
Quote — acquirer CEO.  Quote — target CEO or seller.
Transaction details: consideration, financing, conditions, approvals, expected closing.
What changes: leadership, brand, locations — as far as decided.
Advisers.
About [each company].
Contacts.
[Forward-looking statements and other legal notices — supplied by counsel]
```

## Rules

- Until closing, the companies remain separate. Write "will" and "expected to", subject to conditions; never describe the combined business as existing.
- No synergy, earnings or job numbers unless the company has decided to disclose them and counsel has cleared them.
- Internal and external versions must not contradict each other. Assume every internal message will be forwarded to a journalist.
- Employees should not learn from the press. The run sheet puts them at or before public release where disclosure rules allow.
- Quotes say something specific. Delete any quote that could be attached to a different deal unchanged.

## Output

Key messages · press release · Q&A (external and internal versions) · audience messages · run sheet · list of items awaiting confirmation or legal clearance.
