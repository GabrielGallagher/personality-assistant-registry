# Personality Assistant Registry

Registry of MCP servers and reusable templates for the desktop app.

## Files

- `registry.json`: Registry index consumed by the desktop app.
- `templates/`: Human-editable template library (heartbeat tasks, prompts, presets, etc.).

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

## Templates

Templates are included in `registry.json` under the `templates` array for quick app access,
and also stored as JSON files under `templates/` for easier review and editing.

## Install Methods

- `manual`: Requires user steps (shown in UI).
- `command`: The app can run a command (usually `npx`) if Node is available.

Native binaries should include `artifacts` with `url`, `filename`, and `sha256`.
If the artifact is an archive, add `entrypoint` to point to the executable inside the archive.
