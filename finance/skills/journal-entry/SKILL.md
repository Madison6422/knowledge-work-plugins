---
name: journal-entry
description: Prepare a balanced journal entry from source documents — accounts, debits and credits, a clear memo, and links to supporting evidence — ready for a person to review and post. Trigger with "draft a journal entry for [transaction]", "book this accrual", "create a JE from this invoice".
---

# Journal Entry

Turn a source document into a clean, balanced journal entry a human can review and post.

## What it does

Reads a transaction's source document (invoice, receipt, contract, payroll run, bank memo) and drafts the journal entry: the accounts to debit and credit, the amounts, a plain-language memo, and references back to the supporting evidence. Debits must equal credits before anything is shown. Claude drafts the entry; a person reviews and posts it.

> **You approve before it goes out.** Claude never posts to the ledger or any system of record. It produces a draft entry for a person to check and post.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Data warehouse | `~~data warehouse` | Pulls the chart of accounts, prior similar entries, and transaction detail so account codes and amounts come straight from the books |

> **No connectors?** Paste in the source document (or the numbers and account list) and Claude drafts the entry from that. Every figure it uses is quoted back with its source line so you can verify it.

## How it works

1. Take the source document or pasted details. Identify the transaction, date, amount, and currency.
2. **Connected:** query `~~data warehouse` for the chart of accounts and any prior entries for the same vendor or transaction type, so account codes match your books. **Standalone:** use the account list you provide, or ask for the codes it needs.
3. Determine the debit and credit lines. Confirm total debits equal total credits — if they don't balance, stop and flag the gap rather than force it.
4. Write a memo that states what the entry records and why, and attach a reference to each supporting document.
5. Present the draft for a person to review and post. Never invent an amount or an account — every number is shown with the source it came from.

<!-- CUSTOMIZE: list your standard account codes / chart-of-accounts ranges here -->
<!-- CUSTOMIZE: set your memo format and required support references (PO #, invoice #, contract ID) -->

## Output

```markdown
## Journal Entry — draft for review
**Date:** 2026-07-15  **Currency:** USD  **Source:** Invoice #4821 (Acme Supply)

| Account | Code | Debit | Credit |
|---|---|---:|---:|
| Office Supplies Expense | 6200 | 1,250.00 | |
| Accounts Payable — Acme | 2000 | | 1,250.00 |
| **Totals** | | **1,250.00** | **1,250.00** |

**Balanced:** yes (Dr 1,250.00 = Cr 1,250.00)
**Memo:** Record July office supply purchase, Acme Invoice #4821, net 30.
**Support:** Invoice #4821 (source doc); PO #779.

> Review and post. Amounts pulled from Invoice #4821; account codes from chart of accounts.
```

## Customize this skill

- Add your chart-of-accounts codes and naming so drafts match your ledger.
- Set the memo template and which support references are mandatory (PO, invoice, contract).
- Define approval routing — who reviews and posts entries, and any dollar thresholds that need a second sign-off.

## Related skills

- `reconciliation` — match an account against its source and propose adjusting entries.
- `month-end-close` — drive the close checklist that these entries feed into.
- `financial-statements` — assemble statements once entries are posted.
