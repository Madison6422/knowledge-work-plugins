---
name: ticket-triage
description: Classify an incoming support ticket by category, severity/priority, and sentiment, then recommend a route — self-serve, agent, or escalate — after checking the knowledge base for an existing answer. Trigger with "triage this ticket", "what priority is this", "how should I route this ticket".
---

# Ticket Triage

Turn a raw incoming ticket into a clear, routed classification in seconds.

## What it does
Reads a support ticket — pasted in or pulled from your ~~helpdesk — and classifies it four ways: category, severity/priority, customer sentiment, and recommended route. It checks your ~~knowledge base first so tickets with a known answer are flagged for self-serve or a quick canned reply instead of burning agent time.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Helpdesk | `~~helpdesk` | Pulls the ticket, its conversation history, tags, and the customer record |
| Knowledge base | `~~knowledge base` | Finds existing articles that already answer the question |
| CRM | `~~CRM` | Adds plan/tier so priority reflects account value |

> **No connectors?** Paste the ticket text (and any customer detail you have) directly into the chat. Claude classifies it and drafts the routing call from the content alone — you just won't get automatic KB matches or account context.

## How it works
1. **Get the ticket.** Connected: pull it from ~~helpdesk by ID, including the full thread and tags. Standalone: use the text pasted into the chat.
2. **Classify the category.** Map to your team's ticket categories (billing, bug, how-to, feature request, outage, account/access, other).
<!-- CUSTOMIZE: replace with your actual ticket categories -->
3. **Score severity/priority.** Weigh customer impact, scope (one user vs. many), and account tier from ~~CRM against your priority matrix.
<!-- CUSTOMIZE: set your P1–P4 thresholds and what counts as "urgent" -->
4. **Read sentiment.** Flag frustrated, at-risk, or churn-signal language so agents can respond with the right tone.
5. **Check the ~~knowledge base.** Search for articles that answer the question. If a strong match exists, note it for a self-serve or canned response.
6. **Recommend a route.** Self-serve (KB link), agent (normal queue), or escalate (needs engineering/product) — with a one-line reason.

## Output
```markdown
**Ticket:** #4821 — "Export keeps failing on large reports"
**Category:** Bug
**Priority:** P2 (multiple users affected, Pro tier)
**Sentiment:** Frustrated — second contact this week
**KB match:** "Troubleshooting export timeouts" (85% match)
**Route:** Agent — likely known issue; confirm against KB, then escalate if repro differs
**Why:** Impacts a paying account; existing article covers the common cause but not large-report timeouts.
```

## Customize this skill
- Edit the **category list** in step 2 to match your team's taxonomy.
- Set your **priority matrix** (P1–P4 definitions and tier weighting) in step 3.
- Adjust the **sentiment flags** and routing rules for how your queue is staffed.

## Related skills
- **draft-response** — write the reply once a ticket is routed to an agent.
- **escalation-packet** — package a ticket that needs engineering or product.
- **customer-context** — pull the full account picture before responding.
