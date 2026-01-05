# Heartbeat Task Templates

Each file describes a reusable heartbeat task. Fields:
- `id`
- `type`: `heartbeat-task`
- `name`
- `summary`
- optional `tags`
- optional `requires` (e.g., `mcp:slack-mcp`)
- `task` with `prompt`, `intervalMinutes`, `useGlobalSources`, `schemaTargets`
