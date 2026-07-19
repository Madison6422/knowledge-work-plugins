---
description: Build a ranked evidence dossier for a drug target against an indication.
argument-hint: "[gene/target + indication]"
---

# Target Brief
Runs the **target-prioritization** skill.

## Instructions
1. Read `$ARGUMENTS` for the target(s) and indication. If no indication is given, ask for one — evidence is only meaningful against a disease context.
2. Follow the **target-prioritization** skill across all axes: genetic association, expression, tractability, safety, and competition.
3. Pull association and expression from ~~target evidence, tractability from ~~compound database, and competition from ~~clinical trials; back each axis with a source.
4. Return the scorecard with a plain-language recommendation and the open questions.
5. Note the brief is for internal prioritization only — verify against primary sources; not clinical or investment guidance.
