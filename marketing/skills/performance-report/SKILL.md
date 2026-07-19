---
name: performance-report
description: Pull channel performance into a clear report — what moved, why it moved, and what to do next — across product, marketing, and email analytics. Works from pasted numbers alone and gets sharper when your analytics tools are connected. Trigger with "how did [channel/campaign] perform", "build me a performance report", "what moved this week".
---

# Performance Report

Turn raw channel numbers into a report that says what changed, why, and what to do next.

## What it does
Gathers performance across your channels and writes a decision-ready report: the metrics that moved, the likely drivers, and a short list of next actions. It works from numbers you paste and gets much sharper when product, marketing, and email analytics are connected so it can read the real trend instead of a snapshot.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Product analytics | `~~product analytics` | Signups, activation, funnel conversion, and behavior after the click |
| Marketing analytics | `~~marketing analytics` | Cross-channel spend, traffic, CAC, and campaign attribution |
| Email marketing | `~~email marketing` | Opens, clicks, list growth, and per-send performance |

> **No connectors?** Fully usable. Paste your numbers (from any dashboard export) and Claude structures the report and reads the trend. Connectors mainly remove the copy-paste and let it pull the full time series.

## How it works
1. Take the period and channels you want covered (and any numbers you paste).
2. **Connected — marketing analytics:** if `~~marketing analytics` is available, pull spend, traffic, and attribution across channels.
3. **Connected — product analytics:** if `~~product analytics` is available, follow the funnel past the click — signups, activation, conversion.
4. **Connected — email marketing:** if `~~email marketing` is available, add opens, clicks, and list growth per send.
<!-- CUSTOMIZE: list your core channels and the metric that defines success for each -->
5. **Standalone:** if nothing is connected, build the report from the numbers you paste.
6. Compare against the prior period, name the likely drivers, and recommend 2–4 next actions.
<!-- CUSTOMIZE: set your comparison window (week over week, vs. plan, vs. same period last year) and any KPI targets -->

## Output
```markdown
# Performance Report: <Period>
**Headline:** <the one thing that matters this period>

## What moved
| Channel | Metric | This period | Prior | Δ |
| --- | --- | --- | --- | --- |

## Why it moved
- <driver tied to a change — campaign, spend, seasonality, funnel step>

## What to do next
1. <action> — <expected effect>
```

## Customize this skill
- List your core channels and each one's success metric.
<!-- CUSTOMIZE: set KPI targets so "good/bad" is judged against plan, not just the prior period -->
- Define your standard comparison window.
- Note who receives the report and how often it runs.

## Related skills
- **campaign-plan** — feed results back into the next campaign's KPIs.
- **competitor-brief** — put your numbers in context against a rival's signals.
- **content-draft** — write more of what the report shows is working.
