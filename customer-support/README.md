# Customer Support

Triage tickets, draft responses, escalate issues, and build your knowledge base. Research customer context and turn resolved issues into self-service content.

## What's inside

### Skills

| Skill | What it does |
| --- | --- |
| `ticket-triage` | Classify a ticket by category, priority, and sentiment, and recommend a route (self-serve, agent, escalate). |
| `draft-response` | Draft an on-brand, accurate reply grounded in KB articles and the customer's history — you review before sending. |
| `escalation-packet` | Package an issue for engineering/product with repro, impact, and links; file it and notify the right channel. |
| `kb-article` | Turn a resolved ticket into a reusable self-service article — problem, solution, steps, related links. |
| `customer-context` | Assemble a 360° customer view: plan/tier, open + past tickets, account owner, recent activity. |

### Commands

| Command | What it does |
| --- | --- |
| `/customer-support:triage` | Runs **ticket-triage** on a ticket ID or pasted ticket. |
| `/customer-support:draft-reply` | Runs **draft-response** on a ticket ID or customer question. |
| `/customer-support:escalate` | Runs **escalation-packet** on a ticket ID or issue. |

## Connectors

These skills are tool-agnostic — they refer to tools by category (e.g. `~~helpdesk`, `~~knowledge base`) so any connected server in that category works. See **[CONNECTORS.md](CONNECTORS.md)** for the full mapping.

Categories used: `~~helpdesk`, `~~knowledge base`, `~~CRM`, `~~project tracker`, `~~chat`, `~~email`.

Everything works standalone too: paste a ticket or question into the chat and the skills run on that alone — connectors just add automatic lookups and context.

## Customize for your team
- Replace the **ticket categories** and **priority matrix** in `ticket-triage`.
- Paste your **tone guide, reply template, and never-promise rules** into `draft-response`.
- Set your **escalation thresholds, tracker fields, and channels** in `escalation-packet`.
- Add your **KB article template and PII-scrub list** in `kb-article`.
- Define your **VIP / at-risk criteria** in `customer-context`.

Look for `<!-- CUSTOMIZE: ... -->` markers throughout the skills for the exact spots to edit.
