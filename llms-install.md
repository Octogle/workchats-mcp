# Installing the Workchats MCP server (for AI agents)

Workchats is a hosted remote MCP server. There is nothing to clone, build or run locally, and no API key.

1. Add this server entry to the client's MCP settings (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "workchats": {
      "type": "streamableHttp",
      "url": "https://mcp.workchats.com/mcp"
    }
  }
}
```

   For read-only access use `https://mcp.workchats.com/mcp/readonly`.

2. Start the server. The client receives a 401 with OAuth metadata and opens Workchats in the user's browser (OAuth 2.1 with PKCE; the client registers itself dynamically).
3. Ask the user to sign in to Workchats, pick a company and click **Allow**. Do not ask the user for a password, code or token in chat.
4. When connected, call a read tool such as `list_my_conversations` to confirm.

Requirements: the user needs a Workchats employee account, and their company admin must have turned on AI assistants. If the company is greyed out on the consent screen, the admin has not enabled it.
