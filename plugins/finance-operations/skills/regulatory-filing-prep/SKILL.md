---
name: regulatory-filing-prep
description: Prepare a periodic regulatory filing for a financial institution — assemble the data, map it to the form, reconcile it and document the checks before sign-off. Use when the user has a recurring regulatory return due (fund, bank or insurer reporting to a supervisor) and asks for a filing checklist, data mapping, reconciliation, variance explanations, or a review pack for the person signing.
license: Apache-2.0
metadata:
  industry: finance
  scenario: am/ops
  author: CorpSkill
  version: 0.1.0
---

# Regulatory Filing Prep

Get a recurring regulatory return from "the deadline is in two weeks" to a pack the accountable person can sign. The work is the same whatever the form: know exactly what is asked, trace every reported figure to a source, reconcile it to the books, explain what moved, and leave a record of all of it.

Supervisors forgive a late question more easily than a wrong number. When a figure cannot be supported, say so in the pack.

## Workflow

1. **Identify the filing precisely.** Name of the return, the supervisor, the reporting entity or entities, reporting date, due date, frequency, and the version of the form and instructions in force for this period. Ask the user for the current instructions or the link to them; do not rely on recollection of field definitions, thresholds or deadlines — they change, and you may be out of date.
2. **List what changed since last time**: new instruction version, new products or entities, restructurings, system migrations, changes in accounting policy, findings from the last review. Each one is a place where last period's method may now be wrong.
3. **Build the data map.** One row per reported field: the definition in the instructions, the source system or report, the transformation applied, the owner, and whether it is direct, derived or a manual estimate.
4. **Pull and reconcile.** Tie totals to the general ledger, the fund accounting records or the audited financial statements for the same date. Every reconciling difference is either explained and documented or open.
5. **Run the checks** below and record the result of each.
6. **Explain movements.** Compare to the prior period and to expectation; write a short cause for each movement above the threshold the user sets (ask; suggest 10% and a monetary floor if they have none).
7. **Assemble the review pack** and the list of open items for the signer.

## Checks

- **Completeness** — every required field populated; every entity, fund, branch and portfolio in scope included; nothing excluded without a documented reason.
- **Internal consistency** — subtotals sum; figures that appear in more than one schedule agree; the form's own validation rules pass.
- **External consistency** — agrees with the ledger, the financial statements and other returns filed for the same date; differences explained by definition, not left as noise.
- **Reasonableness** — movements make sense given what happened in the business; ratios within plausible ranges; no sign errors or unit errors (thousands against units, percentage against decimal).
- **Definitions** — each classification (counterparty type, asset class, maturity bucket, currency, jurisdiction) follows the instructions rather than the internal label with a similar name.
- **Thresholds** — recheck any size or activity threshold that decides which sections or which frequency applies.
- **Manual items** — every manual adjustment or estimate has an owner, a method and evidence.
- **Prior issues** — every finding or supervisor query from previous periods confirmed fixed.

## Output format

```
# [Return name] — [Entity] — period ending [date]
Due [date] · Instructions version [x] · Preparer · Reviewer · Signer

## 1. Changes since last filing
## 2. Data map
| Field | Definition (ref.) | Source | Transformation | Type | Owner |

## 3. Reconciliation
| Reported total | Books and records | Difference | Explanation | Status |

## 4. Check results
| Check | Result | Evidence | Exceptions |

## 5. Movement analysis
| Field | Prior | Current | Change | Cause |

## 6. Judgements and estimates
What was estimated, how, and why that method.

## 7. Open items
| Item | Impact if unresolved | Owner | Due |

## 8. Sign-off
Preparer / reviewer / accountable signer, with dates.
```

Also produce a dated timeline working back from the due date: data cut-off, reconciliation complete, review, sign-off, submission, with a buffer for portal or validation failures.

## Rules

- Never fill a field with a placeholder that could be mistaken for a real value. Use an explicit `OPEN` marker and carry it into section 7.
- Keep the previous period's method unless something in step 2 requires a change; when the method changes, say so in section 6 and consider whether prior filings need correcting.
- If an error in a previously filed return is found, raise it immediately and separately — it is a decision for compliance, not something to net off in this period.

## Limits

This skill organises and checks the preparation. It does not know the current instructions for any particular return; it works from the instructions the user provides. Interpretation of the rules, the decision to file, and any resubmission or notification to the supervisor belong to the firm's compliance function and the accountable signer.
