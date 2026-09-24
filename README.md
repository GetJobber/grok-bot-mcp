# Jobber MCP Plugin

This repository packages Jobber's hosted MCP server for Cursor and Grok Bot.

## MCP server

The plugin points at Jobber's production MCP endpoint:

```json
{
  "mcpServers": {
    "jobber": {
      "type": "http",
      "url": "https://mcp.getjobber.com/mcp"
    }
  }
}
```

Cursor handles OAuth during installation using Jobber's hosted authorization flow.

## OAuth redirect URIs

The Jobber OAuth app should allow these Cursor redirect URIs:

```text
https://www.cursor.com/agents/mcp/oauth/callback
http://localhost:8787/callback
cursor://anysphere.cursor-mcp/oauth/callback
```

## Local testing

Clone this repository into Cursor's local plugin directory:

```sh
mkdir -p ~/.cursor/plugins/local
git clone https://github.com/GetJobber/grok-bot-mcp.git ~/.cursor/plugins/local/jobber
```

Then reload Cursor, install the Jobber plugin, and complete the OAuth sign-in.

## Publishing

Submit this public repository at:

```text
https://cursor.com/marketplace/publish
```

The plugin manifest is in `.cursor-plugin/plugin.json`, and `mcpServers` is pinned to `./mcp.json`.
