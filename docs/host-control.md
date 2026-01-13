# Host Control MCP

Built-in host automation for input, screen, window, clipboard, system, and accessibility actions.

## Availability
- Bundled with the desktop app (no install)
- Enable per agent in Agent Settings -> Connectors
- Configure global defaults in Settings -> Host Control

## Permissions (macOS)
- Accessibility: required for keyboard/mouse and UI element access
- Screen Recording: required for screenshots and OCR

## Capabilities
- Input control (type, click, scroll)
- Screen capture and OCR
- Window management
- Clipboard read/write
- System open/notifications
- Accessibility element targeting

## Safety Model
- Per-agent capability toggles
- Allowlists (apps/window titles/hotkeys)
- User presence guard
- Rate limits
- Approval prompts
- Audit log with retention

## Tooling Notes
- Input tools require a target window
- Untargeted input is denied by default
- Use `host_get_capabilities` for runtime support checks

## Troubleshooting
- If permissions are missing, open System Settings and re-check
- Linux Wayland: limited support for input and screenshots
