# Nanobananana for DeepSeek Harness (`@nanobananana/dsh-plugin`)

A DeepSeek Harness (DSH) bundle plugin that adds the Nanobananana remote MCP server to a DSH profile via `dsh.bundle.patch`, enabling image generation, image editing, and video generation in DSH.

- **MCP Endpoint:** `https://nanobananana.com/api/mcp` (Streamable HTTP, 10s startup timeout)
- **Compatibility:** `dsh >=0.2.2-rc.5 <0.3.0`

## Installation

Install into the DSH profile you use (for example, `tui`):

```sh
dsh plugin --profile tui add @nanobananana/dsh-plugin
```

## Configuration

Set `NANOBANANA_API_KEY` to your Nanobananana API key in the environment or DSH credential store where DSH runs, then start or restart DSH (`dsh tui`).

- DSH reads `NANOBANANA_API_KEY` through its credentials provider and sends `Authorization: Bearer <token>` when connecting. Resolved secrets are not written to the composed configuration.
- If the credential is not set yet, the MCP client waits until it is configured.
- To create or manage API keys, see [Nanobananana API tokens](https://nanobananana.com/account/api-tokens).

## Removal

```sh
dsh plugin --profile tui remove @nanobananana/dsh-plugin
```

## License

[MIT](./LICENSE)

[Visit Nanobananana](https://nanobananana.com/zh)
