# Productivity

Manage tasks, plan your day, and build up memory of important context about your work. Syncs with your calendar, email, and chat to keep everything organized and on track.

## What's inside

### Skills

| Skill | What it does |
|---|---|
| `daily-brief` | Morning brief: today's calendar, top priorities, overdue tasks, unread items needing a reply, and one suggested focus. |
| `task-triage` | Collect open action items from chat, email, and your project tracker; dedupe, prioritize, and propose a ranked to-do list with owners and due dates. |
| `meeting-notes` | Turn raw notes or a transcript into clean minutes — decisions, action items, open questions — and file tasks into your project tracker. |
| `personal-memory` | Keep a durable memory of your projects, people, and preferences so Claude stops re-asking. |
| `weekly-review` | End-of-week roll-up: what shipped, what slipped, next week's priorities, and what's waiting on others. |

### Commands

| Command | What it does |
|---|---|
| `/productivity:plan-day` | Runs `daily-brief` for today. Optional date or focus. |
| `/productivity:catch-up` | Summarizes what you missed across chat and email since a given time. |
| `/productivity:remember` | Appends a fact to your `personal-memory` file. |

## Connectors

This plugin is tool-agnostic — it refers to tools by category (`~~calendar`, `~~email`, `~~chat`, `~~project tracker`, `~~knowledge base`) so any MCP server in that category works. See **[CONNECTORS.md](./CONNECTORS.md)** for the full mapping and the servers pinned in `.mcp.json`.

Every skill works standalone: paste in your agenda, tasks, or threads and it does the same job. Connectors just make it automatic and complete.

## Customize for your team

- Replace the `~~category` placeholders' behavior by editing each skill's **How it works** steps.
- Search for `<!-- CUSTOMIZE -->` marks — each flags a spot to add your terminology, thresholds, or defaults (what "urgent" means, who owns unassigned tasks, your minutes template, the memory file path).
- Set your default channels, boards, and week boundaries in the skills that post or file items.
- Tighten the human-approval notes to match your policy for external sends and task creation.
