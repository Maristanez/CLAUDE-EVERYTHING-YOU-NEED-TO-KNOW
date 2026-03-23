# Setting Up MCP Servers

## What Is MCP?

Model Context Protocol (MCP) gives Claude **access** to external tools and data. While skills teach Claude how to do things, MCP servers connect Claude to live systems — search engines, databases, browsers, and more.

## Configuration

MCP servers are configured in Claude Code's settings files:

### Project-Level (recommended for team sharing)

`.claude/settings.json`:

```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["-y", "package-name"],
      "env": {
        "API_KEY": "your-key"
      }
    }
  }
}
```

### User-Level (personal settings)

`~/.claude/settings.json` — same format, applies to all projects.

## Recommended MCP Servers

### 1. Context7 — Live Library Docs (No API Key Needed)

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    }
  }
}
```

**Why:** Eliminates hallucinated API calls by injecting current documentation.

### 2. Tavily — AI-Optimized Search

```json
{
  "mcpServers": {
    "tavily": {
      "command": "npx",
      "args": ["-y", "tavily-mcp"],
      "env": {
        "TAVILY_API_KEY": "your-key"
      }
    }
  }
}
```

**Why:** Clean structured search data instead of raw HTML. Get a key at [tavily.com](https://tavily.com).

### 3. Task Master AI — Project Management

```json
{
  "mcpServers": {
    "taskmaster": {
      "command": "npx",
      "args": ["-y", "task-master-ai"]
    }
  }
}
```

**Why:** Breaks PRDs into structured tasks with dependencies.

### 4. MCP Playwright — Browser Automation

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["-y", "@anthropic-ai/mcp-playwright"]
    }
  }
}
```

**Why:** Let Claude control a browser for testing and scraping.

### 5. Codebase Memory — Knowledge Graph

```json
{
  "mcpServers": {
    "codebase-memory": {
      "command": "npx",
      "args": ["-y", "codebase-memory-mcp"]
    }
  }
}
```

**Why:** Persistent knowledge graph of your codebase across sessions.

## Multiple Servers

You can run multiple MCP servers simultaneously:

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    },
    "tavily": {
      "command": "npx",
      "args": ["-y", "tavily-mcp"],
      "env": { "TAVILY_API_KEY": "your-key" }
    }
  }
}
```

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Server not connecting | Check `npx` is available and Node.js 18+ installed |
| Tools not appearing | Restart Claude Code after config changes |
| API key errors | Verify env vars are set correctly |
| Slow startup | Some servers download on first run — wait for initial setup |

## Building Custom MCP Servers

Use [fastmcp](https://github.com/jlowin/fastmcp) to build your own:

```python
from fastmcp import FastMCP

mcp = FastMCP("my-custom-server")

@mcp.tool()
def search_docs(query: str) -> str:
    """Search internal documentation."""
    # Your implementation
    return results
```
