# MCP Servers Overview

Model Context Protocol (MCP) servers give Claude **access** to external tools and data. Unlike skills (which teach Claude how to do things), MCP servers connect Claude to live systems.

---

## 1. Tavily — AI-Optimized Search

**Repo:** [tavily-ai/tavily-mcp](https://github.com/tavily-ai/tavily-mcp)

A search engine built specifically for AI agents. Returns clean, structured data instead of blue links.

### Four Tools

| Tool | Purpose |
|------|---------|
| `search` | Web search with structured results |
| `extract` | Pull specific content from URLs |
| `crawl` | Deep-crawl entire sites |
| `map` | Site structure mapping |

### Setup

```json
{
  "mcpServers": {
    "tavily": {
      "command": "npx",
      "args": ["-y", "tavily-mcp"],
      "env": {
        "TAVILY_API_KEY": "your-api-key"
      }
    }
  }
}
```

### Why use it?

- Structured data output (not raw HTML)
- Built for agent consumption
- Supports complex multi-step research
- Crawl and map entire sites for comprehensive analysis

---

## 2. Context7 — Live Library Documentation

**Repo:** [upstash/context7](https://github.com/upstash/context7)

Injects up-to-date library documentation into your LLM's context. Eliminates hallucinated APIs.

### The Problem It Solves

LLMs have knowledge cutoffs and often hallucinate API signatures. Context7 fetches the **current** docs for whatever library you're using and injects them into context.

### Setup

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

### Why use it?

- No more hallucinated API calls
- Always current documentation
- Works with any library/framework
- Reduces errors from outdated knowledge

---

## 3. Task Master AI — AI Project Manager

**Repo:** [eyaltoledano/claude-task-master](https://github.com/eyaltoledano/claude-task-master)

Your AI's project manager. Feed it a PRD and get structured tasks with dependencies.

### What It Does

1. Takes a Product Requirements Document (PRD)
2. Breaks it down into structured tasks
3. Maps dependencies between tasks
4. Tracks progress as you work

### Setup

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

### Why use it?

- Automatic task decomposition from specs
- Dependency tracking between tasks
- Progress monitoring
- Keeps complex projects organized

---

## How MCP Servers Work

MCP (Model Context Protocol) is a standard protocol that lets Claude connect to external tools:

1. **Server** exposes tools via the MCP protocol
2. **Claude Code** discovers available tools on startup
3. **During conversation**, Claude can call these tools as needed
4. **Results** flow back into the conversation context

### Where to configure

Add MCP servers to your Claude Code settings:

- **Project-level:** `.claude/settings.json` in your repo
- **User-level:** `~/.claude/settings.json`
- **Global:** System-wide configuration

### Tips

- Start with one MCP server at a time
- Check API key requirements before setup
- Some servers require Node.js or Python runtimes
- Use `npx` for zero-install Node.js servers
