# MCP & Integrations

Tools for building MCP servers and integrating Claude with external systems.

---

## MCP Playwright

**Repo:** [executeautomation/mcp-playwright](https://github.com/executeautomation/mcp-playwright)

Browser automation for LLMs. Let Claude control a browser via Playwright through MCP.

---

## stealth-browser-mcp

**Repo:** [vibheksoni/stealth-browser-mcp](https://github.com/vibheksoni/stealth-browser-mcp)

Undetectable browser automation. Bypasses bot detection for web scraping and testing.

---

## fastmcp

**Repo:** [jlowin/fastmcp](https://github.com/jlowin/fastmcp)

Build MCP servers in minimal Python. The fastest way to create custom MCP servers.

```python
from fastmcp import FastMCP

mcp = FastMCP("my-server")

@mcp.tool()
def my_tool(query: str) -> str:
    return f"Result for {query}"
```

---

## markdownify-mcp

**Repo:** [zcaceres/markdownify-mcp](https://github.com/zcaceres/markdownify-mcp)

Convert PDFs, images, and audio into Markdown. Universal document-to-text conversion.

---

## MCPHub

**Repo:** [samanhappy/mcphub](https://github.com/samanhappy/mcphub)

Manage multiple MCP servers via HTTP. Central management for all your MCP server instances.

---

## Search, Data & LLM Tools

### CK (BeaconBay)
**Repo:** [BeaconBay/ck](https://github.com/BeaconBay/ck)

Search code by meaning, not keywords. Semantic code search.

### ExtractThinker
**Repo:** [enoch3712/ExtractThinker](https://github.com/enoch3712/ExtractThinker)

ORM for document intelligence. Structured data extraction from any document.

### OmniRoute
**Repo:** [diegosouzapw/OmniRoute](https://github.com/diegosouzapw/OmniRoute)

API proxy for 44+ AI providers. Single endpoint, multiple backends.

### dlt
**Repo:** [dlt-hub/dlt](https://github.com/dlt-hub/dlt)

LLM-native data pipelines from 5,000+ sources.

### simonw/llm
**Repo:** [simonw/llm](https://github.com/simonw/llm)

Lightweight CLI for local and remote LLMs. Simple, composable, Unix-philosophy.

### Portkey-AI/gateway
**Repo:** [Portkey-AI/gateway](https://github.com/Portkey-AI/gateway)

Route requests to 250+ LLMs. Load balancing, fallbacks, and caching.

### lmnr
**Repo:** [lmnr-ai/lmnr](https://github.com/lmnr-ai/lmnr)

Trace and evaluate agent behavior. Observability for AI agents.

---

## Video & More

### LTX-Desktop (Lightricks)
**Repo:** [Lightricks/LTX-Desktop](https://github.com/Lightricks/LTX-Desktop)

Generate and edit videos locally.

### MetaClaw
**Repo:** [aiming-lab/MetaClaw](https://github.com/aiming-lab/MetaClaw)

Evolve AI agents without GPU.

### Vane
**Repo:** [ItzCrazyKns/Vane](https://github.com/ItzCrazyKns/Vane)

AI answering engine with local LLMs.
