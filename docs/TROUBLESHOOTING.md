# Troubleshooting

## 401 Unauthorized

Check:

- `Authorization` header is present
- token format is `Bearer <key>`
- key has not expired or been revoked

## MCP connection fails at startup

Check:

- endpoint URL is exactly `https://mcp.adextract.co/mcp`
- TLS certificate is valid
- client supports Streamable HTTP MCP transport

## OAuth flow not starting

Check:

- OAuth metadata endpoints are reachable
- client supports OAuth MCP connector flow
- redirect/callback is allowed by the client

## Server card issues

Check:

- `https://mcp.adextract.co/.well-known/mcp.json` is reachable
- JSON is valid and includes expected fields

## Tool call returns unexpected output

Check:

- request parameters follow tool schema
- platform-specific limits (date range, identifiers, pagination)
- retries for transient provider-side failures

