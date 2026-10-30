# Installing the IsraBase MCP server (for Cline and other agents)

IsraBase is a hosted remote MCP server. There is nothing to clone, build or run, and no API key.

Add this to `cline_mcp_settings.json` (or your client MCP config):

```json
{
  "mcpServers": {
    "israbase": {
      "type": "streamableHttp",
      "url": "https://israbase.com/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

If your client only runs stdio servers, use the bridge instead:

```json
{
  "mcpServers": {
    "israbase": { "command": "npx", "args": ["-y", "mcp-remote", "https://israbase.com/mcp"] }
  }
}
```

Check the setup: call the `get_stats` tool. It returns registry totals (companies, nonprofits, partnerships).

Limits: read-only, 30 requests per minute per IP.
