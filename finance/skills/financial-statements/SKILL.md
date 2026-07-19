---
name: financial-statements
description: Assemble draft financial statements — P&L, balance sheet, and cash flow — from ledger data with clean formatting and footnotes, ready for a person to review. Trigger with "draft the P&L for [period]", "build a balance sheet", "assemble financial statements for the quarter".
---

# Financial Statements

Turn ledger data into clean, footnoted draft statements a human can review and finalize.

## What it does

Assembles the three core statements — income statement (P&L), balance sheet, and cash flow — from ledger balances. It groups accounts into standard line items, formats them for readability, checks that the statements tie (balance sheet balances, cash flow reconciles to cash), and adds footnotes for anything that needs explanation. Claude drafts; a person reviews and finalizes.

> **You approve before it goes out.** These are draft statements for internal review, not filed or distributed financials. A person reviews before anything is shared externally.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Data warehouse | `~~data warehouse` | Pulls trial-balance and account-level detail so line items are built from live ledger data with drill-down support |

> **No connectors?** Paste in the trial balance or account balances and Claude builds the statements from that. Every line item shows which accounts roll into it.

## How it works

1. Confirm the entity, period, and basis (accrual/cash) and which statements are needed.
2. **Connected:** pull the trial balance and account detail from `~~data warehouse`. **Standalone:** use the balances you paste in.
3. Map accounts into standard line items (revenue, COGS, opex; assets, liabilities, equity; operating/investing/financing cash flows). Show a prior-period column where available.
4. Run the tie-out checks: assets = liabilities + equity; net income flows to retained earnings; cash flow ending cash matches the balance sheet.
5. Add footnotes for material items, unusual movements, and any assumptions. Flag anything that doesn't tie rather than plugging it.
6. Present the drafts for review. Never invent a balance — every line traces to the accounts that feed it.

<!-- CUSTOMIZE: set your statement line-item groupings and account mappings -->
<!-- CUSTOMIZE: list your standard footnotes and disclosure language -->

## Output

```markdown
## Income Statement — draft (source: trial balance 07/31/2026)
| Line item | Jul 2026 | Jun 2026 |
|---|---:|---:|
| Revenue | 1,240,000 | 1,180,000 |
| Cost of goods sold | (496,000) | (472,000) |
| **Gross profit** | **744,000** | **708,000** |
| Operating expenses | (520,000) | (505,000) |
| **Operating income** | **224,000** | **203,000** |

## Balance Sheet — draft
| | Jul 2026 |
|---|---:|
| Total assets | 8,410,000 |
| Total liabilities | 3,180,000 |
| Total equity | 5,230,000 |
| **Check: A = L + E** | **ties (8,410,000)** |

**Footnotes**
1. Revenue up 5.1% MoM; driven by [segment] — see variance-analysis.
2. Opex includes one-time [item] of 18,000.
> Draft for review. All figures from the 07/31 trial balance.
```

## Customize this skill

- Set your line-item groupings and how accounts map into each.
- Add your standard footnote and disclosure language.
- Define the review path — who signs off before statements are shared.

## Related skills

- `variance-analysis` — explain the period-over-period movements shown here.
- `reconciliation` — ensure accounts tie before statements are built.
- `month-end-close` — statements are the output of a completed close.
