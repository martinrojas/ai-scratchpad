# Claude Code Tools & Extensions

This directory contains Claude Code-specific commands, skills, and agent configurations — ready to copy into your own projects.

## Overview

Claude Code is Anthropic's official CLI and VS Code extension for Claude. This section provides ready-to-use extensions optimized for Claude Code workflows, organized into three types:

| Type | Location | How to use | Description |
|------|----------|------------|-------------|
| **Commands** | `.claude/commands/` | Type `/command-name` | Slash commands triggered by the user |
| **Skills** | `.claude/skills/` | Auto-invoked by Claude | Reusable capabilities Claude activates when relevant |
| **Agents** | `.claude/agents/` | Configured as subagents | Specialized agent personas for delegation |

## Commands

Custom slash commands you invoke with `/command-name` in Claude Code.

### `/reload-context` - Reload Project Context

Rebuilds full project context at the start of a new conversation — reads documentation, verifies implementation state, and identifies next steps.

See [commands/reload-context-command.md](commands/reload-context-command.md)

### `/reflection` - Session Analysis & Reflection

Analyzes the current development session to extract learnings — problems solved, patterns established, user preferences discovered, and system relationships mapped. Outputs structured reflection for building cumulative knowledge.

See [commands/reflection-command.md](commands/reflection-command.md)

### `/optimize-docs` - Documentation Optimization

Audits a repository's documentation and either scaffolds structure (if missing) or performs a maintenance pass. Handles `AGENTS.md` creation, routing tables, doc organization, and stale content cleanup.

See [commands/optimize-docs-command.md](commands/optimize-docs-command.md)

## Skills

Reusable capabilities that Claude activates automatically when the context matches. Place in `.claude/skills/` with a `SKILL.md` file.

### `analyze-document` - Deep Document Analysis

Applies a structured analytical framework to any document — surfaces non-obvious insights, tensions, actionable takeaways, and gaps instead of producing a generic summary. Includes document-type-specific modifiers.

See [skills/analyze-document/SKILL.md](skills/analyze-document/SKILL.md)

### `reload-context` - Context Reload Skill

Skill version of the reload-context command — automatically triggered when Claude detects a new conversation needs project context.

See [skills/reload-context/SKILL.md](skills/reload-context/SKILL.md)

### `portkey-typescript-sdk` - Portkey AI Gateway Integration

Guides integration of the Portkey AI Gateway into TypeScript/JavaScript applications for LLM observability, caching, fallbacks, and multi-provider routing.

See [skills/portkey-typescript-sdk/SKILL.md](skills/portkey-typescript-sdk/SKILL.md)

## Agents

Specialized agent configurations for delegation via Claude Code's subagent system.

### Senior Code Reviewer

A senior fullstack code reviewer with 15+ years of experience. Performs comprehensive reviews covering security, performance, architecture, and best practices. Produces structured output with severity levels and prioritized recommendations.

See [agents/senior-code-reviewer.md](agents/senior-code-reviewer.md)

### UI Engineer

An expert UI engineer with deep modern frontend expertise (React, Vue, Angular, TypeScript, CSS, accessibility). Focuses on clean, production-ready component architecture with proper typing and integration patterns.

See [agents/ui-engineer.md](agents/ui-engineer.md)

---

## Installation

To use these extensions in your own projects:

### Commands

```bash
# Copy all commands
cp tools/claude-code/commands/*.md .claude/commands/

# Or copy individual commands
cp tools/claude-code/commands/reflection-command.md .claude/commands/
```

### Skills

```bash
# Copy all skills
cp -r tools/claude-code/skills/* .claude/skills/

# Or copy individual skills
cp -r tools/claude-code/skills/analyze-document/ .claude/skills/
```

### Agents

```bash
# Copy agent configurations
cp tools/claude-code/agents/*.md .claude/agents/
```

After copying, customize paths and references to match your project structure.

## Creating Your Own

### New Command

1. Create a `.md` file in `.claude/commands/` — filename becomes the command name
2. Write clear instructions with expected output format
3. Invoke with `/command-name` in Claude Code

### New Skill

1. Create a directory in `.claude/skills/{skill-name}/`
2. Add a `SKILL.md` with YAML frontmatter (`name`, `description`, `allowed-tools`)
3. Claude auto-invokes when the description matches the user's context

### New Agent

1. Create a `.md` file in `.claude/agents/`
2. Define the agent's role, expertise, process, and output format
3. Reference as a subagent in commands or skills

## Best Practices

- **Be specific** — Clear instructions reduce ambiguity
- **Structure output** — Request organized, scannable results
- **Use subagents** — Leverage specialized agents (Explore, Plan, etc.)
- **Include success criteria** — Define what "done" looks like
- **Keep focused** — One extension, one purpose

## Learn More

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [Custom Commands Guide](https://docs.anthropic.com/en/docs/claude-code/slash-commands)
- [Prompt Engineering Tips](../../resources/guides/prompt-engineering.md)

---

**Last Updated**: 2026-04-05
