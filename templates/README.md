# Templates

This folder contains optional templates that the desktop app can import.

## Layout
- `heartbeat-tasks/` - Background task templates for the heartbeat scheduler.
- `assistant-prompts/` - Reusable system prompt snippets.
- `assistant-presets/` - Starter configs (prompt + defaults + tags).
- `skills/` - Claude skill packs (metadata + install notes).
- `plugins/` - Claude plugin packs (metadata + install notes).

The registry index (`registry.json`) also includes a `templates` array so the app can fetch
templates in one request. The JSON files here are the human-editable sources.
