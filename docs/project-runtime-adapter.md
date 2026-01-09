# Project Runtime Adapter

App-only skill that bridges `.plans` artifacts with the in-app project system.

## Bootstrap Note

Use this skill only when the project management runtime is available in the app.
In repo-only mode, rely on:
- `plans-authoring-governance`
- `project-context-continuity`
- `superpowers-interop` (when Superpowers workflows are active)

## Expected Behavior
- Bind plans/tasks to the active project record in the UI.
- Mirror status updates between `.plans/` and the project dashboard.
- Attach verification artifacts in the UI and keep reports in `.plans/`.
