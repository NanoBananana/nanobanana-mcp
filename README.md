# Nanobananana MCP

Generate and edit images and generate videos with Nanobananana. This repository contains MIT-licensed client setup and integration metadata.

- [Image generation and editing](https://nanobananana.com/zh/models/image)
- [Video generation](https://nanobananana.com/zh/models/video)
- [Nanobananana](https://nanobananana.com/zh)

## Connect

Create a token under [Account → API tokens](https://nanobananana.com/account/api-tokens). Connect with Streamable HTTP at `https://nanobananana.com/api/mcp` and send `Authorization: Bearer YOUR_API_KEY`. Generation tools use your account credits.

### Claude Code

```sh
claude mcp add --transport http nanobananana https://nanobananana.com/api/mcp --header "Authorization: Bearer $NANOBANANA_API_KEY"
```

Install the accompanying skill with `/plugin marketplace add NanoBananana/nanobanana-mcp` and then `/plugin install nanobananana-creative@nanobananana`.

### Codex

Add this to `~/.codex/config.toml`:

```toml
[mcp_servers.nanobananana]
url = "https://nanobananana.com/api/mcp"
bearer_token_env_var = "NANOBANANA_API_KEY"
```

Install the accompanying skill with `codex plugin marketplace add NanoBananana/nanobanana-mcp` and then `codex plugin add nanobananana-creative@nanobananana`.

### Cursor

Set `NANOBANANA_API_KEY` in the environment that starts Cursor. Add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "nanobananana": {
      "url": "https://nanobananana.com/api/mcp",
      "headers": {
        "Authorization": "Bearer ${env:NANOBANANA_API_KEY}"
      }
    }
  }
}
```

### Gemini CLI

```sh
gemini extensions install https://github.com/NanoBananana/nanobanana-mcp
```

Enter your token without the Bearer prefix when prompted.

### Cline

Create a token and set `NANOBANANA_API_KEY` in your shell. Run:

```sh
cline mcp add nanobananana --transport streamable-http https://nanobananana.com/api/mcp \
  --header "Authorization: Bearer $NANOBANANA_API_KEY" --yes
```

### Kiro

Set `NANOBANANA_API_KEY` in the environment that starts Kiro, restart Kiro, and open [Add Nanobananana to Kiro](https://kiro.dev/launch/mcp/add?name=nanobananana&config=%7B%22url%22%3A%22https%3A%2F%2Fnanobananana.com%2Fapi%2Fmcp%22%2C%22headers%22%3A%7B%22Authorization%22%3A%22Bearer%20%24%7BNANOBANANA_API_KEY%7D%22%7D%7D).

## Tools

| Tool                    | Purpose                                 |
| ----------------------- | --------------------------------------- |
| `nano_account_status`   | Check plan, credits, and API limits.    |
| `nano_list_models`      | Discover image and video models.        |
| `nano_get_model`        | Inspect a model's parameters.           |
| `nano_estimate_cost`    | Estimate generation cost in credits.    |
| `nano_upload_image`     | Import an HTTPS image URL as an input.  |
| `nano_generate_image`   | Submit an image generation or edit job. |
| `nano_generate_video`   | Submit a video generation job.          |
| `nano_get_generation`   | Check a job's status or result.         |
| `nano_list_generations` | Find recent jobs.                       |

[Privacy Policy](https://nanobananana.com/privacy) · [Support](mailto:hi@nanobananana.com)

See [Cline installation](llms-install.md) for Streamable HTTP setup and a read-only model-list check.
