---
name: variance-analysis
description: Compare actuals against budget or a prior period, quantify each variance by recomputing the change over base, explain the drivers, and flag anything material. Trigger with "run variance analysis for [period]", "actuals vs budget for Q3", "why did opex move this month".
---

# Variance Analysis

Compare actuals to budget or prior period, size each variance, and explain what drove it.

## What it does

Takes actuals and a comparison base (budget, forecast, or a prior period), computes the variance for each line — amount and percent, recomputed as (actual − base) ÷ base — and explains the drivers behind the material ones. It flags anything over your materiality threshold so reviewers focus on what matters. Claude drafts the analysis; a person reviews before it's used in reporting.

> **A person reviews before it goes out.** The analysis and its narrative are drafts for a person to check before they're shared or included in a board or management package.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Data warehouse | `~~data warehouse` | Pulls actuals, budget, and prior-period balances at line-item detail so variances are computed from live data and drivers can be drilled down |

> **No connectors?** Paste in the actuals and the comparison figures and Claude computes and explains the variances from that. Every variance shows the two numbers it was computed from.

## How it works

1. Confirm the period, the metric set (P&L lines, department, KPI), and the base to compare against (budget / forecast / prior period).
2. **Connected:** pull actuals and base figures from `~~data warehouse`. **Standalone:** use the figures you paste in.
3. For each line, recompute the variance yourself: absolute change = actual − base; percent change = (actual − base) ÷ base. Show both. Do not trust a pre-computed variance without checking it.
4. Flag any variance at or above your materiality threshold (by amount or percent).
5. Explain the driver for each material variance — volume, price, timing, one-offs — using detail from the source, not speculation. Where the driver is unknown, say so.
6. Present the analysis for review. Never invent a figure or a driver — each variance is shown with its two source numbers.

<!-- CUSTOMIZE: set your materiality threshold (e.g. > $10k AND > 5%) -->
<!-- CUSTOMIZE: define your default comparison base (budget vs prior period) and driver categories -->

## Output

```markdown
## Variance Analysis — Opex, Q3 Actuals vs Budget (draft)
Source: actuals from ledger; budget from FY26 plan.

| Line | Actual | Budget | Var $ | Var % | Material? |
|---|---:|---:|---:|---:|---|
| Salaries | 620,000 | 600,000 | +20,000 | +3.3% | No |
| Marketing | 310,000 | 250,000 | +60,000 | +24.0% | **Yes** |
| Travel | 45,000 | 70,000 | -25,000 | -35.7% | **Yes** |

### Material variances
- **Marketing +60,000 (+24.0%):** Q3 campaign pulled forward from Q4 — one-time; source: GL 6400 detail.
- **Travel -25,000 (-35.7%):** two conferences deferred to Q4; recurring spend unchanged.

Threshold applied: > $25k or > 15%.
> Draft for review before inclusion in the management package.
```

## Customize this skill

- Set your materiality threshold (amount, percent, or both).
- Choose the default comparison base and your driver categories (volume/price/timing/one-off).
- Name the line items or departments the analysis should always break out.

## Related skills

- `financial-statements` — the statements whose movements this explains.
- `month-end-close` — variance review is a standard close step.
- `journal-entry` — book any corrections a variance uncovers.
