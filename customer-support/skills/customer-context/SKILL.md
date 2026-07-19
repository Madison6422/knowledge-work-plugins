---
name: customer-context
description: Assemble a 360° view of a customer before you respond — plan/tier, open and past tickets, account owner, and recent activity — pulled from your helpdesk, CRM, and chat. Trigger with "give me context on this customer", "who is this customer", "pull up this account before I reply".
---

# Customer Context

Know who you're talking to before you type a word.

## What it does
Builds a one-screen brief on a customer by pulling their plan/tier and account owner from your ~~CRM, their open and past tickets from your ~~helpdesk, and any recent internal discussion from ~~chat. The result tells an agent how much the account matters, what they've dealt with before, and who owns the relationship.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Helpdesk | `~~helpdesk` | Open + past tickets, recurring issues, and contact history |
| CRM | `~~CRM` | Plan/tier, account value, renewal date, and account owner |
| Chat | `~~chat` | Recent internal mentions — known issues, VIP flags, past escalations |

> **No connectors?** Paste what you know — company name, email, plan, and any prior ticket text. Claude organizes it into the same brief; it just can't fetch what you don't provide.

## How it works
1. **Identify the customer.** Match by email or account name across ~~helpdesk and ~~CRM.
2. **Pull account facts.** Plan/tier, seats, renewal date, and account owner from ~~CRM.
<!-- CUSTOMIZE: list the CRM fields that matter most to your team (MRR, health score, renewal) -->
3. **Summarize ticket history.** Open tickets, recent resolved ones, and any recurring theme from ~~helpdesk.
4. **Check internal chatter.** Search ~~chat for recent mentions — known bugs, VIP notes, or a live escalation.
5. **Flag what matters.** Surface anything that should change how you respond: at-risk renewal, repeat issue, VIP, or an open escalation.
<!-- CUSTOMIZE: define your VIP / at-risk criteria (tier, MRR threshold, renewal window) -->

## Output
```markdown
**Customer:** Dana Ruiz — Northwind Co.
**Plan:** Pro (25 seats) · Renews in 38 days · Owner: Priya (AE)
**Value:** $18k ARR · Health: watch (2 escalations this quarter)

**Open tickets (2)**
- #4821 Export fails on large reports — P2, escalated to eng
- #4830 SSO login loop — awaiting customer reply

**Recent history**
- 3 tickets in 30 days, all export/reporting related — recurring theme
- Last CSAT: 3/5

**Internal notes (~~chat)**
- #eng-triage: export timeout is a known regression from v3.4.1

⚠️ Handle with care: renewal is close and this is a repeat issue. Lead with ownership.
```

## Customize this skill
- List the **CRM fields** your team cares about in step 2.
- Define **VIP / at-risk criteria** in step 5.
- Point step 4 at the **chat channels** where support and eng discuss customers.

## Related skills
- **ticket-triage** — feed tier and history into the priority call.
- **draft-response** — write a reply informed by this context.
- **escalation-packet** — attach account value when escalating.
