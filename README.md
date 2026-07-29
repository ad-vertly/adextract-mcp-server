# Adextract MCP Server

[![MCP](https://img.shields.io/badge/MCP-Streamable%20HTTP-blue)](https://modelcontextprotocol.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Connect AI assistants to **Adextract** — search ad libraries across **Meta**, **Google Ads**, **LinkedIn**, and **TikTok**, plus creative analysis with `ad_reader`.

**Hosted endpoint:** `https://mcp.adextract.co/mcp`

---

## Installation

### Hosted MCP (recommended)

Connect to the Adextract hosted server:

```
https://mcp.adextract.co/mcp
```

Get your API key at [adextract.co](https://adextract.co) (account → API keys).

### Cursor

Add to `~/.cursor/mcp.json` or project `.cursor/mcp.json`:

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

### VS Code

Add to `.vscode/mcp.json`:

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

### Claude Web (OAuth)

1. Open Claude → **Settings** → **Connectors** → **Add custom connector**
2. Name: `ad-extract`
3. URL: `https://mcp.adextract.co/mcp`
4. Sign in and approve when prompted — no API key in the URL.

### Claude Desktop (`mcp-remote`)

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

More clients and config paths: [docs/CLIENT_SETUP.md](docs/CLIENT_SETUP.md)

---

## Available Tools

| Tool | Platform | Description |
|------|----------|-------------|
| `search_meta_ads` | Meta | Search Facebook & Instagram ads |
| `search_meta_pages` | Meta | Discover pages and location IDs |
| `get_meta_page_info` | Meta | Page transparency and metadata |
| `get_meta_ad_details` | Meta | EU/UK ad transparency details |
| `search_google_ads` | Google | Google Ads Transparency Center |
| `search_google_ads_advertisers` | Google | Advertiser and domain search |
| `get_google_ad_details` | Google | Creative details |
| `get_google_ads_advertiser_info` | Google | Advertiser profile from Search ads |
| `search_linkedin_ads` | LinkedIn | LinkedIn Ad Library |
| `search_tiktok_ads` | TikTok | TikTok Ads Library |
| `search_tiktok_advertisers` | TikTok | TikTok advertiser discovery |
| `get_tiktok_ad_details` | TikTok | Targeting and creative details |
| `ad_reader` | All | Analyze image/video creatives (format, audience, emotion, archetypes) |

Full reference: [docs/TOOLS.md](docs/TOOLS.md)

---

## Prompts & Resources

Built-in MCP prompts for common workflows:

- `adextract_top_ads_for_brand`
- `adextract_competitor_benchmark`
- `adextract_channel_strategy`
- `adextract_analyze_ad_url`
- `adextract_schedule_watchlist`

Resources include agent skill instructions and prompt-pack references (`adextract://skill/main`, etc.).

---

## Authentication

| Method | Best for |
|--------|----------|
| **OAuth 2.0** | Claude Web and OAuth-capable connectors |
| **Bearer API key** | Cursor, VS Code, Claude Desktop, `mcp-remote` |

Discovery endpoints:

- `https://mcp.adextract.co/.well-known/oauth-protected-resource`
- `https://mcp.adextract.co/.well-known/oauth-authorization-server/oauth`

Server card (registry / client discovery):

- `https://mcp.adextract.co/.well-known/mcp.json`

---

## Example prompts

```
Show me the latest Nike ads on Facebook in the US.
→ search_meta_ads({ q: "nike", country: "US", active_status: "active" })

Find Google ads for tesla.com from the last 30 days.
→ search_google_ads({ domain: "tesla.com", time_period: "last_30_days" })

Analyze this ad creative URL with ad_reader.
→ ad_reader({ url: "https://..." })
```

---

## Documentation

| Doc | Purpose |
|-----|---------|
| [docs/CLIENT_SETUP.md](docs/CLIENT_SETUP.md) | Per-client configuration |
| [docs/TOOLS.md](docs/TOOLS.md) | Tools, prompts, resources |
| [docs/TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md) | Common errors and fixes |
| [REGISTRY_CHECKLIST.md](REGISTRY_CHECKLIST.md) | Pre-submission checklist |
| [SECURITY.md](SECURITY.md) | Security policy |
| [SUPPORT.md](SUPPORT.md) | How to get help |

---

## Links

- **Website:** [adextract.co](https://adextract.co)
- **MCP endpoint:** `https://mcp.adextract.co/mcp`
- **Repository:** [github.com/ad-vertly/adextract-mcp-server](https://github.com/ad-vertly/adextract-mcp-server)

Built with ❤️ by [Adextract](https://adextract.co)
