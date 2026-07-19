---
name: write-query
description: Write, explain, and optimize SQL against the team's warehouse using the real schema, with inline comments and a small sample-check before running anything heavy. Trigger with "write a query for [question]", "explain this SQL", "optimize this query", "how many [thing] last month".
---

# Write Query

Turn a plain-language question into clean, correct SQL against your warehouse — explained and sample-checked before it runs at scale.

## What it does
Takes a question, maps it to the real tables and columns in your `~~data warehouse`, and writes readable SQL with comments explaining each step. Before running anything expensive, it does a small sample-check (a `LIMIT`ed preview or a cheap count) so you catch join fan-out, wrong grain, or bad filters early. It can also explain or optimize SQL you paste in.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Data warehouse | `~~data warehouse` | Reads the live schema (tables, columns, types) so queries reference real objects, and runs the sample-check |

> **No connectors?** Paste your schema (a `CREATE TABLE`, a column list, or a screenshot) and the question. Claude writes the SQL and explains it; you run it yourself and paste back the sample rows so it can sanity-check the grain and filters.

## How it works
1. Restate the question and confirm the grain (one row per _what_?) and the time window.
2. **Connected:** inspect the `~~data warehouse` schema to find the right tables, join keys, and column names.
   **Standalone:** use the schema you pasted; flag any columns it has to assume.
3. Draft the SQL with inline `--` comments on each join and filter, using the team's SQL dialect.
   <!-- CUSTOMIZE: set your dialect and conventions — e.g. Snowflake vs BigQuery vs Databricks, snake_case tables, `analytics.` schema prefix -->
4. **Sample-check first:** run a `LIMIT 100` preview or a cheap `COUNT(*)` to verify row counts look sane and joins don't fan out, before running the full/heavy version.
   <!-- CUSTOMIZE: your "heavy query" threshold — e.g. warn before scanning > 1 TB or querying the raw events table -->
5. Report the result plus any caveats (nulls, duplicates, timezone of the date column).
   <!-- CUSTOMIZE: your canonical timezone and fiscal calendar (e.g. UTC storage, reporting in US/Pacific, fiscal year starts Feb 1) -->

## Output
```markdown
**Question:** How many paid signups in June?

**Grain:** one row per user • **Window:** 2026-06-01 → 2026-06-30 (US/Pacific)

**Sample-check:** LIMIT 100 preview looked correct; COUNT = 4,812 — no join fan-out.

```sql
-- Paid signups in June, one row per user
select count(distinct u.user_id) as paid_signups
from analytics.users u
join analytics.subscriptions s   -- one active sub per user
  on s.user_id = u.user_id
where s.plan_type = 'paid'
  and u.signed_up_at >= '2026-06-01'
  and u.signed_up_at <  '2026-07-01';
```

**Caveats:** `signed_up_at` is UTC; window converted to Pacific. 12 users had null plan_type (excluded).
```

## Customize this skill
- Set your SQL dialect, schema prefixes, and naming conventions in step 3.
- Set the "heavy query" threshold that triggers the sample-check warning in step 4.
- Set your canonical timezone and fiscal calendar in step 5.

## Related skills
- **explore-dataset** — profile a table before you query it.
- **statistical-analysis** — go beyond counts to trends and significance.
- **build-visualization** — chart the query results.
