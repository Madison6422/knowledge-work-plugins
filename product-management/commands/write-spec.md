---
description: Draft a product/feature spec from a rough idea or problem.
argument-hint: "[feature or problem]"
---

# Write Spec
Runs the `write-spec` skill to turn a rough idea into a structured, review-ready spec.

## Instructions
1. Take `$ARGUMENTS` as the feature or problem to spec. If it's vague, ask one or two clarifying questions about who it's for and what success looks like.
2. Run the **write-spec** skill: state the problem, goals, non-goals, user stories, requirements, success metrics, and open questions.
3. Pull supporting context where connected — related tickets from `~~project tracker`, prior docs from `~~knowledge base`, and mockups from `~~design`. If nothing is connected, work from what the user pasted plus web research.
4. Return the spec in the skill's output format and flag any assumptions or open questions that need answers.
