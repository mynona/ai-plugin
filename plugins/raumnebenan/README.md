# raumnebenan Agent Plugin

Product thinking resources and MCP integration for VS Code Chat.

## Installation

### Via GitHub Copilot CLI Plugin Marketplace

```bash
/plugin install raumnebenan@raumnebenan-ai-plugins
```

### Via MCP Configuration

Add to `mcp.json` in one of these locations:

- Workspace: `.vscode/mcp.json`
- Global profile: open via command `MCP: Open User Configuration`

Use this schema (current VS Code):

```json
{
	"servers": {
		"raumnebenan": {
			"type": "http",
			"url": "https://www.raumnebenan.de/mcp"
		}
	}
}
```

Compatibility note: older plugin/mcp examples may use `mcpServers`. Current VS Code MCP config expects `servers`.

The plugin connects to the hosted raumnebenan MCP endpoint. It does not launch a local MCP server for tool calls.

## What this plugin provides

- Skill: search-raumnebenan
- MCP server: raumnebenan (https://www.raumnebenan.de/mcp)

## Updating

The MCP tool surface is served by the hosted endpoint above, so updating a local package is not required for MCP tool calls.

## Usage in chat

- Slash skill command: /raumnebenan search-raumnebenan <your query>
- Natural language (Agent mode): "Use raumnebenan and list the five categories"

## MCP tools

This plugin exposes tools and prompts from the MCP server. If tools are unavailable:

1. Run `MCP: List Servers` and verify `raumnebenan` is present and enabled.
2. Run `MCP: Reset Trust` and trust the server again.
3. Ensure the server exists either in workspace `.vscode/mcp.json` or global user `mcp.json`.
4. Reload VS Code window.
