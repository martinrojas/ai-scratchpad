# Claude Code Tools & Commands

This directory contains Claude Code-specific configurations, custom slash commands, and integration examples.

## Overview

Claude Code is Anthropic's official CLI and VS Code extension for Claude. This section provides ready-to-use commands and configurations optimized for Claude Code workflows.

## Available Commands

### `/reload-context` - Reload Project Context

**Purpose**: Example command demonstrating Claude Code's custom command system

**What it does**:

- Loads project documentation
- Verifies implementation state using subagents
- Identifies next steps
- Provides comprehensive project summary

**Use as**: A template for creating your own context-loading commands

See [commands/reload-context.md](commands/reload-context.md) for the full implementation.

---

## Creating New Commands

To add a new custom command:

1. Create a markdown file in `.claude/commands/` directory
   - Filename becomes the command: `my-command.md` → `/my-command`

2. Write the command prompt in the markdown file
   - Use clear instructions
   - Specify expected output format
   - Include examples if helpful

3. Use the command by typing `/command-name` in Claude Code

## Command Best Practices

- **Be specific** - Clear instructions reduce ambiguity
- **Structure output** - Request organized, scannable results
- **Use subagents** - Leverage specialized agents (Explore, Plan, etc.)
- **Include success criteria** - Define what "done" looks like
- **Keep focused** - One command, one purpose

## Installation

To use these commands in your own projects:

1. **Copy commands to your project**:

   ```bash
   cp -r tools/claude-code/commands/ .claude/commands/
   ```

2. **Customize for your project**:
   - Edit command prompts to match your file structure
   - Adjust paths and references
   - Modify output format as needed

3. **Use in Claude Code**:
   - Type `/command-name` in any conversation
   - Commands are project-specific

## Learn More

- [Claude Code Documentation](https://github.com/anthropics/claude-code)
- [Custom Commands Guide](https://github.com/anthropics/claude-code#custom-commands)
- [Prompt Engineering Tips](../../resources/guides/prompt-engineering.md)

---

**Last Updated**: 2025-11-20
