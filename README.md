# Tume AI MCP Server

<img src="assets/logo.png" alt="Tume AI" width="96" align="right">

Tume AI gives AI assistants read-only access to energy market data through one hosted [Model Context Protocol](https://modelcontextprotocol.io) server:

- Wholesale power prices, load, generation and fuel mix for ERCOT, PJM, NYISO, CAISO, MISO, SPP, ISO-NE and Ontario (IESO)
- US-wide and global datasets, including EIA data and interconnection queues
- Regulatory dockets from FERC and state commissions
- Solar and wind generation profiles, weather history and forecasts

Queries are SELECT-only and validated before they run. The server reports the current catalogue, so new markets and datasets appear without a client update.

**Server URL:** `https://mcp.tume.ai/mcp` (Streamable HTTP)

## Sign in

The server uses OAuth. Your client opens a Tume AI sign-in page the first time it connects; you need a Tume AI account from [tume.ai](https://tume.ai). There is no API key to copy.

## Connect

### Claude (claude.ai and Claude Desktop)

Settings → Connectors → Add custom connector, then enter `https://mcp.tume.ai/mcp`.

### Claude Code

```bash
claude mcp add --transport http tume-ai https://mcp.tume.ai/mcp
```

### Cursor

Add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "tume-ai": {
      "type": "http",
      "url": "https://mcp.tume.ai/mcp"
    }
  }
}
```

### VS Code

Add this to `.vscode/mcp.json`:

```json
{
  "servers": {
    "tume-ai": {
      "type": "http",
      "url": "https://mcp.tume.ai/mcp"
    }
  }
}
```

### Gemini CLI

```bash
gemini extensions install https://github.com/Tume-AI/tume-ai-mcp
```

### Cline

Add this to `cline_mcp_settings.json`:

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

## Try it

- "What energy market datasets can you access?"
- "What were the latest ERCOT day-ahead prices by zone?"
- "How many projects are in the US interconnection queue?"

## About this repository

This repository holds the client configuration and marketplace manifests for the hosted Tume AI server. The server itself runs at `mcp.tume.ai` and is not part of this repository.

## Links

- Website: [tume.ai](https://tume.ai)
- Privacy policy: [tume.ai/privacy](https://tume.ai/privacy)
- Terms of service: [tume.ai/terms](https://tume.ai/terms)
- MCP Registry: `ai.tume/energy-data`
- Contact: Akintonde Abbas, [akintonde.abbas@tume.ai](mailto:akintonde.abbas@tume.ai)

## License

The files in this repository are released under the [MIT License](LICENSE).
