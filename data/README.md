# Data

Write SQL, explore datasets, and generate insights faster. Build visualizations and dashboards, and turn raw data into clear stories for stakeholders.

## What's inside

**Skills**

| Skill | What it does |
|---|---|
| write-query | Write, explain, and optimize SQL against the warehouse — real schema, comments, and a sample-check before running heavy. |
| explore-dataset | Profile a dataset: row counts, distributions, nulls, keys, and data-quality issues before you analyze. |
| build-visualization | Turn results into the right chart with clean encoding and labels; recommend chart type from the data shape. |
| statistical-analysis | Run the right analysis (trends, cohorts, significance, correlation caveats) and state assumptions and limits plainly. |
| insight-story | Turn an analysis into a stakeholder narrative — headline, evidence, so-what, action — with numbers validated first. |

**Commands**

| Command | What it does |
|---|---|
| `/data:write-query` | Runs write-query — turn a question into commented, sample-checked SQL. |
| `/data:explore` | Runs explore-dataset — profile a table or dataset. |
| `/data:build-dashboard` | Runs build-visualization — assemble several charts into a dashboard. |

## Connectors

This plugin is tool-agnostic — skills refer to tools by category (e.g. `~~data warehouse`, `~~notebook`). See **[CONNECTORS.md](./CONNECTORS.md)** for the full mapping. Categories used: data warehouse, notebook, product analytics, analytics, chat.

## Customize for your team
- Set your SQL dialect, schema prefixes, timezone, and fiscal calendar in **write-query**.
- Set data-quality thresholds and known-messy tables in **explore-dataset**.
- Set your chart library, color palette, and dashboard layout in **build-visualization**.
- Set significance levels, sample-size minimums, and known confounders in **statistical-analysis**.
- Set audiences, number-validation rules, and summary tone in **insight-story**.
- Every skill has `<!-- CUSTOMIZE: ... -->` marks pointing at exactly what to edit.
