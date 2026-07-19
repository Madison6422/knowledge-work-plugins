---
name: kb-article
description: Turn a resolved ticket into a reusable self-service article for the knowledge base — problem, solution, step-by-step fix, and related articles. Claude drafts; you review and publish. Trigger with "turn this into a KB article", "write a help article from this ticket", "document this fix".
---

# KB Article

Capture a fix once, and let customers find it themselves next time.

## What it does
Takes a resolved ticket — the problem and the solution that worked — and drafts a clean, reusable article for your ~~knowledge base: a clear problem statement, the solution, numbered steps, and links to related articles. It removes customer-specific details so the article is safe to publish.

> **You approve before it goes out.** Claude drafts the article and shows it to you. A human reviews for accuracy and publishes.

## Connectors it uses

| Category | Placeholder | What it adds |
| --- | --- | --- |
| Helpdesk | `~~helpdesk` | Pulls the resolved ticket thread so the fix is captured accurately |
| Knowledge base | `~~knowledge base` | Finds related articles to link and, on approval, creates the new draft |

> **No connectors?** Paste the resolved ticket or a short description of the problem and fix. Claude drafts the article as markdown you can paste into your KB.

## How it works
1. **Get the resolution.** Connected: pull the resolved ticket from ~~helpdesk. Standalone: use the pasted problem + fix.
2. **Scrub PII.** Strip names, emails, account IDs, and anything customer-specific. Keep the fix generic.
<!-- CUSTOMIZE: list fields that must always be removed before publishing -->
3. **Write the problem statement.** One or two sentences in the customer's words — matching how they'd search for it.
4. **Write the solution and steps.** A short "why this happens" plus numbered, testable steps with expected results.
5. **Link related articles.** Search the ~~knowledge base and add "Related" links so the article connects into your help center.
6. **Apply your format.** Title, tags/category, and any front-matter your KB requires.
<!-- CUSTOMIZE: paste your article template — title style, tags, required sections, tone -->

## Output
```markdown
# Why report exports fail on large reports (and how to fix it)

**Applies to:** All plans · Web app

## Problem
Exporting a large report (roughly 50,000+ rows) fails with an "Export failed" message
instead of downloading.

## Why it happens
Very large exports can exceed the current processing limit and time out before the file
is built.

## Fix
1. Narrow the report to a shorter date range.
2. Export in batches rather than all at once.
3. Choose **CSV** instead of PDF — it processes faster for large datasets.
4. Retry the export. The file should download within a minute.

If it still fails, contact support with the report name so we can investigate.

**Related:** Exporting reports · Supported export formats · Report size limits
**Tags:** exports, reports, troubleshooting
```

## Customize this skill
- List **PII fields to strip** in step 2.
- Paste your **article template** (title style, tags, required sections) in step 6.
- Point step 5 at the **KB space** where new articles are drafted for review.

## Related skills
- **draft-response** — reuse the same grounded answer in a direct reply.
- **ticket-triage** — surfaces tickets with no existing article as KB candidates.
- **customer-context** — check whether an issue is widespread enough to document.
