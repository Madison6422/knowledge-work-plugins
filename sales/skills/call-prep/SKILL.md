---
name: call-prep
description: Prepare for a specific sales call — account snapshot, attendee research, prior-touch history, a suggested agenda, discovery questions, and likely objections. Pulls from CRM, email, chat, conversation intelligence, and calendar when connected. Trigger with "prep me for my call with [company]", "get me ready for the [account] meeting", "call prep for tomorrow".
---

# Call Prep

Walk into any sales call with a one-page plan: who's in the room, what's happened so far, and what to ask.

## What it does
Assembles everything you need for a specific upcoming call — a quick account snapshot, research on each attendee, a recap of prior touches, a suggested agenda, discovery questions, and the objections you're most likely to hear. Works from what you paste in, and pulls history automatically when your tools are connected.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| CRM | `~~CRM` | Deal stage, contacts, notes, and next steps on record |
| Email | `~~email` | Prior threads and what was last promised |
| Chat | `~~chat` | Internal context from the deal channel |
| Conversation intelligence | `~~conversation intelligence` | Recaps and key moments from previous calls |
| Calendar | `~~calendar` | The meeting time, attendees, and invite context |

> **No connectors?** Paste the invite, the company name, and any notes, and Claude builds the plan from that plus web research. Connectors add prior-touch history and attendee detail you'd otherwise gather by hand.

## How it works
1. Identify the call from what you name, or from `~~calendar` if connected.
2. **Account snapshot:** pull a short profile (web research always; `~~CRM` adds deal stage and history).
3. **Attendee research:** for each person on the invite, note title, role in the deal, and a talking point.
4. **Prior touches:** summarize the last few interactions from `~~email`, `~~chat`, and `~~conversation intelligence` — what was said, what was promised.
5. **Build the plan:** suggested agenda, discovery questions tuned to their stage, and the top objections with a response for each.
<!-- CUSTOMIZE: set your sales stages and the discovery framework your team uses (MEDDIC, SPICED, etc.) -->

## Output
```markdown
# Call Prep: <Company> — <date/time>
**Attendees:** <names + titles> · **Deal stage:** <stage> · **Owner:** <rep>

## Snapshot
<2–3 lines on the account and where the deal stands>

## Prior touches
- <date> — <channel> — <what happened / what was promised>

## Suggested agenda
1. <item>

## Discovery questions
- <question tuned to their stage>

## Likely objections
| Objection | Response |
| --- | --- |
```

## Customize this skill
- Set your stage names and discovery framework under step 5.
<!-- CUSTOMIZE: list your 5–8 most common objections and the approved responses -->
- Add your standard agenda template for each call type (discovery, demo, negotiation).
<!-- CUSTOMIZE: note which meeting types this should trigger on -->

## Related skills
- **account-research** — deeper first-contact briefing on a new account.
- **pipeline-review** — decide which calls matter most this week.
- **competitive-battlecard** — arm up when a competitor is in the deal.
