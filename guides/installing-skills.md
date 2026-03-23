# Installing & Managing Claude Skills

## What Are Skills?

Skills are markdown instruction files (typically `SKILL.md`) that teach Claude **how** to perform specific tasks. They live in your project's `.claude/skills/` directory.

## Where to Find Skills

| Source | Skills | URL |
|--------|--------|-----|
| Official Anthropic | ~20 | [github.com/anthropics/skills](https://github.com/anthropics/skills) |
| SkillsMP | 80k+ | [skillsmp.com](https://skillsmp.com) |
| SkillHub | 31k+ | [skillhub.club](https://skillhub.club) |
| AI Templates | Various | [aitmpl.com/skills](https://aitmpl.com/skills) |
| Awesome Claude Skills | Curated | [github.com/travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) |

## Installation Methods

### Method 1: Manual Copy

```bash
# Clone the skill repo
git clone https://github.com/anthropics/skills.git /tmp/skills

# Copy specific skill to your project
mkdir -p .claude/skills
cp /tmp/skills/skills/frontend-design/SKILL.md .claude/skills/frontend-design.md
```

### Method 2: Use the Skill Creator

The official Skill Creator lets you build custom skills:

1. Install the skill creator skill
2. Describe the workflow you want
3. Claude generates a SKILL.md for you

```
> /install-skill skill-creator
```

### Method 3: Write Your Own

Create `.claude/skills/my-skill.md`:

```markdown
# My Custom Skill

## When to Use
Describe when Claude should apply this skill.

## Instructions
Step-by-step instructions for Claude to follow.

## Examples
Show input/output examples.
```

## Skill Categories

### Essential Starter Kit

1. **Frontend Design** — Better UI generation
2. **Superpowers** — 20+ dev skills in one package
3. **Context Optimization** — Reduce token usage
4. **PDF Processing** — Document handling

### For Content Creators

1. **Brand Guidelines** — Consistent brand voice
2. **Canvas Design** — Social graphics
3. **Doc Co-Authoring** — Collaborative writing

### For Developers

1. **Systematic Debugging** — Root cause analysis
2. **TDD Guard** — Test-first enforcement
3. **File Search** — Advanced code search

## Tips

- Keep skills focused — one task per skill
- Use the SkillHub ratings to find quality skills
- Test skills with real tasks before relying on them
- Skills can reference other skills for complex workflows
