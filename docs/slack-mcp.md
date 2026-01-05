# Slack MCP setup

This MCP uses a Slack user token (xoxp) to search, read, and post messages.

## What you need
- A Slack app installed in your workspace
- A User OAuth token (starts with `xoxp-`)

## Steps
1. Create a Slack app at https://api.slack.com/apps.
2. Add the user token scopes needed for the actions you want (read history, search, post).
3. Install the app to your workspace.
4. Copy the User OAuth token and set `SLACK_MCP_XOXP_TOKEN`.

## Environment variables
- `SLACK_MCP_XOXP_TOKEN` (required)

## Links
- https://api.slack.com/apps
