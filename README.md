# Anthropic Claude Knowledge Work Plugins

A copy-and-customize **plugin marketplace** that turns Claude into a specialist for your role, team, and company. Built for [Claude Cowork](https://claude.com/product/cowork), also compatible with [Claude Code](https://claude.com/product/claude-code).

Everything here is plain **markdown and JSON** — no backend, no build step, no code to run. A team lead can open any file, add company terminology and workflows, and Claude picks it up. That's the whole point: fork this repo, make it yours, share it with your team.

## What is a plugin?

A plugin bundles four things for one job function:

- **Skills** — markdown files that teach Claude how your role actually works: the workflows, best practices, and step-by-step playbooks. Claude draws on them *automatically* when a task is relevant.
- **Commands** — slash commands you trigger *explicitly*, like `/sales:call-prep` or `/finance:reconcile`. Each is a thin entry point to a skill.
- **Connectors** — MCP server definitions that wire Claude to the external tools your role depends on (Slack, Notion, Jira, HubSpot, a data warehouse, and so on).
- **A manifest** — a small JSON file naming the plugin and its version.

Install a plugin and Claude gains that role's expertise plus access to that role's tools.

## The plugins

Eleven role-based plugins, each a self-contained folder you can install on its own:

| Plugin | How it helps | Connectors it ships with |
|--------|--------------|--------------------------|
| **[productivity](./productivity)** | Plan your day, triage tasks, take meeting notes, and keep a personal memory of your work. | Slack, Notion, Asana, Linear, Jira, Monday, ClickUp, Microsoft 365, Google Workspace |
| **[sales](./sales)** | Research accounts, prep for calls, draft outreach, review your pipeline, and build battlecards. | Slack, HubSpot, Close, Clay, ZoomInfo, Apollo, Outreach, Notion, Jira, Fireflies, Microsoft 365, SimilarWeb |
| **[customer-support](./customer-support)** | Triage tickets, draft responses, package escalations, pull customer context, and grow the knowledge base. | Slack, Intercom, HubSpot, Guru, Jira, Notion, Microsoft 365 |
| **[product-management](./product-management)** | Write specs, plan roadmaps, synthesize research, update stakeholders, and track competitors. | Slack, Linear, Asana, Monday, ClickUp, Jira, Notion, Figma, Amplitude, Pendo, Intercom, Fireflies, SimilarWeb |
| **[marketing](./marketing)** | Draft content, plan campaigns, enforce brand voice, brief on competitors, and report on performance. | Slack, Canva, Figma, HubSpot, Amplitude, Notion, Ahrefs, SimilarWeb, Klaviyo, Supermetrics |
| **[legal](./legal)** | Review contracts, triage NDAs, check compliance, assess risk, and reuse approved clauses. | Slack, Box, Egnyte, Jira, DocuSign, Microsoft 365 |
| **[finance](./finance)** | Prepare journal entries, reconcile accounts, build statements, analyze variances, and run month-end close. | Snowflake, Databricks, BigQuery, Slack, Microsoft 365 |
| **[data](./data)** | Write and optimize SQL, explore datasets, build visualizations, run analysis, and tell the story. | Snowflake, Databricks, BigQuery, Hex, Amplitude, Definite, Jira, Slack |
| **[enterprise-search](./enterprise-search)** | Search across chat, docs, wikis, and email at once; synthesize cited answers; get a daily digest. | Slack, Notion, Guru, Jira, Asana, Microsoft 365 |
| **[bio-research](./bio-research)** | Search the literature, prioritize targets, summarize papers, design experiments, explore pathways. | PubMed, bioRxiv, ClinicalTrials.gov, ChEMBL, Open Targets, Synapse, Benchling, BioRender, Consensus |
| **[plugin-management](./plugin-management)** | Create new plugins and customize existing ones for your company's tools and workflows. | — (edits files; no external tools) |

Plus **[`_template/`](./_template)** — a blank plugin to copy when you build your own.

## Install a plugin

### In Claude Code

```bash
# 1. Add this marketplace (point at your fork, or a local path)
claude plugin marketplace add your-org/knowledge-work-plugins

# 2. Install the plugins you want
claude plugin install sales@knowledge-work-plugins
claude plugin install data@knowledge-work-plugins
```

Once installed, plugins activate automatically. Skills fire when they're relevant, and slash commands show up in your session — for example `/sales:call-prep`, `/data:write-query`, `/finance:reconcile`.

### In Cowork

Install plugins from the plugins directory in the Cowork app, or point Cowork at your fork of this repo.

### Connecting the tools

A plugin's skills work **standalone** out of the box — you paste in context, Claude researches the rest. They get much better when you connect the tools in that plugin's `.mcp.json`. You authorize each connector (usually a one-click OAuth) the first time Claude needs it. Nothing is connected until you say so.

## How the folders work

Every plugin follows the exact same shape:

```
plugin-name/
├── .claude-plugin/
│   └── plugin.json          # Manifest: name, version, description, author
├── .mcp.json                # Tool connections (MCP servers for this role)
├── CONNECTORS.md            # Which tools plug in, by category
├── README.md                # What this plugin does + how to customize it
├── commands/                # Slash commands you invoke explicitly
│   └── call-prep.md         #   → /plugin-name:call-prep
└── skills/                  # Domain knowledge Claude uses automatically
    └── call-prep/
        └── SKILL.md         #   the workflow, in editable markdown
```

And the repo as a whole:

```
knowledge-work-plugins/
├── .claude-plugin/
│   └── marketplace.json     # The index of every plugin in this repo
├── README.md                # You are here
├── _template/               # Copy this to start a new plugin
├── productivity/
├── sales/
└── ... one folder per plugin
```

Two file types carry all the behavior:

- **`SKILL.md`** has YAML frontmatter (`name`, and a `description` that includes the phrases that trigger it) followed by the workflow in plain markdown. Claude reads the description to decide when a skill applies, then follows the body.
- **`commands/*.md`** has frontmatter (`description`, `argument-hint`) and a few numbered steps. It's the explicit `/plugin:command` version of a skill.

## Make it yours

These plugins are deliberately generic starting points. They become genuinely useful once you bend them to how *your* company works. Every skill has `<!-- CUSTOMIZE: ... -->` comments marking the best places to edit.

- **Add your terminology and workflows.** Open a `SKILL.md` and replace the generic steps with how your team actually does it — your stages, your naming, your rules, your templates. This is the highest-leverage edit.
- **Point connectors at your stack.** Edit a plugin's `.mcp.json` to swap in the exact MCP servers you use. Skills refer to tools by *category* (`~~CRM`, `~~chat`, `~~data warehouse`), so any server in that category works — see each plugin's `CONNECTORS.md`.
- **Adjust the output.** Change the `## Output` block in a skill to match the format your team expects to receive.
- **Trim or extend.** Delete skills you won't use; add new ones by copying an existing skill folder.

## Create a new plugin

Two ways:

1. **Use the `plugin-management` plugin.** Install it and run `/plugin-management:create-plugin` — it walks you through the whole thing.
2. **Do it by hand.** Copy `_template/` to a new folder, fill in `plugin.json` and `.mcp.json`, write a few `SKILL.md` files and commands, and add an entry to `.claude-plugin/marketplace.json`. See [CONTRIBUTING.md](./CONTRIBUTING.md) for the step-by-step.

## Contributing

Plugins are just markdown and JSON. Fork the repo, make your changes, and open a PR. See [CONTRIBUTING.md](./CONTRIBUTING.md).

## Credits & license

Structure and connector set are inspired by Anthropic's open-source [knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins). Released under the [MIT License](./LICENSE) — copy it, fork it, sell services around it, whatever helps your team.
