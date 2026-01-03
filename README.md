# Personality Assistant Registry

Opinionated registry of MCP servers for the desktop app.

## Files

- `registry.json`: Registry index consumed by the desktop app.

## Entry Fields

- `id`: Unique ID (kebab-case).
- `name`: Display name.
- `summary`: Short description.
- `homepage`: Project URL.
- `category`: Grouping label.
- `runtime`: Preferred and fallback runtime (`native` or `node`).
- `install`: Install metadata (manual or command).
- `env`: Environment variables expected by the MCP server.

## Install Methods

- `manual`: Requires user steps (shown in UI).
- `command`: The app can run a command (usually `npx`) if Node is available.

Native binaries will be added as registry entries later with SHA256 verification.
