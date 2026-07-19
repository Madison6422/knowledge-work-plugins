# Enterprise Search

Search across all of your company's tools in one place. Find anything across email, chat, documents, and wikis without switching between apps.

## What's inside

### Skills
| Skill | What it does |
| --- | --- |
| **unified-search** | Runs one query across every connected source, dedupes, ranks by relevance and recency, and returns grouped results with links. |
| **search-strategy** | Refines a vague ask into a precise search — clarify intent, expand synonyms, choose sources, and iterate. |
| **source-management** | Tracks which sources are connected, what each is good for, and coverage gaps; recommends what to connect next. |
| **knowledge-synthesis** | Reads the top hits across sources and writes one cited answer, flagging where sources disagree or are stale. |
| **daily-digest** | A recurring digest of what's new and relevant across sources since last check, grouped by topic, with links. |

### Commands
| Command | What it does |
| --- | --- |
| `/enterprise-search:search` | Runs **unified-search** on what you type. |
| `/enterprise-search:digest` | Runs **daily-digest** for a time window you give (or since last check). |
| `/enterprise-search:add-source` | Runs **source-management** to review coverage and add a source. |

## Connectors

This plugin is tool-agnostic — skills refer to tools by category with `~~placeholder` markers, and the pinned servers live in `.mcp.json`. See **CONNECTORS.md** for the full mapping. Categories used: `~~chat`, `~~knowledge base`, `~~project tracker`, `~~email`, `~~calendar`.

Every skill works standalone (on what you paste in, plus web research where relevant) and gets broader as sources connect.

## Customize for your team
- Add your internal acronyms, project codenames, and synonyms so vague queries resolve to the right docs.
- Set recency and staleness thresholds (what's "too old to matter" and what's "may be outdated").
- Define source-of-truth precedence for synthesis (e.g. knowledge base overrides chat).
- Set default source routing by question type, and any sources to exclude for privacy.
- Configure the digest schedule, relevance filters, and topic buckets.

Look for `<!-- CUSTOMIZE: ... -->` markers inside each `SKILL.md` for the exact spots to edit.
