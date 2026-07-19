---
name: competitor-brief
description: Brief on a competitor's marketing — positioning, active campaigns, SEO and traffic signals, and the content angles they own. Works from web research alone and gets sharper when SEO and competitive-intelligence tools are connected. Trigger with "competitor brief on [company]", "what is [competitor] doing in marketing", "where does [rival] win on SEO".
---

# Competitor Brief

Size up a competitor's marketing so you know where they win and where there's an opening.

## What it does
Builds a structured read on one competitor's marketing: how they position themselves, what campaigns and messaging are live, their SEO and traffic signals, and the content topics they dominate. It always works from public web research and gets much sharper when SEO and competitive-intelligence tools add keyword, backlink, and traffic data.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| SEO | `~~seo` | Keyword rankings, top pages, backlink profile, content gaps |
| Competitive intelligence | `~~competitive intelligence` | Traffic estimates, channel mix, audience overlap, growth trend |

> **No connectors?** Fully usable from web research alone. Give Claude a competitor name or URL and it reads their site, ads, and public content. Connectors add the hard numbers — rankings, traffic, and backlinks — you can't see from the site.

## How it works
1. Take the competitor name or URL you provide.
2. **Web research (always):** summarize positioning, live campaigns, messaging, and the content themes they publish most.
3. **Connected — SEO:** if `~~seo` is available, pull their ranking keywords, top pages, backlinks, and the gaps you could target.
4. **Connected — competitive intelligence:** if `~~competitive intelligence` is available, add traffic estimates, channel mix, and growth trend.
<!-- CUSTOMIZE: list the competitors you track and the angles you care about most (pricing, ICP, category) -->
5. Synthesize into where they're strong, where they're exposed, and 2–4 angles you can own.
<!-- CUSTOMIZE: define what "an opening" means for your team — underserved keyword, weak content, unclaimed positioning -->

## Output
```markdown
# Competitor Brief: <Company>
**Positioning:** <one-liner> · **Primary audience:** <who> · **Traffic trend:** <up/flat/down>

## Live campaigns & messaging
- <campaign / message + where seen>

## SEO & traffic signals
| Signal | Reading |
| --- | --- |
| Top keywords | <…> |
| Top pages | <…> |
| Backlinks / authority | <…> |

## Content angles they own
- <topic they dominate>

## Openings for us
- <angle> — <why it's winnable>
```

## Customize this skill
- List the competitors you track by name.
<!-- CUSTOMIZE: set your priority keywords/topics so gap analysis focuses on what matters -->
- Define what counts as an "opening" worth acting on.
- Note any sources or claims that need a second check before you cite them.

## Related skills
- **campaign-plan** — turn an opening into a campaign.
- **performance-report** — compare your channel results against the competitor's signals.
- **content-draft** — draft content that targets the gaps you find.
