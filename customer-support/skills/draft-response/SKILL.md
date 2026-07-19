---
name: draft-response
description: Draft an on-brand, accurate reply to a customer, grounded in your knowledge base articles and the customer's helpdesk history. Claude drafts; the agent reviews and edits before sending. Trigger with "draft a reply to this ticket", "help me respond to this customer", "write a response".
---

# Draft Response

Write a customer-ready reply that's accurate, on-brand, and grounded in real sources.

## What it does
Drafts a reply to a customer question using your ~~knowledge base for the facts and the customer's ~~helpdesk history for context, so the answer fits their situation and doesn't repeat what they've already tried. Every draft is a starting point — the agent reviews, edits, and sends.

> **You approve before it goes out.** Claude never sends. It produces a draft in the chat (or as a helpdesk note); a human reads it, edits it, and hits send.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Knowledge base | `~~knowledge base` | Grounds the answer in approved articles so facts and steps are correct |
| Helpdesk | `~~helpdesk` | Reads the ticket thread and past tickets so the reply fits the customer's history |
| CRM | `~~CRM` | Adds plan/tier so the reply reflects what the customer actually has access to |

> **No connectors?** Paste the customer's question plus any relevant article text or prior messages. Claude drafts from what you give it — just verify facts yourself, since it can't reach your KB.

## How it works
1. **Read the question.** Connected: pull the ticket thread from ~~helpdesk. Standalone: use the pasted question.
2. **Ground the facts.** Search the ~~knowledge base for the relevant article(s) and base the answer on them. Cite the article so the agent can verify.
3. **Add context.** Check ~~helpdesk history and ~~CRM tier so the reply doesn't suggest something they've tried or a feature they don't have.
4. **Draft in your voice.** Match your brand tone and reply template — greeting, acknowledgment, answer, clear next step, sign-off.
<!-- CUSTOMIZE: paste your tone guide and reply template (greeting, structure, sign-off) -->
5. **Flag any gaps.** If the KB doesn't cover it, say so plainly rather than guessing — mark it for escalation or a KB article.
<!-- CUSTOMIZE: set your rule for what must never be promised without approval (refunds, dates, legal) -->
6. **Hand off for review.** Output the draft for the agent to edit and send.

## Output
```markdown
**Reply draft — Ticket #4821**
_Grounded in: "Troubleshooting export timeouts" · Customer on Pro tier_

Hi Dana,

Thanks for flagging this — sorry the export has been getting in your way.

Large reports can time out when they exceed the current export size limit. Two things
that usually fix it:
1. Filter the report to a shorter date range, then export in batches.
2. Switch the format to CSV, which processes faster than PDF for big datasets.

If it still fails after that, reply here and I'll pull in our engineering team with the
exact report so we can dig in.

Best,
[Agent name]

---
⚠️ Review before sending: confirm the size-limit number against the current KB article.
```

## Customize this skill
- Paste your **tone guide and reply template** in step 4.
- Set the **never-promise-without-approval** rules (refunds, timelines, legal) in step 5.
- Point step 2 at the **KB spaces** your team treats as source of truth.

## Related skills
- **ticket-triage** — classify and route before drafting.
- **customer-context** — pull the full account picture first.
- **kb-article** — turn the resolved answer into a reusable article.
