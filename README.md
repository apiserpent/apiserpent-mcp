# apiserpent-mcp

[![apiserpent/apiserpent-mcp MCP server](https://glama.ai/mcp/servers/apiserpent/apiserpent-mcp/badges/score.svg)](https://glama.ai/mcp/servers/apiserpent/apiserpent-mcp)

An [MCP](https://modelcontextprotocol.io) server for the [Serpent API](https://apiserpent.com) that gives AI agents real-time Google search results as structured JSON.

## Tools

| Tool | Description | Parameters |
| --- | --- | --- |
| `google_search` | Search Google through the Serpent API and return real-time web results. | `query` (string, required) — the web search query. |

## Requirements

- Node.js 18 or newer
- A Serpent API key — get one at [apiserpent.com](https://apiserpent.com)

## Installation

```bash
git clone https://github.com/apiserpent/apiserpent-mcp.git
cd apiserpent-mcp
npm install
```

## Configuration

The server reads your API key from the `APISERPENT_API_KEY` environment variable:

```bash
export APISERPENT_API_KEY="your-api-key"
```

The key is sent to the Serpent API in the `X-API-Key` header.

## Usage

Run the server over stdio:

```bash
npm start
```

### Claude Desktop

Add the following to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "apiserpent": {
      "command": "node",
      "args": ["/absolute/path/to/apiserpent-mcp/index.js"],
      "env": {
        "APISERPENT_API_KEY": "your-api-key"
      }
    }
  }
}
```

## License

Released under the [MIT License](LICENSE).
