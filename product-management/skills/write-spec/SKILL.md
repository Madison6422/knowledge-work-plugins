---
name: write-spec
description: Turns a rough product or feature idea into a structured spec — problem, goals, non-goals, user stories, requirements, success metrics, and open questions. Pulls supporting context from your project tracker, knowledge base, and design files. Trigger with "write a spec for [feature]", "draft a PRD", "turn this idea into a spec".
---

# Write Spec
Draft a clear, review-ready product spec from a one-line idea or a messy brain dump.

## What it does
Takes whatever you have — a Slack thread, a sentence, a customer complaint — and shapes it into a complete spec: the problem, what success looks like, what's explicitly out of scope, the user stories, and the open questions that still need answers. It fills gaps by pulling related tickets, docs, and designs when those tools are connected, and flags assumptions so reviewers can push back on the right things.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Project tracker | `~~project tracker` | Related tickets, prior epics, existing scope so the spec doesn't reinvent work |
| Knowledge base | `~~knowledge base` | Existing PRDs, strategy docs, and past decisions to stay consistent |
| Design | `~~design` | Links to mockups and flows to ground requirements in real screens |

> **No connectors?** Paste in the idea, any notes, and links. The skill drafts the full spec from that plus web research on the problem space, and marks where connected context would sharpen it.

## How it works
1. Restate the **problem** in one or two sentences and confirm who it's for.
2. Pull context: search `~~project tracker` for related tickets/epics, `~~knowledge base` for prior specs and strategy, and link relevant `~~design` frames. Standalone: use pasted notes and links.
3. Draft **goals** and **non-goals** — be explicit about what this does *not* do.
4. Write **user stories** and **requirements**, tagged must-have vs. nice-to-have.
<!-- CUSTOMIZE: set your priority scale — e.g. P0/P1/P2, or MoSCoW -->
5. Propose **success metrics** tied to the goals.
<!-- CUSTOMIZE: list your team's north-star and guardrail metrics -->
6. Collect **open questions** and assumptions so reviewers know what's unresolved.

## Output
```markdown
# Spec: [Feature name]
**Author:** [you] · **Status:** Draft · **Last updated:** [date]

## Problem
[1–2 sentences: who hurts, and how]

## Goals
- [Outcome 1]
- [Outcome 2]

## Non-goals
- [Explicitly out of scope]

## User stories
- As a [user], I want [capability] so that [benefit].

## Requirements
| # | Requirement | Priority | Notes |
|---|-------------|----------|-------|
| 1 | [Requirement] | P0 | [design/ticket link] |

## Success metrics
- [Metric] — target [value]

## Open questions
- [ ] [Unresolved question / assumption to validate]
```

## Customize this skill
- Set your **priority scale** (P0/P1/P2 vs. MoSCoW) in step 4.
- List your team's **north-star and guardrail metrics** so metrics aren't invented each time.
- Point the knowledge-base search at your **spec template or folder** if you have a house format.

## Related skills
- `roadmap-plan` — slot the spec into a quarter once it's approved.
- `research-synthesis` — ground the problem statement in real user evidence.
- `stakeholder-update` — announce the spec once it's ready for review.
