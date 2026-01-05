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
- `docs`: Optional setup guide (inline markdown or path/URL) surfaced in the MCP store UI.
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

## Managed MCP Artifacts (Forks)

Forked MCP servers publish prebuilt zip artifacts via GitHub Actions so the desktop app can
install them directly. The standard release workflow is triggered by pushing a `v*` tag and:

1. `npm install`
2. `npm run build`
3. `npm prune --omit=dev`
4. `npm run package:artifact` (creates `artifact/<id>/` with dist + node_modules + metadata)
5. Zip the artifact directory as `<id>-<platform>-<arch>.zip`
6. Upload zip assets to the GitHub release

See the fork workflows for reference:
- `C:\Users\hello\Claude\google-mcp-fork\.github\workflows\release.yml`
- `C:\Users\hello\Claude\xero-mcp-server\.github\workflows\release.yml`

## Updating `registry.json` After a Release

1. Update the entry `version`.
2. Update each artifact's `url`, `filename`, `sha256`, `size`, and `entrypoint`.
3. Bump the registry `version` and `updatedAt` fields at the top level.

Common hash/size commands:

Windows (PowerShell):
```powershell
Get-FileHash .\google-mcp-windows-x86_64.zip -Algorithm SHA256
(Get-Item .\google-mcp-windows-x86_64.zip).Length
```

Windows (cmd):
```cmd
certutil -hashfile google-mcp-windows-x86_64.zip SHA256
for %I in (google-mcp-windows-x86_64.zip) do @echo %~zI
```

macOS:
```bash
shasum -a 256 google-mcp-macos-aarch64.zip
stat -f%z google-mcp-macos-aarch64.zip
```

Linux:
```bash
shasum -a 256 google-mcp-linux-x86_64.zip
stat -c%s google-mcp-linux-x86_64.zip
```

Note: `entrypoint` should point to the JS entry inside the zip (usually `dist/index.js`).
