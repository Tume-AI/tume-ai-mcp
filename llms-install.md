# Installing the Tume AI MCP server

Tume AI is a hosted remote MCP server. There is nothing to clone, build or run locally, and no API key or environment variable to set.

1. Add this entry to the MCP settings file (for Cline, `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "tume-ai": {
      "type": "streamableHttp",
      "url": "https://mcp.tume.ai/mcp"
    }
  }
}
```

2. Save the file. The client connects and opens the Tume AI sign-in page in the browser (OAuth). The user signs in with their Tume AI account from https://tume.ai.

3. Verify the connection by calling the `list_markets` tool. It returns the available energy markets and datasets.

If the connection returns 401 before sign-in, that is expected: the server requires OAuth and the client starts the sign-in flow from that response.
