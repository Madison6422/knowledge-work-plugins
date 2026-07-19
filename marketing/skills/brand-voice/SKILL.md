---
name: brand-voice
description: Check a draft against the team's brand voice and messaging guidelines — flag off-tone lines, banned words, and weak phrasing, then suggest on-brand fixes. Works from a pasted voice note alone and gets sharper when the voice guide is connected. Trigger with "brand-check this draft", "does this sound like us", "make this on-brand".
---

# Brand Voice

Review a draft line by line and flag anything that doesn't sound like your team.

## What it does
Reads a draft you paste (or point to) and compares it against your brand voice and messaging guidelines. It flags off-tone lines, banned or off-limits words, jargon, and weak phrasing, then rewrites each flagged line in your voice. It works from a short voice description you paste, and gets much sharper when the full voice guide is connected.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Knowledge base | `~~knowledge base` | The voice guide, tone attributes, banned-word list, and messaging pillars |

> **No connectors?** Fully usable. Paste your draft plus a few lines describing your voice (tone, do's/don'ts) and Claude checks against that. Connecting the knowledge base lets it use the real voice guide instead.

## How it works
1. Take the draft you paste or point to.
2. **Connected — knowledge base:** if `~~knowledge base` is available, load the voice guide, tone attributes, and banned-word list.
<!-- CUSTOMIZE: point to your voice guide location and paste your top tone attributes (e.g. plain, warm, confident, no hype) -->
3. **Standalone:** if not connected, use the voice notes you paste as the rubric.
4. Scan the draft line by line for off-tone phrasing, banned words, jargon, and hype.
<!-- CUSTOMIZE: list banned words and phrases (e.g. "revolutionary", "synergy", "cutting-edge") -->
5. Return each flagged line with the issue and an on-brand rewrite, plus an overall on-tone read.

## Output
```markdown
# Brand Voice Check
**Overall:** <on-brand / needs work> · **Flags:** <count>

## Flagged lines
| Original | Issue | Suggested rewrite |
| --- | --- | --- |

## Notes
- <pattern to watch, e.g. too many passive sentences / off-tone CTA>
```

## Customize this skill
- Paste your tone attributes so checks match your real voice.
<!-- CUSTOMIZE: set severity — which flags block publishing vs. which are just suggestions -->
- Maintain your banned-word and preferred-phrase lists.
- Note any words you require (product names, trademark styling).

## Related skills
- **content-draft** — draft new copy that starts on-brand.
- **campaign-plan** — keep messaging consistent across every channel.
