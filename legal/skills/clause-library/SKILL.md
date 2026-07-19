---
name: clause-library
description: Maintain and retrieve your team's approved standard clauses and fallback positions so drafting reuses vetted language. Claude organizes and suggests; a qualified attorney approves any clause and any use. This is not legal advice. Trigger with "find our standard [clause]", "what's our fallback on liability", "add this clause to the library".
---

# Clause Library

A living library of approved standard clauses and fallback positions, so drafting and negotiation reuse language an attorney has already vetted.

> **Not legal advice.** Claude helps organize and retrieve clauses; it does not approve them. A qualified attorney must approve every clause added to the library and confirm its fit before it is used in a live agreement.

## What it does

Stores and retrieves your team's approved standard clauses, their fallback tiers, and the guidance on when to use each. On request it finds the right clause for a situation, shows the primary and fallback options in order, and — when you provide new vetted language — files it into the library with the metadata that makes it findable later.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Document management | `~~document management` | Stores and retrieves the approved clause library and templates |
| Knowledge base | `~~knowledge base` | Holds usage guidance, fallback ladders, and negotiation notes |
| Chat | `~~chat` | Lets the team request clauses and flag ones needing re-approval |

> **No connectors?** Paste your existing clauses and Claude organizes and retrieves from what you provide in-session. Connect `~~document management` so the library persists and the whole team draws from the same vetted source of truth.

## How it works

**Retrieve**
1. **Take the request.** The clause type and the context (deal type, counterparty leverage, jurisdiction).
2. **Find it.** Connected: pull matching clauses from `~~document management` / `~~knowledge base`. Standalone: search what the user pasted.
3. **Present options in order.** Primary (preferred) → fallback tiers → walk-away position, with the "use when" note for each.
<!-- CUSTOMIZE: your fallback-ladder structure, e.g. Preferred / Acceptable / Last resort -->

**Maintain**
4. **Intake new language.** When the user supplies a clause, capture it with type, approved-by, effective date, jurisdiction, and version.
<!-- CUSTOMIZE: the metadata fields your library requires -->
5. **Flag for approval.** Mark any new or edited clause as **pending attorney approval** until an attorney signs off; only approved clauses are offered as "standard."
6. **File it.** Store to `~~document management` so drafting reuses it.

**You approve before it goes out.** Claude suggests clauses; a qualified attorney approves each clause and confirms its fit for the specific deal. No clause is "approved" on Claude's say-so.

## Output

```markdown
# Clause: [Type] — e.g. Limitation of Liability

**Status:** Approved ✅ / Pending attorney review ⏳
**Approved by:** [attorney] · **Effective:** [date] · **Jurisdiction:** [x]

## Primary (preferred)
> [clause text]
_Use when: standard deals, balanced leverage._

## Fallback 1 (acceptable)
> [clause text]
_Use when: counterparty pushes; still within policy._

## Walk-away
- Below this, escalate to the attorney.

_Organized by Claude. Not legal advice — attorney approval required before use._
```

## Customize this skill

- Point storage/retrieval at your real `~~document management` clause library.
- Define your fallback ladder in step 3.
<!-- CUSTOMIZE: which attorney or role approves clauses into the library -->
- Set the required metadata fields in step 4.
- Decide which clause types the library must always carry (liability, indemnity, IP, termination, confidentiality...).

## Related skills

- **contract-review** — reviews contracts against these approved clauses.
- **nda-triage** — reuses approved confidentiality and carve-out language.
- **risk-assessment** — pulls protective clauses to mitigate flagged risks.
