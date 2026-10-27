# Logsblox for Cursor

Cursor plugin for [Logsblox](https://logsblox.com). It gives agents access to Logsblox projects and immutable application logs through the MCP server that already runs at `https://mcp.logsblox.com`.

This repository is the plugin Cursor indexes. It does not ship a separate MCP server.

## Install

Install **Logsblox** from the Cursor marketplace:

1. In Cursor, open **Browse MCPs**.
2. Search for **Logsblox**.
3. Install the plugin.

Cursor connects to `https://mcp.logsblox.com` and starts sign-in.

## Authentication

Sign in with an existing Logsblox account. Cursor registers an OAuth client and opens the consent screen at `https://app.logsblox.com/oauth/consent`.

Create an account at [https://app.logsblox.com/auth?mode=signup](https://app.logsblox.com/auth?mode=signup) if you need one.

## Tools

Call `list_projects` first. Use a returned `project_id` with the other tools.

| Tool | Use |
| --- | --- |
| `list_projects` | List projects you can access. Call this first. |
| `project_info` | Read one project's details. |
| `summarize_logs` | Volume and facet counts. Facet filters only. Call this before `search_logs`. |
| `top_log_patterns` | Top normalized messages. Use a window of at most one hour. |
| `search_logs` | Matching log lines. Requires `start_date` and `end_date`. |
| `list_recent_errors` | Recent error logs. |

Approval prompts show this server as `plugin-logsblox-logsblox`.

## Links

- Homepage: https://logsblox.com
- MCP endpoint: https://mcp.logsblox.com
- Consent: https://app.logsblox.com/oauth/consent
- Auth notes: https://logsblox.com/auth.md
