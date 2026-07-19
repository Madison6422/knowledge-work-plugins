# Connectors — Bio Research

## How tool references work
This plugin is **tool-agnostic**. Skills never name a specific product — they refer to a tool by its *category* using a `~~placeholder` (for example `~~literature` or `~~target evidence`). The `.mcp.json` file pins the specific MCP servers that ship with the plugin, but the prose stays generic so **any MCP server in a category works**. Swap a server in `.mcp.json` and the skills keep working unchanged.

Every skill also runs **standalone**: with no connectors, it uses what you paste in (abstracts, PDFs, target names) plus general web research. Connecting a server just makes the search systematic and the links verifiable.

## Connectors for this plugin
| Category | Placeholder | Included servers | Other options |
|---|---|---|---|
| Literature | `~~literature` | pubmed, biorxiv, consensus | Semantic Scholar, Europe PMC |
| Clinical trials | `~~clinical trials` | c-trials | — |
| Chemical / bioactivity DB | `~~compound database` | chembl | PubChem, DrugBank |
| Target–disease evidence | `~~target evidence` | open-targets | — |
| Research data platform | `~~research data` | synapse | Zenodo, Dryad |
| ELN / LIMS | `~~lab notebook` | benchling | LabArchives, SciNote |
| Scientific figures | `~~figures` | biorender | — |

> Categories not currently used by a skill (`~~research data`, `~~figures`) are still pinned in `.mcp.json` and available to reference as you extend the plugin.
