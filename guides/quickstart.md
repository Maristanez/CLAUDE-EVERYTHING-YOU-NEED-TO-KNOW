# Quickstart: Get Up and Running in 5 Minutes

## Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed
- Node.js 18+ (for MCP servers that use `npx`)
- An Anthropic API key or Claude Pro/Max subscription

## Step 1: Install Your First Skill

Skills are just markdown files. Drop them into your project:

```bash
# Clone the official skills repo
git clone https://github.com/anthropics/skills.git

# Copy a skill to your project
cp -r skills/skills/frontend-design/.claude/skills/ your-project/.claude/skills/
```

Or install from a skills platform:
- [skillsmp.com](https://skillsmp.com) — 80k+ skills
- [skillhub.club](https://skillhub.club) — 31k+ AI-rated skills

## Step 2: Set Up an MCP Server

Add to your Claude Code settings (`.claude/settings.json`):

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

Restart Claude Code and the MCP server tools become available.

## Step 3: Try It Out

Start Claude Code in your project directory:

```bash
claude
```

Claude will automatically:
- Load any skills in `.claude/skills/`
- Connect to configured MCP servers
- Have access to all the tools and knowledge you've set up

## What Next?

- [Installing Skills](./installing-skills.md) — Deep dive into skill management
- [Setting Up MCP](./setting-up-mcp.md) — Configure more MCP servers
- [Building Agent Workflows](./building-agent-workflows.md) — Combine everything together
