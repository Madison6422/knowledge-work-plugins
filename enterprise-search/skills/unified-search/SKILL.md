---
name: unified-search
description: Run one query across every connected source — chat, knowledge base, project tracker, and email — then dedupe, rank by relevance and recency, and return grouped results with links. Works standalone on pasted content and gets broader as sources connect. Trigger with "search everything for [topic]", "find anything about [X]", "look across all our tools for [query]".
---

# Unified Search

One query, every source. Find anything across chat, docs, wikis, tickets, and email without switching apps.

## What it does
Takes a single search request and fans it out to every connected source at once, then merges the hits into one clean list. It removes duplicates (the same doc linked in chat and the wiki), ranks by how well each result matches and how recent it is, and groups the output by source with a direct link for each hit. With no connectors it still searches whatever you paste in and can pull public web results when useful.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Chat | `~~chat` | Messages, threads, and shared files from team channels and DMs |
| Knowledge base | `~~knowledge base` | Wiki pages, docs, and verified answers |
| Project tracker | `~~project tracker` | Tickets, tasks, and project docs |
| Email | `~~email` | Relevant threads, attachments, and announcements |

> **No connectors?** Still useful. Paste in text, a doc, or a thread and Claude searches within it, and can pull public web results for background. Connectors are what let one query reach across your real tools at once.

## How it works
1. Take your query as-is, or lightly normalize it (fix obvious typos, note key terms).
2. **Connected — fan out:** query each available source in parallel — `~~chat`, `~~knowledge base`, `~~project tracker`, `~~email`.
3. **Standalone:** search any content you pasted in; optionally add public web results for context.
4. **Dedupe:** collapse the same item found in multiple places into one result, noting where else it appeared.
5. **Rank:** score each hit on relevance to the query and recency, so fresh, on-topic items rise.
<!-- CUSTOMIZE: set your recency weighting — e.g. down-rank anything older than 12 months, or boost the current quarter -->
6. Group results by source, add a one-line snippet and a direct link for each, and flag the single best match.
<!-- CUSTOMIZE: list any sources to always exclude from search (e.g. HR, legal, exec-only channels) -->

## Output
```markdown
# Search: "<query>"
**Top match:** <title> — <source> · <link>

## Chat (~~chat)
- <snippet> — <channel/author, date> · <link>

## Knowledge base (~~knowledge base)
- <page title> — <space, updated date> · <link>

## Project tracker (~~project tracker)
- <ticket/task> — <status, updated date> · <link>

## Email (~~email)
- <subject> — <from, date> · <link>

_Also seen in: <other sources where a top hit appeared>_
```

## Customize this skill
- Set recency weighting and the "too old to matter" cutoff under step 5.
<!-- CUSTOMIZE: add your team's aliases and jargon so a query for the internal name matches the real docs -->
- Add internal acronyms and project codenames so queries resolve to the right items.
- List sources or channels to always exclude for privacy or noise reasons.

## Related skills
- **search-strategy** — refine a vague ask into a precise, high-yield query first.
- **knowledge-synthesis** — turn the top hits into a single cited answer.
- **source-management** — check what's connected and where coverage gaps are.
