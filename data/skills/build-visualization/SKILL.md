---
name: build-visualization
description: Turn query results into the right chart with clean encoding and clear labels, recommending a chart type from the shape of the data. Trigger with "visualize this", "what chart for [data]", "make a chart of [metric]", "build a dashboard".
---

# Build Visualization

Pick the right chart for the data, then make it clean — good encoding, honest axes, readable labels.

## What it does
Takes query results or a table and recommends the chart type that fits the data's shape (trend over time, part-to-whole, comparison, distribution, correlation). It builds the chart with sensible encoding — right mark, sorted categories, clear labels, honest axes — and explains why that type fits. It can assemble several charts into a simple dashboard.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Notebook | `~~notebook` | Renders live charts from query results and hosts multi-chart dashboards you can share |

> **No connectors?** Paste the data (CSV or a table). Claude recommends the chart type, describes the exact encoding (x, y, color, sort, labels), and gives you a chart spec / config you can drop into your tool. It can't render live without a notebook, but the recommendation and spec are complete.

## How it works
1. Read the data's shape: how many dimensions, measures, and rows; is there a time axis or categories?
2. Recommend a chart type from the shape (see mapping) and say why in one line.
   <!-- CUSTOMIZE: your team's default chart library / tool and house style -->
3. Define clean encoding: pick the mark, sort categories by value, set axis starting points honestly (bars start at zero), and add direct labels over legends where it helps.
4. **Connected:** render in `~~notebook`; **Standalone:** output the chart spec/config for your tool.
5. Add a one-line takeaway title (what the chart shows, not just what it is).
   <!-- CUSTOMIZE: your color palette, brand fonts, and accessibility rules (e.g. colorblind-safe categorical palette) -->
6. For a dashboard, arrange charts most-important first and keep encodings consistent across panels.
   <!-- CUSTOMIZE: your standard dashboard layout and which top-line metrics always appear -->

**Shape → chart**
| Data shape | Use |
|---|---|
| Measure over time | Line (or area if cumulative) |
| Compare categories | Sorted bar |
| Part-to-whole | Stacked bar / 100% bar (avoid pie for > 3 slices) |
| Distribution | Histogram / box plot |
| Two measures | Scatter |

## Output
```markdown
**Recommended:** sorted horizontal bar — you're comparing revenue across 8 channels (one measure, one category).

**Encoding**
- y: channel, sorted by revenue descending
- x: revenue (starts at 0), labeled in $K
- direct value labels on each bar; no legend needed
- single brand color; highlight the top channel

**Title:** "Paid Search drove 38% of Q2 revenue"

[rendered chart in notebook / chart spec below]
```

## Customize this skill
- Set your default chart library and house style in step 2.
- Set your color palette, fonts, and accessibility rules in step 5.
- Set your standard dashboard layout and always-on metrics in step 6.

## Related skills
- **write-query** — produce the results you're charting.
- **explore-dataset** — understand distributions before plotting them.
- **insight-story** — wrap the charts in a stakeholder narrative.
