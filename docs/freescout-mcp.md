# FreeScout MCP setup

Use this MCP to read shared inbox tickets from FreeScout.

## What you need
- A FreeScout instance URL
- An API key for a user
- The FreeScout API module enabled

## Steps
1. Enable the FreeScout API module in your instance.
2. Create an API key for the user who should access the mailbox.
3. Set `FREESCOUT_URL` to the base URL (for example, `https://support.example.com`).
4. Set `FREESCOUT_API_KEY` to the generated API key.

## Environment variables
- `FREESCOUT_URL` (required)
- `FREESCOUT_API_KEY` (required)

## Links
- https://github.com/freescout-helpdesk/freescout/wiki/API
