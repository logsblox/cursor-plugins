---
name: logsblox-mcp
description: Connect to the Logsblox MCP server to list projects and search immutable logs.
---

# Use the Logsblox MCP server

Use this skill when a user wants an agent to inspect Logsblox projects or search stored logs.

## Endpoint

`https://mcp.logsblox.com`

Transport: Streamable HTTP. Server card: `https://logsblox.com/.well-known/mcp/server-card.json`.

## Auth

The server is an OAuth-protected resource.

1. Fetch `https://mcp.logsblox.com/.well-known/oauth-protected-resource`
2. Use the listed `authorization_servers` issuer
3. Register a client at `https://api.logsblox.com/auth/v1/oauth/clients/register` if you do not already have one
4. Complete the authorization-code flow (consent UI: `https://app.logsblox.com/oauth/consent`)
5. Call MCP with `Authorization: Bearer <access_token>`

Humans create an account at `https://app.logsblox.com/auth?mode=signup`. See `https://logsblox.com/auth.md`.

In Cursor, install the Logsblox plugin from Browse MCPs. That install connects this server.

## Tools

Call `list_projects` first. Then use a returned `project_id` with:

- `project_info`
- `summarize_logs` before `search_logs` (facet filters only)
- `top_log_patterns` on a window of at most one hour
- `search_logs` (requires `start_date` and `end_date`)
- `list_recent_errors`

Do not invent project IDs.
