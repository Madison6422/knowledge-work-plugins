---
name: explore-dataset
description: Profile a dataset before you analyze it — row counts, distributions, nulls, keys, and obvious data-quality issues — so you understand its shape and traps first. Trigger with "explore [table]", "profile this dataset", "what's in [table]", "is this data clean".
---

# Explore Dataset

Get to know a table before you trust it — a fast, structured profile of size, shape, keys, and quality gotchas.

## What it does
Runs a standard profiling pass over a dataset: total rows, per-column distributions and cardinality, null rates, candidate primary keys, duplicate checks, and obvious data-quality flags (out-of-range values, mixed formats, unexpected nulls). The result tells you what the data means and where it will bite you, before you build analysis on top of it.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Data warehouse | `~~data warehouse` | Reads the schema and runs the profiling queries directly against the table |
| Notebook | `~~notebook` | Renders the profile as tables and quick distribution charts you can save and share |

> **No connectors?** Paste a sample (a CSV export, the first few hundred rows, or a schema). Claude profiles what you give it, notes that stats are sample-based not full-table, and lists the exact queries to run for the complete picture.

## How it works
1. Identify the table/dataset and its intended grain (one row per _what_?).
2. **Connected:** query the `~~data warehouse` for row count, column types, null counts, distinct counts, and min/max per column.
   **Standalone:** compute the same profile over the pasted sample and mark it as sample-based.
3. Check keys and duplicates: does the assumed primary key uniquely identify rows? Flag fan-out risk for later joins.
4. Flag data-quality issues: high null rates, single-value columns, outliers, mixed date/number formats, stale max dates.
   <!-- CUSTOMIZE: your data-quality thresholds — e.g. flag columns with > 20% nulls, or a freshness SLA (max date within 24h) -->
5. **Connected:** render distributions and the profile summary in `~~notebook` for sharing.
   <!-- CUSTOMIZE: known-messy tables or columns your team should always double-check -->
6. Summarize what the dataset is good for and what to avoid.
   <!-- CUSTOMIZE: link to your data catalog / dictionary so column meanings resolve to the source of truth -->

## Output
```markdown
**Dataset:** analytics.orders • **Rows:** 1,204,882 • **Grain:** one row per order • **Freshness:** max order_date = 2026-07-18 (fresh)

**Columns (highlights)**
| Column | Type | Nulls | Distinct | Notes |
|---|---|---|---|---|
| order_id | string | 0% | 1,204,882 | unique — valid primary key |
| user_id | string | 0% | 88,410 | ~13.6 orders/user |
| amount | number | 0% | — | range $0–$9,900; 34 rows = $0 (refunds?) |
| coupon | string | 71% | 22 | mostly null — expected |

**Quality flags**
- 34 orders with amount = 0 — confirm these are refunds, not bad rows.
- `channel` has mixed casing ("Web" vs "web") — normalize before grouping.

**Good for:** order-level revenue, per-user frequency. **Avoid:** joining on `email` (12% null).
```

## Customize this skill
- Set your null-rate and freshness thresholds in step 4.
- List known-messy tables to always double-check in step 5.
- Link your data catalog / dictionary in step 6.

## Related skills
- **write-query** — once you know the shape, query it correctly.
- **statistical-analysis** — analyze the clean columns you profiled.
- **build-visualization** — turn distributions into shareable charts.
