---
description: Compare actuals vs budget or prior period, size each variance, and explain drivers
argument-hint: "[period, e.g. 'Q3 vs budget']"
---

# Variance Analysis

Runs the `variance-analysis` skill to compare actuals against a base and explain the movements.

## Instructions

1. Read `$ARGUMENTS` for the period and the comparison base (budget, forecast, or prior period).
2. Run the `variance-analysis` skill. Pull actuals and base figures from `~~data warehouse` if connected; otherwise ask the user to paste both sets of numbers.
3. For each line, recompute the variance: amount = actual − base, percent = (actual − base) ÷ base. Show both.
4. Flag every variance at or above the materiality threshold and explain its driver using source detail, not speculation.
5. Present the analysis for the user to review before it's shared. Show each variance with the two source figures it came from.
