# adextract for Hermes and OpenClaw

Connects your agent to the adextract remote MCP server (`https://mcp.adextract.co/mcp`) for competitor ad research across the public ad libraries of Meta, Google, LinkedIn and TikTok. It can also analyze any ad image or video for format, audience, emotion and message.

This package is configuration only. It has no local code and no background process. It holds an `mcp.json` that points at the hosted server, a cost table, and five skills that explain how to research each platform.

## Install

1. Create an account at https://app.adextract.co (sign in with Google) and create an API key.
2. Add the key to your Hermes profile's `.env`: `ADEXTRACT_API_KEY=...`
3. `hermes plugins install adextract`

If you would rather sign in with OAuth than use a key, add the server yourself after installing the plugin: `hermes mcp add adextract --url https://mcp.adextract.co/mcp --auth oauth`. A server in your own config replaces the package's entry, and the skills keep working.

New accounts get free starter credits.

## Install on OpenClaw

1. Create an API key at https://app.adextract.co and put `ADEXTRACT_API_KEY=...` in the environment your gateway runs with.
2. `openclaw plugins install clawhub:adextract`

The same package works there: OpenClaw reads it as a bundle, loads the five skills, and connects the same hosted server with the same `Authorization` header.

## What you get

13 tools: ad search, advertiser and page lookup, single-ad details, and `ad_reader` for creative analysis. Every tool is annotated read-only. Nothing is posted, bought or changed anywhere.

## Disclosure

- **Network:** every tool call goes to `mcp.adextract.co`. Nothing else is contacted by this package.
- **Credential:** an API key you create, sent only as an `Authorization` header to `mcp.adextract.co`. Hermes reads it from your profile's environment. The package never reads files or stores anything. Headers are dropped on any cross-origin redirect.
- **Cost:** each successful call uses one credit, declared in `plugin.json` so Hermes can show it. Calls that return an error are normally refunded.
- **What the server logs:** your account email, credit balance, and a usage record of tool name, time, success and credits used. Search queries are not stored.
- **Account emails:** the adextract service may email the account address about the account (welcome, inactivity, expiring credits). The package sends nothing.
- **No self-updating code:** the package never fetches or replaces its own files. The tool list is served by the remote server at runtime and is not covered by the pinned commit.
- **Trust:** the server is marked `untrusted`, so Hermes asks before any write-capable tool. adextract has none.
- **Telemetry:** none from this package.

Support: hello@adextract.co. Privacy: https://adextract.co/privacy. Terms: https://adextract.co/terms.

License: MIT.
