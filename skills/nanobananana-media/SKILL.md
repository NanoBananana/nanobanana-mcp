---
name: nanobananana-media
description: Generate or edit images and generate videos with Nanobananana MCP. Use when a user asks to make an image, edit an image or create a video using Nanobananana.
---

# Nanobananana Media

Use the Nanobananana MCP tools. If the tools are unavailable, share the [connection instructions](https://github.com/NanoBananana/nanobanana-mcp#connect).

1. Choose a model with `nano_list_models` and check its inputs with `nano_get_model`.
2. Import a reference image from an HTTPS URL with `nano_upload_image`. For a local image, use the [Nanobananana CLI](https://www.npmjs.com/package/@nanobananana/cli).
3. Estimate the cost with `nano_estimate_cost` and get the user's approval before submitting the generation.
4. Submit the image or video job and check it with `nano_get_generation`. Return the result links. If submission times out, check `nano_list_generations` before retrying.
