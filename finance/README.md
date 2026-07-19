# Finance

Streamline finance and accounting workflows, from journal entries and reconciliation to financial statements and variance analysis. Speed up audit prep, month-end close, and keeping your books clean.

Every skill drafts; a person reviews and approves before anything is posted to the books or a system of record. Numbers are always shown with their source — figures are never invented.

## What's inside

### Skills

| Skill | What it does |
|---|---|
| `journal-entry` | Prepare a balanced journal entry from source docs — accounts, debits/credits, memo, and support references — for a person to post |
| `reconciliation` | Reconcile an account (bank, AP, AR, GL) against a source: match items, surface unmatched/aged items, propose adjustments |
| `financial-statements` | Assemble draft P&L, balance sheet, and cash flow from ledger data with clean formatting and footnotes |
| `variance-analysis` | Compare actuals vs budget/prior period, recompute each variance, and explain the drivers; flag anything material |
| `month-end-close` | Drive the close: a checklist with owners and status, tie-outs, and a close packet for sign-off |

### Commands

| Command | What it does |
|---|---|
| `/finance:reconcile` | Runs `reconciliation` for an account and period |
| `/finance:variance-analysis` | Runs `variance-analysis` for a period vs a base |
| `/finance:close-checklist` | Runs `month-end-close` for a period |

## Connectors

See [CONNECTORS.md](CONNECTORS.md) for how tool references work and which servers are included. Categories used by this plugin: `~~data warehouse`, `~~chat`. Skills are tool-agnostic — they work standalone from what you paste in, and get better when a server in each category is connected.

## Customize for your team

- Add your chart of accounts, line-item groupings, and account mappings so drafts match your ledger.
- Set your materiality thresholds, aging buckets, and close-calendar day targets.
- Define approval routing — who reviews and posts entries, and any dollar thresholds needing a second sign-off.
- Edit the `<!-- CUSTOMIZE -->` marks in each skill for your terminology and templates.
- Swap the connected servers in `.mcp.json` for any others in the same category.
