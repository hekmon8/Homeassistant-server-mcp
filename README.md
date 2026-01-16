# Home Assistant MCP Server

[![smithery badge](https://smithery.ai/badge/@hekmon8/Homeassistant-server-mcp)](https://smithery.ai/server/@hekmon8/Homeassistant-server-mcp)

## 🌟 Sponsors

| Website | Description |
|---------|-------------|
| [**ProductDirs.com**](https://productdirs.com) | AI Tools Directory & Launch Platform - Free submission service for discovering and promoting AI SaaS products, startups, and developer tools with community-driven rankings |
| [**ThisTools.app**](https://thistools.app) | AI SaaS Discovery Platform - Free listing directory for artificial intelligence software, automation tools, and productivity applications with curated collections |
| [**AIImgCombiner.com**](https://aiimgcombiner.com) | AI-Powered Image Fusion Tool - Free online service for merging and combining photos using artificial intelligence with preset styles and custom prompts for professional results |

A Model Context Protocol (MCP) server for interacting with Home Assistant. This server provides tools to control and monitor your Home Assistant devices through MCP-enabled applications.

<a href="https://glama.ai/mcp/servers/io8m0yc5wq">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/io8m0yc5wq/badge" alt="Home Assistant Server MCP server" />
</a>

This project is part of the AI Model Context Protocol (MCP) ecosystem. For more information and documentation about MCP tools, visit [www.aimcp.info](http://www.aimcp.info).

## Features

- Get device states
- Control device states (on/off)
- Trigger automations
- List available entities

## Installation

### Installing via Smithery

To install Home Assistant MCP Server for Claude Desktop automatically via [Smithery](https://smithery.ai/server/@hekmon8/Homeassistant-server-mcp):

```bash
npx -y @smithery/cli install @hekmon8/Homeassistant-server-mcp --client claude
```

### Manual Installation
1. Clone this repository:
```bash
git clone https://github.com/yourusername/homeassistant-server-mcp.git
cd homeassistant-server-mcp
```

2. Install dependencies:
```bash
npm install
```

3. Build the project:
```bash
npm run build
```

4. Configure the MCP server by adding the following to your MCP settings file (typically located at `~/Library/Application Support/Code/User/globalStorage/saoudrizwan.claude-dev/settings/cline_mcp_settings.json` for VSCode):

```json
{
  "mcpServers": {
    "homeassistant": {
      "command": "node",
      "args": ["/path/to/homeassistant-mcp/homeassistant-server/build/index.js"],
      "env": {
        "HA_URL": "http://your-homeassistant-url:8123",
        "HA_TOKEN": "your-long-lived-access-token"
      }
    }
  }
}
```

Replace `your-homeassistant-url` and `your-long-lived-access-token` with your Home Assistant instance URL and access token.

## Usage

The server provides the following tools:

### 1. Get Device State

```typescript
// Example usage
use_mcp_tool({
  server_name: "homeassistant",
  tool_name: "get_state",
  arguments: {
    entity_id: "light.living_room"
  }
});
```

### 2. Toggle Device State

```typescript
// Example usage
use_mcp_tool({
  server_name: "homeassistant",
  tool_name: "toggle_entity",
  arguments: {
    entity_id: "switch.bedroom",
    state: "on"  // or "off"
  }
});
```

### 3. Trigger Automation

```typescript
// Example usage
use_mcp_tool({
  server_name: "homeassistant",
  tool_name: "trigger_automation",
  arguments: {
    automation_id: "automation.morning_routine"
  }
});
```

### 4. List Entities

```typescript
// Example usage
use_mcp_tool({
  server_name: "homeassistant",
  tool_name: "list_entities",
  arguments: {
    domain: "light"  // optional, filters by domain
  }
});
```

## Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please make sure to update tests as appropriate and follow the existing code style.

## Documentation

For detailed documentation about MCP tools and the ecosystem:
- Visit [www.aimcp.info](http://www.aimcp.info)
- Check the MCP tools directory on the website
- Read the integration guides and best practices

## License

This project is licensed under the MIT License - see below for details:

```
MIT License

Copyright (c) 2024 homeassistant-mcp

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Security

To securely use this server:

1. Always use HTTPS for your Home Assistant instance
2. Keep your access tokens secure and never commit them to version control
3. Regularly rotate your access tokens
4. Use environment variables for sensitive information

## Support

If you encounter any issues or have questions, please:

1. Check the existing issues in the repository
2. Create a new issue if your problem hasn't been reported
3. Provide as much context as possible when reporting issues
4. Visit [www.aimcp.info](http://www.aimcp.info) for additional support resources
