---
name: committee-memo
description: Draft the internal approval memo an investment bank needs before taking on a mandate — engagement / commitment / new business committee. Use when the user describes a prospective M&A advisory, IPO, follow-on or bond mandate and asks for a committee memo, engagement approval paper, underwriting committee submission, or "what do I need to get this through committee".
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/mna
  author: CorpSkill
  version: 0.1.0
---

# Committee Memo

Write the paper a deal team submits to its internal committee to get permission to take a mandate. The reader is a senior banker or risk officer who has ten of these to read and wants to know three things: what are we being asked to do, what could go wrong for the firm, and is it worth it.

This is a firm-risk document, not a pitch. Do not sell the deal. A memo that hides a problem the committee later discovers costs the team far more than a memo that states it.

## Workflow

1. **Establish which committee and what is being asked.** The answer changes the memo:
   - *Advisory (M&A, restructuring)* — the firm puts reputation at stake, not capital. Focus: client, conflicts, fee, reputational risk, whether a fairness opinion is expected.
   - *Underwriting (IPO, follow-on, bonds)* — the firm may put capital and legal liability at stake. Add: underwriting commitment and size, due diligence plan, disclosure risk, market risk between launch and pricing.
   - *Committed financing* — the firm lends its balance sheet. Add: hold amount, syndication plan, flex terms, downside case.
   If the user has their firm's template, follow its headings and order exactly and use this skill only for content.
2. **Collect the facts.** Ask for whatever is missing from the list under "Inputs". Do not invent a fee, a valuation, an ownership structure or a conflict check result. Where a fact is unknown, write `[TO CONFIRM: …]` in place and list it again at the end.
3. **Work out the risks before drafting.** For each heading under "Risk review", decide whether it applies and how it is mitigated. A risk with no mitigant is still stated — with "none; accepted because …" or "open".
4. **Draft** using the structure below. Keep it to two or three pages. Numbers in a table, judgement in prose.
5. **Self-check** against the list at the end, then hand over with the open items.

## Inputs

- Client: legal name, jurisdiction, ownership, listed or private, who the firm's relationship is with and how long
- Counterparties known so far (target, buyer, selling shareholders, co-advisers, other underwriters)
- Transaction: type, expected size, structure, timetable, the firm's exact role (sole / joint, lead / co-, advisory only or with financing)
- Economics: retainer, success fee and its basis, underwriting spread, expense cap, tail period, minimum fee
- Team: senior sponsor, day-to-day lead, staffing
- Status of know-your-client, sanctions screening and conflict check
- Anything unusual: related parties, politically exposed persons, litigation, a hostile element, activist involvement, sensitive sector or jurisdiction

## Risk review

- **Conflicts** — other mandates or lending relationships with any party; principal positions; research coverage; staff with personal interests; whether an information barrier or consent is needed.
- **Client and reputation** — who ultimately owns and controls the client; source of wealth; press, regulatory or litigation history; would the firm be comfortable seeing its name next to this client on a front page.
- **Execution** — what has to happen for the deal to complete (financing, shareholder vote, regulatory and antitrust approvals, third-party consents) and the realistic chance it does not.
- **Legal and liability** — disclosure liability on an offering; fairness opinion exposure; indemnity from the client and whether it is worth anything.
- **Capital and market** (underwriting / financing only) — amount at risk, for how long, what protects the firm (market-out, flex, pricing range), the loss in a stated downside case.
- **Economics** — fee against the work and the risk; what the firm earns if the deal fails; any departure from standard terms.

## Output format

```
# [Committee name] — [Client] / [Project name]
Date · Sponsor · Deal team · Decision requested by [date]

## 1. Request
One paragraph: approval to act as [role] for [client] on [transaction], fee [summary].

## 2. Client and relationship
## 3. Transaction
Description, size, structure, timetable, our role and other advisers.

## 4. Economics
| Item | Terms | Standard? |
Expected fee, fee if not completed, expenses, tail.

## 5. Risk review
| Area | Issue | Mitigant | Status |
One row per applicable area above. Then two or three sentences on the risk that matters most.

## 6. Compliance status
KYC · sanctions · conflict check — each: cleared / pending / issue, with date.

## 7. Conditions and open items
What the team asks the committee to approve subject to; what is still to confirm.

## 8. Recommendation
```

## Self-check

- Could a committee member say what is being approved after reading only section 1?
- Is the worst realistic outcome for the firm stated in plain words, with a number where capital is at risk?
- Does every figure trace to something the user supplied? No assumed fees or sizes.
- Is every pending compliance item shown as pending rather than implied to be done?
- Has the pitch language been removed — "transformational", "marquee", "strong relationship" without evidence?

## Limits

This skill drafts the memo. It does not run the conflict check, the KYC or the sanctions screening, and it does not replace the firm's own template, legal review or the committee's judgement. Committee names, thresholds and required sections differ by firm and jurisdiction; ask rather than assume.
