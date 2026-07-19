# raumnebenan Agent Plugin

raumnebenan.de is a resource hub focused on actionable product thinking for product owners, product designers, business analysts, product managers, agile coaches, and user researchers.

- the installable Copilot CLI plugin lives in `plugins/raumnebenan/`
- plugin manifest is in `plugins/raumnebenan/plugin.json`
- marketplace manifest is in `.github/plugin/marketplace.json`
- plugin skill content is in `plugins/raumnebenan/skills/raumnebenan/`
- plugin MCP server config is in `plugins/raumnebenan/.mcp.json`
- the repository root also contains a VS Code extension wrapper that points to the plugin directory above

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
│           └── raumnebenan/
│               └── SKILL.md
└── skills/
    └── raumnebenan/
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
