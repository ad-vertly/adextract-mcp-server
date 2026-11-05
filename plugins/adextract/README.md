# adextract for Hermes

Connects your agent to the adextract remote MCP server (`https://mcp.adextract.co/mcp`) for competitor ad research across the public ad libraries of Meta, Google, LinkedIn and TikTok. It can also analyze any ad image or video for format, audience, emotion and message.

This package is configuration only. It has no local code and no background process. It contains an `mcp.json` that points at the hosted server, plus five skills that explain how to research each platform.

## Install

```
hermes plugins install adextract
hermes mcp login adextract
```

Sign in with Google in the browser window that opens. New accounts get free starter credits.

## What you get

13 tools: ad search, advertiser and page lookup, single-ad details, and `ad_reader` for creative analysis. Every tool is annotated read-only. Nothing is posted, bought or changed anywhere.

## Disclosure

- **Network:** every tool call goes to `mcp.adextract.co`. Nothing else is contacted by this package.
- **Account:** sign-in is OAuth 2.0 with PKCE. Hermes stores and refreshes the token.
- **What the server logs:** your account email, credit balance, and a usage record of tool name, time, success and credits used. Search queries are not stored.
- **Cost:** each successful call uses one credit. Failed calls are not charged.
- **No self-updating code:** the package never fetches or replaces its own files. The tool list is served by the remote server at runtime and is not covered by the pinned commit.
- **Trust:** the server is marked `untrusted`, so Hermes asks before any write-capable tool. adextract has none.
- **Telemetry:** none from this package.

Support: hello@adextract.co. Privacy: https://adextract.co/privacy. Terms: https://adextract.co/terms.

License: MIT.
