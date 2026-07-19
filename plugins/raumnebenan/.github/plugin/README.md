# raumnebenan Agent Plugin

Product thinking resources and MCP integration for VS Code Chat.

## Installation

### Via GitHub Copilot CLI Plugin Marketplace

```bash
/plugin install raumnebenan@raumnebenan-ai-plugins
```

### Via MCP Configuration

Add to your `.mcp.json` or IDE MCP settings:

```json
{
	"mcpServers": {
		"raumnebenan": {
			"type": "http",
			"url": "https://www.raumnebenan.de/mcp"
		}
	}
}
```

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

This plugin exposes tools and prompts from the MCP server. If tools are unavailable, reload the window and ensure the plugin is enabled in Agent Plugins.