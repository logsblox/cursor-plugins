# Logsblox

Cursor plugin for [Logsblox](https://logsblox.com). It lists projects and reads immutable application logs through `https://mcp.logsblox.com`.

## Install

Install **Logsblox** from Cursor **Browse MCPs**. Cursor connects to `https://mcp.logsblox.com` and starts sign-in.

## Authentication

Sign in with an existing Logsblox account. Consent is at `https://app.logsblox.com/oauth/consent`.

Create an account at [https://app.logsblox.com/auth?mode=signup](https://app.logsblox.com/auth?mode=signup) if you need one.

## Tools

Call `list_projects` first. Use a returned `project_id` with:

- `project_info`
- `summarize_logs` before `search_logs` (facet filters only)
- `top_log_patterns` on a window of at most one hour
- `search_logs` (requires `start_date` and `end_date`)
- `list_recent_errors`
