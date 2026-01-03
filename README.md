# Personality Assistant Registry

Opinionated registry of MCP servers for the desktop app.

## Files

- `registry.json`: Registry index consumed by the desktop app.

## Entry Fields

- `id`: Unique ID (kebab-case).
- `name`: Display name.
- `summary`: Short description.
- `version`: MCP release version used for installs.
- `homepage`: Project URL.
- `category`: Grouping label.
- `runtime`: Preferred and fallback runtime (`native` or `node`).
- `install`: Install metadata (manual or command).
- `artifacts`: Optional list of native binaries with SHA256 hashes.
- `env`: Environment variables expected by the MCP server.

## Install Methods

- `manual`: Requires user steps (shown in UI).
- `command`: The app can run a command (usually `npx`) if Node is available.

Native binaries should include `artifacts` with `url`, `filename`, and `sha256`.
If the artifact is an archive, add `entrypoint` to point to the executable inside the archive.
