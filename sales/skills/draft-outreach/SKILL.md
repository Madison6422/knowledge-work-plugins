---
name: draft-outreach
description: Write a personalized outreach sequence — a first email plus follow-ups — grounded in real account context instead of generic templates. You approve every message before anything sends. Pulls from enrichment, CRM, and sales engagement when connected. Trigger with "draft outreach to [prospect]", "write a sequence for [account]", "write me a cold email to [company]".
---

# Draft Outreach

Turn account context into a personalized, multi-step outreach sequence you can review and send.

## What it does
Writes a first-touch email and a short follow-up sequence that reference real, specific details about the prospect — not filler. It grounds each message in enrichment and CRM context when available, and can hand the approved sequence to your sales engagement tool. **You approve before anything sends.**

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Data enrichment | `~~data enrichment` | Verified contact details, role, and personalization hooks |
| CRM | `~~CRM` | Deal history and prior contact so messaging fits the relationship |
| Sales engagement | `~~sales engagement` | Load the approved sequence into a cadence to schedule sends |

> **No connectors?** Paste in the prospect's name, company, and any context, and Claude writes the full sequence as copy you can send by hand. Connectors add personalization detail and let you push an approved sequence into a cadence.

## How it works
1. Take the prospect or account and any context you provide.
2. **Gather hooks:** pull personalization detail from web research, `~~data enrichment`, and `~~CRM` history.
3. **Draft the sequence:** a first email plus 2–4 follow-ups, each with a distinct angle and a clear call to action.
<!-- CUSTOMIZE: set sequence length, cadence spacing, and tone/voice for your team -->
4. **Review together:** show the full sequence for your edits.
5. **You approve before it goes out.** Only after you say so does anything move to `~~sales engagement`; otherwise it stays as copy for you to send.

## Output
```markdown
# Outreach Sequence: <Prospect> @ <Company>
**Personalization hooks:** <2–3 specifics used>

## Email 1 — <angle> (Day 0)
**Subject:** <subject>
<body>

## Email 2 — <angle> (Day 3)
**Subject:** <subject>
<body>

## Email 3 — <angle> (Day 7)
...

> Draft only — nothing sends until you approve.
```

## Customize this skill
- Set sequence length, cadence timing, and voice under step 3.
<!-- CUSTOMIZE: paste 1–2 of your best-performing emails as style references -->
- Add required disclaimers, opt-out language, or compliance rules for external sends.
<!-- CUSTOMIZE: define who must approve before a sequence is loaded into a cadence -->

## Related skills
- **account-research** — gather the context this sequence is built on.
- **call-prep** — prep the call once a prospect replies.
- **pipeline-review** — see which prospects need a follow-up nudge.
