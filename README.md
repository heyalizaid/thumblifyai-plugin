<div align="center">
  <img src="./logo.png" alt="ThumblifyAI logo" width="96" />

  # ThumblifyAI Plugin

  **An AI Thumbnail Maker for your AI agents.**

  Create, style-match, recreate, and refine YouTube thumbnails with ThumblifyAI's hosted MCP server.
</div>

ThumblifyAI is an AI Thumbnail Maker for creators. This repository packages its hosted [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) server as a portable Agent Plugin for compatible agent apps, including Cursor, Claude, and other MCP clients.

## Available tools

Connect your ThumblifyAI account to use these MCP tools. Credit costs shown are per successful operation; account plan limits apply.

| Tool | What it does | Credits |
| --- | --- | ---: |
| `generate_thumbnail` | Generate a thumbnail from a text prompt. Supports 16:9 and 9:16 aspect ratios. | 1 |
| `style_match_thumbnail` | Create a thumbnail using the visual style of 1–3 reference images. | 2 |
| `ultra_edit` | Refine or edit an image using reference images and a prompt. | 1 |
| `recreate_thumbnail` | Recreate a reference thumbnail with your trained ThumblifyAI face model. | 3 |
| `sketch_to_thumbnail` | Turn a sketch into a polished thumbnail. | 2 |
| `find_thumbnail_inspirations` | Find relevant thumbnail inspiration for a video idea. | 0 |

Tool availability, input requirements, and credit costs can change. Your connected agent discovers the current tool definitions from the MCP server.

## Install in Cursor

After the repository is accepted into the Cursor Marketplace:

1. Open **Customize** in Cursor and go to the plugin marketplace.
2. Search for **ThumblifyAI** and select **Install**.
3. When Cursor connects to the MCP server, choose **OAuth** and sign in to your ThumblifyAI account.
4. Start a chat and ask Cursor to create, style-match, recreate, or edit a thumbnail with ThumblifyAI.

For local evaluation before marketplace listing, add the remote MCP server in Cursor's MCP settings using `https://api.thumblifyai.com/mcp`, then authenticate with OAuth when Cursor prompts you.

This plugin uses the portable Agent Plugins format, with `plugin.json` and `mcp.json` at the repository root. It does not need a `.cursor-plugin/` directory.

## OAuth and API key authentication

The hosted MCP endpoint is:

```text
https://api.thumblifyai.com/mcp
```

OAuth is the recommended sign-in method for compatible MCP clients. It connects the client to your existing ThumblifyAI account; no API key needs to be copied into the plugin or committed to this repository. Some clients may offer different authentication flows. Where OAuth is unavailable, ThumblifyAI also supports bearer API key authentication if the client supports custom authorization headers.

## Other compatible agent apps

Agent Plugin support varies by app. Apps that support the open Agent Plugins specification can use this portable package. Other MCP-compatible apps can connect directly to the endpoint above and use OAuth when offered by the client. See the [ThumblifyAI MCP setup guide](https://thumblifyai.com/agents/mcp-server) for client-specific instructions.

## Repository contents

```text
thumblifyai-plugin/
├── plugin.json
├── mcp.json
├── README.md
├── LICENSE
└── logo.png
```

Skills are not included yet. They can be added later under `skills/<skill-name>/SKILL.md`.

## Links

- [ThumblifyAI](https://thumblifyai.com)
- [MCP server and setup guide](https://thumblifyai.com/agents/mcp-server)
- [Product Hunt](https://www.producthunt.com/products/thumblifyai)
- [Cursor Marketplace submission](https://cursor.com/marketplace/publish)

## License

MIT. See [LICENSE](./LICENSE).
