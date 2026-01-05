# Xero MCP setup

Use this MCP to access Xero accounting data.

## What you need
- A Xero developer app
- OAuth client ID and client secret

## Steps
1. Create an app in the Xero developer portal.
2. Copy the client ID and client secret.
3. Set `XERO_CLIENT_ID` and `XERO_CLIENT_SECRET` in the MCP Store.
4. Optional: set `XERO_READONLY` to true to limit write operations.
5. Optional: if you manage OAuth externally, set `XERO_CLIENT_BEARER_TOKEN`.

If you use the managed install in the desktop app, you do not need `XERO_MCP_PATH`.

## Environment variables
- `XERO_CLIENT_ID` (required)
- `XERO_CLIENT_SECRET` (required)
- `XERO_CLIENT_BEARER_TOKEN` (optional)
- `XERO_READONLY` (optional)

## Links
- https://developer.xero.com/
