---
description: Triage a support ticket — category, priority, sentiment, and route.
argument-hint: "[ticket id or pasted ticket]"
---

# Triage

Runs the **ticket-triage** skill to classify and route an incoming ticket.

## Instructions
1. Take the ticket from `$ARGUMENTS` — a ~~helpdesk ticket ID to pull, or pasted ticket text to use as-is.
2. Run the **ticket-triage** skill: classify category, severity/priority, and sentiment, and check the ~~knowledge base for an existing answer.
3. Recommend a route — self-serve, agent, or escalate — with a one-line reason.
4. If the ticket looks like an escalation, suggest running `/customer-support:escalate` next.
