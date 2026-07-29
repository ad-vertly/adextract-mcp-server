# Client Setup Guide

**Endpoint:** `https://mcp.adextract.co/mcp`

Create an API key at [adextract.co](https://adextract.co) unless your client uses OAuth (e.g. Claude Web).

---

## Cursor

**Config file:** `~/.cursor/mcp.json` or `.cursor/mcp.json` in your project  
**Settings:** Cursor → Features → MCP

```json
{
  "mcpServers": {
    "ad-extract": {
      "url": "https://mcp.adextract.co/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

---

## VS Code

**Config file:** `.vscode/mcp.json` (workspace) or user MCP settings

```json
{
  "servers": {
    "ad-extract": {
      "type": "http",
      "url": "https://mcp.adextract.co/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

---

## Claude Web (OAuth)

1. Claude.ai → **Settings** → **Connectors** → **Add custom connector**
2. **Name:** `ad-extract`
3. **URL:** `https://mcp.adextract.co/mcp` (no API key in URL)
4. Connect → sign in on adextract.co when redirected → approve access

OAuth discovery (for client implementers):

- `https://mcp.adextract.co/.well-known/oauth-protected-resource`
- `https://mcp.adextract.co/.well-known/oauth-authorization-server/oauth` (RFC 8414 for issuer `https://mcp.adextract.co/oauth`)

---

## Claude Desktop

Uses `mcp-remote` as a stdio bridge to the hosted HTTP endpoint.

**Config:** `%APPDATA%\Claude\claude_desktop_config.json` (Windows) or `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS)

```json
{
  "mcpServers": {
    "ad-extract": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.adextract.co/mcp",
        "--header",
        "Authorization: Bearer YOUR_API_KEY"
      ]
    }
  }
}
```

---

## Windsurf

**Config:** `~/.codeium/windsurf/mcp_config.json`

```json
{
  "mcpServers": {
    "ad-extract": {
      "serverUrl": "https://mcp.adextract.co/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

---

## Verify connection

1. Open a new chat in your client.
2. Confirm Adextract tools appear in the tool list.
3. Try: *"Search active Nike ads on Meta in the US."*

Issues? See [TROUBLESHOOTING.md](TROUBLESHOOTING.md).
