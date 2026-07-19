---
name: source-management
description: Track which sources are connected, what each is good for, and where coverage has gaps — then help decide what to connect next. Works standalone from what you describe and reads live connection status when available. Trigger with "what sources are connected", "what should I connect next", "review my search sources", "add a source".
---

# Source Management

Know what you're actually searching — and what you're missing.

## What it does
Gives you a clear map of your search coverage: which sources are connected, what each one is best at finding, and where the blind spots are (a tool your team lives in that isn't wired up yet). It then recommends what to connect next based on the gaps that matter most. It works from a description of your stack with nothing connected, and reads real connection status when sources are available.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Chat | `~~chat` | Confirms chat is searchable; flags if missing |
| Knowledge base | `~~knowledge base` | Confirms canonical docs are searchable |
| Project tracker | `~~project tracker` | Confirms tickets and tasks are searchable |
| Email | `~~email` | Confirms mail threads are searchable |

> **No connectors?** Still useful — describe your tools and Claude maps coverage and gaps from that. When sources are connected, it reports live status instead of relying on your description.

## How it works
1. Detect connected sources (or take the list you describe) and note which category each fills.
2. For each, summarize what it's best at finding so routing decisions are obvious.
<!-- CUSTOMIZE: list the tools your team actually uses per category, so "gaps" reflects your real stack -->
3. **Find gaps:** compare against the categories your team relies on and flag any that are missing or thin.
4. Rank what to connect next by how much search coverage it would add and how often you'd hit it.
<!-- CUSTOMIZE: set your priority order — e.g. knowledge base and chat before email -->
5. Give a short recommendation with the single highest-value source to add.

## Output
```markdown
# Search coverage
**Connected:** <count> sources across <count> categories

| Category | Placeholder | Status | Best for |
| --- | --- | --- | --- |
| Chat | ~~chat | ✅ / ❌ | <what it finds> |
| Knowledge base | ~~knowledge base | ✅ / ❌ | <what it finds> |
| Project tracker | ~~project tracker | ✅ / ❌ | <what it finds> |
| Email | ~~email | ✅ / ❌ | <what it finds> |

## Gaps
- <missing/thin category> — <what you can't find because of it>

## Recommended next
1. <source to connect> — <coverage it adds>
```

## Customize this skill
- List the specific tools your team uses in each category under step 2.
- Set the priority order for closing gaps under step 4.
<!-- CUSTOMIZE: note any sources you deliberately won't connect (compliance, access) so they aren't flagged as gaps -->
- Record sources you intentionally exclude so they don't show up as gaps.

## Related skills
- **unified-search** — search everything that's currently connected.
- **search-strategy** — route queries to the sources you do have.
- **daily-digest** — coverage decides what the digest can watch.
