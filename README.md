# My MCP Servers Project

Small project on basic knowledge on how to create and add MCPs to a client such as Claude Desktop

## Quick Start

### Prerequisites
- Node.js 18+ installed
- Python 3.x for MCP SDK

### Installation
```powershell
cd C:\Users\rafae\Documents\Projects\frontend-masters\my-mcp
npm install
```

## Project Structure

| File | Purpose |
|------|---------|
| style-checker.js | Code review style checker |
| weather.js | Weather data server |
| mcp.js | Main MCP entry point |

## Usage with Claude Desktop

### Example: Style Checker Configuration

Add this to `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "styleguide-server": {
      "command": "C:\\Program Files\\nodejs\\node",
      "args": ["C:\\Users\\rafae\\Documents\\Projects\\frontend-masters\\my-mcp\\style-checker.js"],
      "env": {
        "NODE_OPTIONS": "--no-deprecation"
      }
    }
  }
}
```

### Full Configuration with All Servers

```json
{
  "mcpServers": {
    "demo-server": {
      "command": "C:\\Program Files\\nodejs\\node",
      "args": ["C:\\Users\\rafae\\Documents\\Projects\\frontend-masters\\my-mcp\\mcp.js"],
      "env": {
        "NODE_OPTIONS": "--no-deprecation"
      }
    },
    "weather-server": {
      "command": "C:\\Program Files\\nodejs\\node",
      "args": ["C:\\Users\\rafae\\Documents\\Projects\\frontend-masters\\my-mcp\\weather.js"],
      "env": {
        "NODE_OPTIONS": "--no-deprecation"
      }
    },
    "styleguide-server": {
      "command": "C:\\Program Files\\nodejs\\node",
      "args": ["C:\\Users\\rafae\\Documents\\Projects\\frontend-masters\\my-mcp\\style-checker.js"],
      "env": {
        "NODE_OPTIONS": "--no-deprecation"
      }
    }
  }
}
```

## Debugging Path Issues

If you see: `ENOENT: no such file or directory, open 
/C:/Users/...`

**Fix:** Use `path.resolve(process.cwd(), "./style-guide.md")` instead of `new URL(import.meta.url)`

---

Built with Codex Desktop ✨
