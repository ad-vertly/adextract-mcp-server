# Security Policy

## Reporting a vulnerability

Report security issues privately — do not open public issues for active vulnerabilities.

- **Email:** security@adextract.co
- **Subject:** `Security report: Adextract MCP`
- **Include:** affected endpoint, reproduction steps, impact, suggested fix (if any)

We aim to acknowledge reports within 48 hours.

## Scope

In scope:

- `https://mcp.adextract.co/mcp` and subpaths
- OAuth authorization and token endpoints
- Authentication and authorization logic on the hosted service

Out of scope:

- Third-party ad library APIs (Meta, Google, LinkedIn, TikTok upstream)
- Client-side MCP configuration on user machines

## Practices

- Protected operations require valid OAuth or bearer credentials.
- API keys are hashed at rest; raw keys are shown once at creation.
- Rotate keys immediately if you suspect exposure.
- Never commit secrets to this repository.
