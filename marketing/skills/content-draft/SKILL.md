---
name: content-draft
description: Draft on-brand content — blog posts, emails, social, or landing copy — from a short brief, following the team's voice and structure. Works from a pasted brief alone and gets sharper when brand rules and assets are connected. Trigger with "draft a blog post about [topic]", "write the launch email", "give me landing copy for [page]".
---

# Content Draft

Turn a short brief into a finished, on-brand draft in the format you need.

## What it does
Takes a content type and a topic (plus whatever brief you paste) and produces a structured, ready-to-edit draft in your team's voice. It follows the piece's natural shape — hook, body, CTA for an email; problem, proof, offer for a landing page — and pulls in brand rules and reusable assets when those tools are connected. You always get a usable draft; connectors make it match your house style without you restating it.

## Connectors it uses
| Category | Placeholder | What it adds |
| --- | --- | --- |
| Knowledge base | `~~knowledge base` | Voice guide, messaging pillars, approved boilerplate and product descriptions |
| Design / creative | `~~design` | Existing brand assets, templates, and layouts to match copy length and format |

> **No connectors?** Fully usable from a pasted brief. Give Claude the content type, topic, and audience — plus any voice notes — and it drafts from that. Connectors just save you from re-pasting brand rules every time.

## How it works
1. Read the content type and topic you provide, plus any brief, links, or reference copy.
2. **Connected — knowledge base:** if `~~knowledge base` is available, pull the voice guide, messaging pillars, and approved boilerplate so the draft matches house style.
3. **Connected — design:** if `~~design` is available, check existing templates/assets so copy fits the intended format and length.
<!-- CUSTOMIZE: name your content types and the required structure for each (e.g. blog = H2s + TL;DR; email = one CTA) -->
4. **Standalone:** if nothing is connected, draft from the brief and any voice notes you paste.
5. Draft the piece in the right structure for its type, then flag any claim that needs a fact-check or an owner sign-off.
<!-- CUSTOMIZE: list claims that always need review — pricing, performance stats, customer names, legal terms -->

## Output
```markdown
# <Content type>: <Working title>
**Audience:** <who> · **Goal:** <what it should do> · **CTA:** <primary action>

## Draft
<the drafted copy, in the structure for this content type>

## Alternate hooks / subject lines
- <option 1>
- <option 2>

## Needs review before publish
- <claim or line that needs a fact-check or sign-off>
```

## Customize this skill
- Define your content types and the structure each one must follow.
<!-- CUSTOMIZE: point to where your voice guide and boilerplate live in the knowledge base -->
- Set which claims always require a human fact-check or approval.
- Add your default audience/persona names so briefs can stay short.

## Related skills
- **brand-voice** — check the finished draft against your voice guide.
- **campaign-plan** — decide which content pieces a campaign needs before drafting.
- **performance-report** — see which past pieces performed so you write more of what works.
