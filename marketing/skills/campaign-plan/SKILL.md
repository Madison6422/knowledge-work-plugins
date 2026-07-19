---
name: campaign-plan
description: Plan a multi-channel marketing campaign end to end — goal, audience, channels, messaging, timeline, assets needed, and KPIs. Works from a stated goal alone and gets sharper when your knowledge base, tracker, and email tool are connected. Trigger with "plan a campaign for [launch]", "build a campaign plan to [goal]", "map out the channels for [initiative]".
---

# Campaign Plan

Turn a campaign goal into a concrete, channel-by-channel plan the team can execute.

## What it does
Takes a goal (a launch, a number, an event) and builds a structured plan: who you're targeting, which channels carry the message, the core message per channel, a timeline, the assets each stage needs, and the KPIs you'll judge it by. It works from a one-line goal and gets sharper when brand rules, the project tracker, and your email tool are connected so tasks and sends line up with reality.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Knowledge base | `~~knowledge base` | Voice guide, messaging pillars, positioning, past campaign notes |
| Project tracker | `~~project tracker` | Turns the plan into owned, dated tasks and checks team capacity |
| Email marketing | `~~email marketing` | Audience segments, list sizes, and send-window history for the email channel |

> **No connectors?** Fully usable from a stated goal. Claude proposes audience, channels, messaging, timeline, and KPIs you can edit. Connectors mainly turn the plan into real tasks and ground the email channel in your actual lists.

## How it works
1. Take the campaign goal and any constraints you provide (budget, deadline, target number).
2. **Connected — knowledge base:** if `~~knowledge base` is available, pull messaging pillars and positioning so channel messages stay on-strategy.
3. **Connected — email marketing:** if `~~email marketing` is available, read available segments and list sizes to size the email channel realistically.
4. **Connected — project tracker:** if `~~project tracker` is available, draft the plan as dated tasks with owners and check for conflicts.
<!-- CUSTOMIZE: list your standard channels and who owns each (paid, social, email, blog, PR, events) -->
5. **Standalone:** if nothing is connected, propose a full plan from the goal that you can hand-edit.
6. Assemble the plan, size each stage's asset needs, and set KPIs with a baseline and a target.
<!-- CUSTOMIZE: set your default KPIs per goal type — awareness, leads, pipeline, retention -->

> **You approve before it goes out.** Claude drafts the plan and the tasks; a human confirms budget, owners, and dates before anything is scheduled or sent.

## Output
```markdown
# Campaign Plan: <Name>
**Goal:** <goal + target number> · **Window:** <start–end> · **Owner:** <name>

## Audience
- <segment> — <why they matter>

## Channels & messaging
| Channel | Core message | Asset needed | Owner |
| --- | --- | --- | --- |

## Timeline
| Week | Milestone | Deliverable |
| --- | --- | --- |

## KPIs
| Metric | Baseline | Target |
| --- | --- | --- |
```

## Customize this skill
- List your standard channels and their owners.
<!-- CUSTOMIZE: set budget thresholds that require sign-off before scheduling -->
- Define default KPIs and targets by campaign type.
- Point to where past campaign retros live so lessons carry forward.

## Related skills
- **content-draft** — draft the assets the plan calls for.
- **performance-report** — measure the campaign against its KPIs after launch.
- **brand-voice** — keep every channel message on-tone.
