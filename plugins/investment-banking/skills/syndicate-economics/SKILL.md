---
name: syndicate-economics
description: Compute how underwriting fees and expenses are split across a syndicate for an equity or bond offering — each bank's share of the gross spread, deal expenses and stabilisation result — from the syndicate terms. Use when the user asks for syndicate economics, fee split, league-table credit versus economics, a syndicate settlement statement, or how much each underwriter earns on a deal.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/ecm-dcm
  author: CorpSkill
  version: 0.1.0
---

# Syndicate Economics

Work out what each bank in the syndicate earns and owes at settlement. The agreement among the underwriters (and the mandate terms) decide the split; this skill applies them and shows the working.

Calculate in a spreadsheet or code. Every bank's net amount must reconcile to the total fee received from the issuer.

## Workflow

1. **Collect the terms**, with document references:
   - gross proceeds and gross spread (percentage or amount); any incentive or discretionary fee and who decides it
   - the fee structure:
     - *Equity (traditional)* — management fee, underwriting fee and selling concession, with their proportions; how the selling concession is credited (fixed economics, or "jump ball" where investors designate)
     - *Equity (fixed economics)* — a stated percentage per bank
     - *Bonds* — usually a single fee split by agreed percentages among bookrunners, with any co-manager fees and any praecipium to the lead
   - each bank's role, underwriting commitment and agreed share
   - over-allotment option: whether exercised and how much
   - syndicate expenses: legal, roadshow, travel, systems — which are reimbursed by the issuer and which are shared
   - stabilisation: who ran it, the profit or loss, and how it is shared
   - any retention, hold-back for expenses, or split of designations
2. **Compute the fee pool**: spread × gross proceeds, including the over-allotment amount if exercised; add any incentive fee awarded.
3. **Split each component** by its own rule: management fee by the agreed management percentages (lead may take a praecipium first); underwriting fee by underwriting commitment; selling concession by designation or fixed share.
4. **Allocate expenses**: deduct shared syndicate expenses, normally from the underwriting fee, pro rata to commitments, unless the terms say otherwise.
5. **Add the stabilisation result** by the agreed sharing.
6. **Produce each bank's statement**: gross fees by component, less expenses, plus or minus stabilisation, net due. Check that the banks' gross fees sum to the pool and the nets reconcile to cash.
7. **Show percentages two ways**: each bank's share of total economics, and — separately, because it differs — its bookrunner or league-table credit.

## Output format

```
## Terms applied
| Term | Value | Source |

## Fee pool
Gross proceeds × spread = [ ] (+ over-allotment) (+ incentive fee)

## Split by component
| Bank | Role | Management | Underwriting | Selling | Incentive | Gross fees | % of total |

## Expenses and stabilisation
| Bank | Share of expenses | Stabilisation P&L |

## Net settlement
| Bank | Gross fees | Expenses | Stabilisation | Net due | Check |

## Assumptions and open items
```

## Rules

- Do not assume a split. Typical proportions exist (for example 20 / 20 / 60 in a traditional equity structure), but each deal's terms govern; if a term is missing, ask and mark the placeholder.
- Keep designated selling credit separate from fixed shares; do not net them.
- Incentive fees are at the issuer's discretion until awarded — show the result with and without.
- Fee splits are commercially sensitive; share each bank's statement only with that bank.

## Limits

The lead manager's settlement statement is the official record. This skill prepares or checks it from the terms supplied.
