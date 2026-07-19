---
name: reconciliation
description: Reconcile an account (bank, AP, AR, or GL) against a source — match items, surface unmatched and aged items, and propose adjusting entries for a person to approve. Trigger with "reconcile the bank account for [period]", "run an AP reconciliation", "match GL to the subledger".
---

# Reconciliation

Match an account against its source, flag what doesn't tie out, and propose fixes a human can approve.

## What it does

Compares an account balance (bank, accounts payable, accounts receivable, or a GL account) against an independent source — a bank statement, subledger, vendor statement, or aging report. It matches items, lists what is unmatched or aged, and proposes adjusting entries to close the gap. Claude drafts; a person reviews and approves before anything is posted.

> **You approve before it goes out.** Proposed adjustments are drafts. No entry is posted to the books until a person reviews and approves it.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Data warehouse | `~~data warehouse` | Pulls the ledger balance and transaction-level detail for both sides, so matching runs against live book data instead of a paste |

> **No connectors?** Paste both sides — the account activity and the source statement — and Claude matches them line by line. Every matched and unmatched item is shown with the figures it came from.

## How it works

1. Identify the account and period, and the source to reconcile against.
2. **Connected:** pull the account's transaction detail and balance from `~~data warehouse`. **Standalone:** use the two lists you paste in.
3. Match items across the two sides by amount, date, and reference. Group clean matches; isolate the exceptions.
4. Surface unmatched items, timing differences, and aged items (e.g. outstanding more than 30/60/90 days). Show the balance impact of each.
5. Propose adjusting entries where a fix is clear (bank fees, missed accruals, duplicates). Recompute the reconciled balance so it ties to the source.
6. Present the reconciliation and proposed adjustments for a person to approve. Never invent a matching item or an amount — every figure is shown with its source.

<!-- CUSTOMIZE: set your aging buckets (e.g. 30/60/90/120) -->
<!-- CUSTOMIZE: define the materiality threshold below which small differences are written off -->

## Output

```markdown
## Reconciliation — Operating Bank, July 2026 (draft)
**Book balance:** 482,110.55 (source: GL 1010)
**Statement balance:** 486,340.55 (source: Bank stmt 07/31)
**Difference:** 4,230.00

**Matched:** 142 of 147 items (98.0% of value)

### Unmatched / aged
| Item | Amount | Age | Note |
|---|---:|---|---|
| Deposit in transit #DT-90 | 5,000.00 | 2 days | Timing — clears Aug |
| Bank service fee | (30.00) | — | Not yet booked |
| Check #1188 outstanding | (740.00) | 47 days | Stale — confirm with vendor |

### Proposed adjustment (for approval)
| Account | Debit | Credit |
|---|---:|---:|
| Bank Fees (6800) | 30.00 | |
| Cash — Operating (1010) | | 30.00 |

**Reconciled balance after adjustments:** 486,340.55 = statement. Ties.
> Review and approve before posting.
```

## Customize this skill

- Set your aging buckets and the materiality threshold for auto-write-offs.
- Name the accounts and sources you reconcile (bank, AP, AR, specific GL codes).
- Define who approves adjustments and how confirmed reconciliations are filed.

## Related skills

- `journal-entry` — draft the adjusting entries this skill proposes.
- `month-end-close` — reconciliations are core close tasks.
- `financial-statements` — clean, reconciled accounts feed the statements.
