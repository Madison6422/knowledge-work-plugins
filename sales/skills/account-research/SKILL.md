---
name: account-research
description: Deep-dive a target company before first contact — what they do, size, recent news, funding, leadership changes, likely pains, and who to talk to. Pulls from web research plus enrichment and CRM history when connected. Trigger with "research [company]", "give me a briefing on [account]", "who should I talk to at [company]".
---

# Account Research

Build a first-contact briefing on a target account so you walk in informed, not cold.

## What it does
Gathers a fast, structured picture of a company before your first touch: what they sell, how big they are, recent signals (funding, news, leadership moves, hiring), the pains your product likely solves for them, and the people worth reaching. It always works from public web research, and gets sharper when enrichment and CRM history are connected.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Data enrichment | `~~data enrichment` | Firmographics, headcount, tech stack, verified contacts and titles |
| CRM | `~~CRM` | Prior relationship history, open/closed deals, existing contacts and notes |

> **No connectors?** Fully usable from web research alone. Paste in a company name or URL and Claude assembles the briefing from public sources. Connectors mainly speed up firmographics and surface any history your team already has.

## How it works
1. Take the company name or URL you provide.
2. **Web research (always):** summarize what they do, market, approximate size, and recent news/funding/leadership signals from public sources.
3. **Connected — enrichment:** if `~~data enrichment` is available, confirm headcount, revenue band, tech stack, and pull candidate contacts with titles.
4. **Connected — CRM:** if `~~CRM` is available, check for prior deals, existing contacts, and past notes so you don't repeat a colleague's outreach.
5. Map likely pains to your offering and propose 2–4 people to talk to with a suggested angle for each.
<!-- CUSTOMIZE: describe your product and the 3–5 pains it solves, so "likely pains" maps to real value props -->

## Output
```markdown
# Account Briefing: <Company>
**What they do:** <one-liner> · **Size:** <headcount / revenue band> · **HQ:** <location>

## Recent signals
- <funding / news / leadership / hiring signal + date>

## Likely pains (mapped to us)
- <pain> → <our value prop>

## Who to talk to
| Name | Title | Why them | Angle |
| --- | --- | --- | --- |

## Existing history (CRM)
- <prior deals / contacts / notes, or "none found">

## Suggested first move
<channel + opening angle>
```

## Customize this skill
- Add your product summary and the pains it solves under step 5.
<!-- CUSTOMIZE: set your ICP — target size, industries, and disqualifiers -->
- Define which titles/personas you sell to so "who to talk to" ranks the right people.
- Note any research sources or compliance limits your team requires.

## Related skills
- **call-prep** — turn a briefing into a specific call plan.
- **draft-outreach** — write the first sequence grounded in this research.
- **competitive-battlecard** — prep for competitors already in the account.
