---
name: daily-digest
description: A recurring digest of what's new and relevant across your sources since last check — pulled from chat, knowledge base, project tracker, and email, grouped by topic, with links. Works standalone on what you paste and gets fuller as sources connect. Trigger with "what's new since yesterday", "give me my digest", "catch me up across our tools", "daily digest".
---

# Daily Digest

Catch up on everything that changed across your tools, grouped by topic, in one read.

## What it does
Sweeps your connected sources for what's new or updated since your last check, filters to what's actually relevant to you, and groups it by topic with a link for each item. It's built to run on a schedule — every morning, or on demand — so you scan one digest instead of five apps. It works from material you paste in with nothing connected, and becomes a true cross-tool catch-up once sources are wired up.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Chat | `~~chat` | New messages, decisions, and mentions since last check |
| Knowledge base | `~~knowledge base` | Newly created or edited docs and pages |
| Project tracker | `~~project tracker` | Status changes, new tickets, and closed work |
| Email | `~~email` | New threads, announcements, and external updates |

> **No connectors?** Paste in a set of updates or a thread and Claude will group and summarize them. Connectors are what make this a genuine "everything since yesterday" sweep.

## How it works
1. Set the window: since your last digest, or a period you name (e.g. "since Friday").
2. **Connected — sweep:** pull what's new or changed from `~~chat`, `~~knowledge base`, `~~project tracker`, `~~email` within the window.
3. **Standalone:** organize whatever updates you provide.
4. **Filter to relevant:** keep items tied to your projects, mentions, and watched topics; drop noise.
<!-- CUSTOMIZE: define what's "relevant to me" — your projects, teams, channels, and watched keywords -->
5. **Group by topic**, newest first, with a one-line summary and link per item.
<!-- CUSTOMIZE: set your topic buckets — e.g. My projects, Team, Company-wide, External -->
6. Lead with a short "top 3 things to know" so the digest is skimmable in seconds.

## Output
```markdown
# Digest — <date> (since <last check>)
**Top 3:** <the three things not to miss>

## <Topic A>
- <what changed> — <source, who, time> · <link>

## <Topic B>
- <what changed> — <source, who, time> · <link>

## Mentions & asks
- <where you were @-mentioned or asked something> · <link>

_Sources swept: ~~chat, ~~knowledge base, ~~project tracker, ~~email_
```

## Customize this skill
- Define what counts as "relevant to me" under step 4.
- Set your topic buckets under step 5.
<!-- CUSTOMIZE: set the schedule and delivery — e.g. weekday 8am, and whether it posts to a channel or stays a draft you review -->
- Choose the schedule and whether the digest is delivered automatically or reviewed first.

## Related skills
- **unified-search** — dig into any digest item across all sources.
- **knowledge-synthesis** — turn a hot topic in the digest into a cited answer.
- **source-management** — coverage determines what the digest can watch.
