# Building Agent Workflows

## The Power Stack

Combine **Skills** + **MCP Servers** + **Agent Frameworks** for powerful workflows:

```
Skills (HOW)  +  MCP (ACCESS)  +  Frameworks (ORCHESTRATE)
     ↓                ↓                    ↓
  Better AI      External data      Multi-agent teams
  behavior       and tools          working together
```

## Workflow Examples

### 1. Research & Report Pipeline

**Tools needed:**
- Tavily MCP (search)
- claude-deep-research-skill (methodology)
- PDF skill (output)

**Flow:**
1. Claude uses Tavily to search for current information
2. Deep research skill structures the 8-phase investigation
3. PDF skill compiles findings into a polished report

### 2. Full-Stack Development Team

**Tools needed:**
- gstack or claude-squad (multi-agent)
- Superpowers skill (dev methodology)
- Context7 MCP (live docs)
- TDD Guard (quality)

**Flow:**
1. gstack spins up specialized agents (frontend, backend, tests)
2. Each agent uses Superpowers for systematic development
3. Context7 ensures no hallucinated APIs
4. TDD Guard enforces test-first on all agents

### 3. SEO Content Machine

**Tools needed:**
- Claude SEO skill (audit)
- Marketing Skills (content)
- Brand Guidelines skill (voice)
- Tavily MCP (research)

**Flow:**
1. SEO skill audits current site
2. Tavily researches competitor content
3. Marketing skills generate optimized content
4. Brand Guidelines ensures consistent voice

### 4. Automated Security Review

**Tools needed:**
- claude-code-security-review (Anthropic)
- promptfoo (testing)
- Systematic Debugging skill (methodology)

**Flow:**
1. Security review analyzes PRs automatically
2. Promptfoo tests for prompt injection vulnerabilities
3. Debugging skill provides root cause analysis for findings

## Multi-Agent Patterns

### Pattern 1: Divide & Conquer

Use **cmux** or **claude-squad** to run parallel agents:

```bash
# Agent 1: Frontend
# Agent 2: Backend API
# Agent 3: Tests
# All working simultaneously on the same codebase
```

### Pattern 2: Pipeline

Sequential agents, each handling one phase:

```
Research Agent → Planning Agent → Coding Agent → Review Agent
```

### Pattern 3: Supervisor

One orchestrator agent delegates to specialist agents:

```
Supervisor Agent
├── Research Agent
├── Coding Agent
├── Testing Agent
└── Documentation Agent
```

## Getting Started Combo

Start with this minimal but powerful setup:

1. **Skill:** Superpowers (dev methodology)
2. **MCP:** Context7 (live docs, no API key needed)
3. **Framework:** claude-squad (parallel agents when needed)

This gives you better coding practices, accurate API knowledge, and the ability to parallelize work — covering 80% of use cases.

## Tips

- Start simple — add one tool at a time
- Skills and MCP servers complement each other, not replace
- Agent frameworks are overkill for simple tasks — use them for complex, multi-step work
- Monitor token usage when running multiple agents
- Use persistent memory tools (Mem9, Codefire) for long-running projects
