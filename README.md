<div align="center">
  <img src="./logo.png" alt="ThumblifyAI logo" width="96" />

  # ThumblifyAI Plugin

  **AI Thumbnail Maker tools for Cursor and compatible agent apps.**

  Generate thumbnail concepts, match visual styles, and refine images through the ThumblifyAI MCP server.
</div>

## What it does

This repository packages ThumblifyAI's hosted Model Context Protocol (MCP) server as a portable Agent Plugin. The server connects to [ThumblifyAI](https://thumblifyai.com), an AI Thumbnail Maker for creators.

Depending on the MCP server version and your account, available workflows include:

- Generate a thumbnail from a prompt.
- Find thumbnail inspiration for a video idea.
- Recreate a reference style with your trained ThumblifyAI face model.
- Turn a sketch into a thumbnail.
- Match the style of reference thumbnails.
- Edit and iterate on existing thumbnails.

Generation and editing may use account credits. Check the tool response and your ThumblifyAI plan for current costs and availability.

## Install in Cursor

1. Open Cursor's **Customize** view and browse or install plugins.
2. Search for **ThumblifyAI** or install this public repository from Cursor's plugin marketplace when it is listed.
3. Sign in to ThumblifyAI and create an API key under **Settings → API Keys**.
4. Configure your MCP client to send the key as `Authorization: Bearer YOUR_API_KEY` when prompted or where that client manages MCP authentication.

The plugin uses the portable Agent Plugins format: root `plugin.json` and `mcp.json`. It does not require a `.cursor-plugin/` directory.

## Authentication

The hosted MCP endpoint is `https://api.thumblifyai.com/mcp`. ThumblifyAI authenticates MCP requests with a bearer API key. The portable Agent Plugins 1.0 format requires literal HTTP header values and does not provide a portable secret-variable mechanism. For that reason, this repository does not contain a key or a fake key placeholder in `mcp.json`.

If your agent app does not prompt for MCP authentication when installing the plugin, add the endpoint in that app's MCP settings and set this header there:

```text
Authorization: Bearer YOUR_API_KEY
```

Keep the API key in the client's secret store or local configuration. Never commit it to this repository. See the [MCP setup guide](https://github.com/heyalizaid/thumblifyai-agent-skills/blob/main/docs/ai-thumbnail-maker-mcp-server.md) for host-specific examples.

## Other agent apps

Agent Plugin compatibility depends on each app's support for the open Agent Plugins specification. The MCP server itself can also be added directly to other MCP-compatible clients using the endpoint and bearer header above. See ThumblifyAI's [agent integration guide](https://thumblifyai.com/agents).

## Repository contents

```text
thumblifyai-plugin/
├── plugin.json
├── mcp.json
├── README.md
├── LICENSE
└── logo.png
```

Skills are intentionally not included yet. They can be added under `skills/<skill-name>/SKILL.md` as they are prepared.

## Product information

- Website: [thumblifyai.com](https://thumblifyai.com)
- Product Hunt: [ThumblifyAI](https://www.producthunt.com/products/thumblifyai)
- Agent setup: [ThumblifyAI Agents](https://thumblifyai.com/agents)

## License

MIT. See [LICENSE](./LICENSE).
