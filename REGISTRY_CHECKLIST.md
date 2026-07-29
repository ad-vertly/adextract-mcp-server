# MCP Registry Checklist

Use before submitting **Adextract MCP** to the [MCP Registry](https://github.com/modelcontextprotocol/registry) or similar directories.

## Repository

- [ ] README links to `https://mcp.adextract.co/mcp`
- [ ] `server.json` is accurate (name, endpoint, auth, categories)
- [ ] `SECURITY.md` and `SUPPORT.md` present
- [ ] No secrets in repo or commit history

## Hosted service

- [ ] `GET https://mcp.adextract.co/health` → `200`
- [ ] `GET https://mcp.adextract.co/.well-known/mcp.json` → valid server card JSON
- [ ] `GET https://mcp.adextract.co/.well-known/oauth-protected-resource` → valid metadata
- [ ] `GET https://mcp.adextract.co/.well-known/oauth-authorization-server/oauth` → valid metadata (RFC 8414)
- [ ] Valid TLS certificate on `mcp.adextract.co`

## Authentication

- [ ] OAuth flow works (Claude Web or test client)
- [ ] Bearer API key works (Cursor or VS Code)
- [ ] Unauthenticated requests return `401` with `WWW-Authenticate`

## Submission payload

| Field | Value |
|-------|-------|
| Repository | `https://github.com/ad-vertly/adextract-mcp-server` |
| Endpoint | `https://mcp.adextract.co/mcp` |
| Server card | `https://mcp.adextract.co/.well-known/mcp.json` |
| Transport | Streamable HTTP |
| Auth | OAuth 2.0, Bearer |
