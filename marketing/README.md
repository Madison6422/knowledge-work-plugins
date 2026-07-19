# Marketing

Create content, plan campaigns, and analyze performance across marketing channels. Maintain brand voice consistency, track competitors, and report on what's working.

## What's inside

### Skills
| Skill | What it does |
| --- | --- |
| `content-draft` | Drafts on-brand content (blog, email, social, landing) from a brief in your voice and structure. |
| `campaign-plan` | Plans a multi-channel campaign: goal, audience, channels, messaging, timeline, assets, and KPIs. |
| `brand-voice` | Checks a draft against your voice and messaging guide; flags off-tone lines and suggests fixes. |
| `competitor-brief` | Briefs a competitor's marketing: positioning, campaigns, SEO/traffic signals, and content angles. |
| `performance-report` | Pulls channel performance into a clear report: what moved, why, and what to do next. |

### Commands
| Command | What it does |
| --- | --- |
| `/marketing:draft-content` | Runs **content-draft** for a given content type and topic. |
| `/marketing:plan-campaign` | Runs **campaign-plan** for a stated campaign goal. |
| `/marketing:brand-check` | Runs **brand-voice** on a pasted draft or file. |

## Connectors

Every skill works with zero connectors and gets sharper when tools are connected. See `CONNECTORS.md` for the full mapping. Tools are referenced by category, not product:
`~~knowledge base`, `~~design`, `~~project tracker`, `~~email marketing`, `~~seo`, `~~competitive intelligence`, `~~product analytics`, `~~marketing analytics`, `~~chat`, `~~email`, `~~calendar`.

## Customize for your team
- Set your voice guide, tone attributes, and banned-word list where the skills point (`brand-voice`, `content-draft`).
- Define your standard channels, owners, and default KPIs (`campaign-plan`, `performance-report`).
- Name the competitors you track and the angles you care about (`competitor-brief`).
- Edit the `<!-- CUSTOMIZE -->` marks in each SKILL.md to add your terminology and thresholds.
- Point the `~~category` placeholders at the specific servers your team uses in `.mcp.json`.
