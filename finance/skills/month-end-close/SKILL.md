---
name: month-end-close
description: Drive the month-end close — a checklist of tasks with owners and status, tie-outs, and a close packet assembled for review. Trigger with "run the month-end close for [period]", "build the close checklist", "where are we on close".
---

# Month-End Close

Coordinate the close: track tasks, owners, and status; run tie-outs; assemble the close packet.

## What it does

Runs the month-end (or period-end) close as a living checklist — every task with an owner, due point, and status — and drives it to completion. It tracks which reconciliations and entries are done, runs tie-outs across the ledger, chases open items via chat, and assembles the close packet for review. Claude coordinates and drafts; a person reviews and signs off the close.

> **A person signs off the close.** Claude tracks status and drafts the packet. It never marks the close complete or posts entries — a person reviews and approves before the books are locked.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Data warehouse | `~~data warehouse` | Reads ledger balances and status to run tie-outs and confirm which accounts are reconciled |
| Chat | `~~chat` | Posts status updates, pings owners on open tasks, and shares the close packet with the team |

> **No connectors?** Keep the checklist in the conversation — paste in status updates and balances, and Claude maintains the tracker, runs the tie-outs on what you provide, and drafts the packet. Every figure is shown with its source.

## How it works

1. Load the close checklist for the period — standard tasks (accruals, reconciliations, cutoff, intercompany, statements) each with an owner and status.
2. **Connected:** read balances and reconciliation status from `~~data warehouse`; post updates and nudge owners via `~~chat`. **Standalone:** update status from what the team pastes in.
3. Track each task through Not started → In progress → Done → Reviewed. Surface blockers and anything overdue.
4. Run tie-outs: subledgers agree to GL, intercompany nets to zero, statements tie. Flag any break with the two figures that disagree.
5. Assemble the close packet — checklist status, key reconciliations, tie-out results, draft statements and variance notes — for a person to review and sign off.
6. Never mark the close done or invent a status; every task's state and every figure traces to its source.

<!-- CUSTOMIZE: list your standard close tasks and their owners -->
<!-- CUSTOMIZE: set your close calendar / day targets (e.g. WD+3) and the tie-outs that must pass -->

## Output

```markdown
## Month-End Close — July 2026 (status as of WD+2)
Source: task status from team; balances from ledger.

| Task | Owner | Status | Note |
|---|---|---|---|
| Bank reconciliations | A. Lee | Reviewed | Ties |
| Accrue July payroll | R. Diaz | Done | JE #JE-4501, pending review |
| AR aging & reserve | M. Ford | In progress | Due WD+3 |
| Intercompany netting | A. Lee | Not started | Blocked on EU balances |
| Draft statements | — | Not started | After reconciliations |

**Tie-outs:** AP subledger = GL (ties). Intercompany — pending.
**Open blockers:** EU intercompany balances outstanding — pinged owner.

### Close packet (draft for sign-off)
- Checklist status (above)
- Key reconciliations + adjustments
- Draft P&L, balance sheet, cash flow
- Variance notes vs budget
> A person reviews and signs off before the books are locked.
```

## Customize this skill

- List your standard close tasks, owners, and the order they run in.
- Set your close calendar (working-day targets) and the required tie-outs.
- Define what goes in the close packet and who signs off.

## Related skills

- `reconciliation` — the reconciliations tracked on the checklist.
- `journal-entry` — draft accruals and adjustments the close requires.
- `financial-statements` — the statements assembled into the close packet.
- `variance-analysis` — the variance review that completes the packet.
