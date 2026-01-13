# OpenRouter Image Generation MCP

Deprecated: use the core connector openrouter-image-gen instead.

Image generation connector for OpenRouter image models (default: Gemini 2.5 Flash Image Preview).

## Setup

1. Install the connector from the registry.
2. Set `OPENROUTER_API_KEY` in the connector environment.
3. Enable the connector for your agent.

## Required Environment Variables

- `OPENROUTER_API_KEY` (required): OpenRouter API key (starts with `sk-or-`).

## Notes

- This connector uses OpenRouter's chat completions endpoint for image generation.
- Provide model overrides via the `model` field in `generate_image`.
- Save output files with `save_to_file: true`.

