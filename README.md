# raumnebenan Agent Plugin

raumnebenan.de is a resource hub focused on actionable product thinking for product owners, product designers, business analysts, product managers, agile coaches, and user researchers.

- plugin manifest is in `plugins/raumnebenan/.github/plugin.json`
- marketplace manifest is in `.github/plugin/marketplace.json`
- reusable skill content is in `skills/raumnebenan/`
- MCP server config is in `.mcp.json`

## Repository structure

```text
.
├── .github/
│   └── plugin/
│       └── marketplace.json
├── .mcp.json
├── plugins/
│   └── raumnebenan/
│       └── .github/
│           └── plugin.json
└── skills/
	└── raumnebenan/
		└── SKILL.md
```

## Install via marketplace (recommended)

Enable plugins and add this repository as a marketplace in VS Code user settings:

```json
{
	"chat.plugins.enabled": true,
	"chat.plugins.marketplaces": [
		"mynona/ai-plugin"
	]
}
```

Then open Extensions and search for `@agentPlugins` to install `raumnebenan`.

Copilot CLI marketplace checks:

```bash
copilot plugin marketplace browse mynona/ai-plugin
copilot plugin install raumnebenan@raumnebenan-ai-plugins
```

## Install without marketplace

Install directly from GitHub and point to the plugin subdirectory:

```bash
copilot plugin install mynona/ai-plugin:plugins/raumnebenan
```

You can also add the local plugin path in VS Code settings:

```json
{
	"chat.plugins.paths": [
		"/absolute/path/to/ai_plugin/plugins/raumnebenan"
	]
}
```

## License

MIT
