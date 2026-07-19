# raumnebenan Agent Plugin

raumnebenan.de is a resource hub focused on actionable product thinking for product owners, product designers, business analysts, product managers, agile coaches, and user researchers.

- the installable Copilot CLI plugin lives in `plugins/raumnebenan/`
- plugin manifest is in `plugins/raumnebenan/plugin.json`
- marketplace manifest is in `.github/plugin/marketplace.json`
- plugin skill content is in `plugins/raumnebenan/skills/search-raumnebenan/`
- plugin MCP server config is in `plugins/raumnebenan/.mcp.json`
- the repository root also contains a VS Code extension wrapper that points to the plugin root directory above (`plugins/raumnebenan`)

## Distribution modes

This repository ships two install modes:

- VS Code extension wrapper (`package.json` at repo root): appears in the Extensions view and contributes the agent plugin.
- Agent plugin (`plugins/raumnebenan/`): installable through Copilot plugin flows and plugin marketplaces.

If you install from the VS Code Extension Marketplace, it will show up as an extension (this is expected).

## Repository structure

```text
.
├── .github/
│   └── plugin/
│       └── marketplace.json
├── package.json
├── plugins/
│   └── raumnebenan/
│       ├── .mcp.json
│       ├── plugin.json
│       └── skills/
│           └── search-raumnebenan/
│               └── SKILL.md
└── skills/
	└── search-raumnebenan/
        └── SKILL.md
```

## Local plugin install

The official docs describe a plugin as a directory whose root contains `plugin.json`. In this repository that directory is:

```text
plugins/raumnebenan/
```

Install that directory directly when testing locally:

```bash
copilot plugin install ./plugins/raumnebenan
```

After reinstalling, verify it loaded:

```bash
copilot plugin list
```

## Install via marketplace (recommended)

Add this repository as a marketplace in VS Code user settings:

```json
{
	"chat.plugins.marketplaces": [
		"mynona/ai-plugin"
	]
}
```

Then open Extensions and search for `@agentPlugins` to install `raumnebenan`.

Note: the VS Code extension wrapper sets `chat.plugins.enabled` via `configurationDefaults` while installed. This is extension-scoped behavior, not a hardcoded user settings edit.

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

You can also register the local plugin path in VS Code settings:

```json
{
	"chat.pluginLocations": {
		"/absolute/path/to/ai_plugin/plugins/raumnebenan": true
	}
}
```

## License

MIT
