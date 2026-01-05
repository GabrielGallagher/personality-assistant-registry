# Google Workspace MCP setup

Use this MCP to access Gmail, Calendar, Drive, Docs, Sheets, and Slides via OAuth.

## What you need
- A Google Cloud project
- An OAuth client with a downloaded `credentials.json`
- The Google APIs you want enabled (Gmail, Calendar, Drive, Docs, Sheets, Slides)

## Steps
1. Open the Google Cloud Console and go to APIs & Services -> Credentials.
2. Create an OAuth client ID (Desktop app) and download `credentials.json`.
3. Enable the APIs you plan to use in the same project.
4. In the MCP Store, set one of:
   - `GOOGLE_MCP_CREDENTIALS_PATH` to the file path, or
   - `GOOGLE_MCP_CREDENTIALS_JSON` with the file contents (advanced).
5. Optional: limit services via `GOOGLE_MCP_SERVICES` (comma list or `all`).
6. Optional: select write scopes using the Gmail/Calendar toggles.

If you use the managed install in the desktop app, you do not need to set `GOOGLE_MCP_PATH`.

## Environment variables
- `GOOGLE_MCP_CREDENTIALS_PATH` (required unless you paste JSON)
- `GOOGLE_MCP_CREDENTIALS_JSON` (optional, advanced)
- `GOOGLE_MCP_SERVICES` (optional)
- `GOOGLE_MCP_SCOPE_PROFILE` (optional)
- `GOOGLE_MCP_GMAIL_COMPOSE` (optional)
- `GOOGLE_MCP_GMAIL_MODIFY` (optional)
- `GOOGLE_MCP_GMAIL_SEND` (optional)
- `GOOGLE_MCP_CALENDAR_WRITE` (optional)

## Links
- https://console.cloud.google.com/apis/credentials
