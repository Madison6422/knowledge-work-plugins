---
name: statistical-analysis
description: Run the appropriate analysis — trends, cohorts, significance tests, correlation with causation caveats — and state assumptions and limits plainly. Trigger with "is this change significant", "analyze this trend", "run a cohort analysis", "are these two things correlated".
---

# Statistical Analysis

Pick the right method for the question, run it, and say clearly what it does and doesn't prove.

## What it does
Matches the question to the right analysis — trend/seasonality, cohort/retention, significance testing, or correlation — and runs it against your data. It states assumptions up front (sample size, independence, distribution), reports effect size alongside p-values, and adds plain-language caveats separating correlation from causation. The goal is an honest answer, not a false-precision one.

## Connectors it uses

| Category | Placeholder | What it adds |
|---|---|---|
| Data warehouse | `~~data warehouse` | Pulls the underlying rows for cohorts, trends, and test inputs |
| Product analytics | `~~product analytics` | Ready-made funnels, retention curves, and event cohorts to test or corroborate |

> **No connectors?** Paste the numbers (group sizes and conversions, a time series, or cohort counts). Claude runs the test, shows the math, and states the assumptions — you just supply the data.

## How it works
1. Pin the question to a method: change between two groups → significance test; behavior over time → trend; retention by signup week → cohort; two metrics moving together → correlation.
   <!-- CUSTOMIZE: your default significance level and minimum sample size (e.g. α = 0.05, n ≥ 100 per group) -->
2. **Connected:** pull inputs from `~~data warehouse` or reuse cohorts/funnels from `~~product analytics`.
   **Standalone:** use the pasted figures.
3. State assumptions before running: sample sizes, independence, distribution, and what could bias the result.
4. Run the analysis and report **effect size with the p-value / interval** — never a bare "significant."
5. Add caveats: correlation ≠ causation, confounders, seasonality, multiple-comparison risk.
   <!-- CUSTOMIZE: known confounders in your business (e.g. paydays, marketing pushes, holiday spikes) to always flag -->
6. Give a plain-language verdict and how much to trust it.
   <!-- CUSTOMIZE: your bar for acting on a result (e.g. needs a confirmed experiment, not just observational data) -->

## Output
```markdown
**Question:** Did the new checkout lift conversion?

**Method:** two-proportion z-test • **Assumptions:** independent users, α = 0.05

| Group | Users | Converts | Rate |
|---|---|---|---|
| Control | 8,140 | 611 | 7.5% |
| New | 8,203 | 722 | 8.8% |

**Result:** +1.3 pts (7.5% → 8.8%), relative lift +17%. p = 0.003, 95% CI [+0.5, +2.1 pts]. Significant.

**Caveats:** Observational split, not randomized — a concurrent email push may have hit the New group. Treat as strong signal; confirm with a controlled A/B before rollout.
```

## Customize this skill
- Set your default significance level and minimum sample size in step 1.
- List known confounders to always flag in step 5.
- Set your bar for acting on a result in step 6.

## Related skills
- **explore-dataset** — check data quality before you test on it.
- **write-query** — pull the exact rows the analysis needs.
- **insight-story** — turn a significant result into a recommendation.
