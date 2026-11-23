# Install Nanobananana MCP in Cline

Use a Cline CLI version with Streamable HTTP MCP support. Create an API key in [Nanobananana settings](https://nanobananana.com/account/api-tokens) and set `NANOBANANA_API_KEY` in the shell where you run Cline. Keep the key out of chat, logs, and source control. The user supplies the key through their own shell.

```sh
cline mcp add nanobanana --transport streamable-http https://nanobananana.com/api/mcp   --header "Authorization: Bearer ${NANOBANANA_API_KEY}" --yes
cline mcp list
```

Cline saves the Authorization header in its local MCP settings. Treat that file as sensitive. Reload Cline if the server was added from a separate session.

To verify the server without paying for a generation, ask Cline to call `nano_list_models` and list available models. Remove the integration with `cline mcp remove nanobanana --yes`.
