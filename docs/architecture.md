# Project Architecture

This document explains the organizational structure and design philosophy of the AI Scratchpad prompt collection.

## Philosophy

### Design Principles

1. **Use-Case First**: Organization prioritizes how people actually use prompts, not technical implementation details
2. **Discoverability**: Clear navigation and consistent structure make finding the right prompt easy
3. **Contribution-Friendly**: Standardized templates and guidelines lower the barrier to contributing
4. **Platform-Agnostic**: Prompts work across AI platforms unless there's a compelling reason for variants
5. **Quality over Quantity**: Focused, well-tested prompts that solve real problems

### Why This Structure?

**Problem**: Many prompt collections become disorganized as they grow, mixing platform-specific, use-case, and format-based organization in confusing ways.

**Solution**: Clear separation of concerns with consistent patterns at every level.

## Directory Structure

```
ai-scratchpad/
├── prompts/              # Use-case organized prompt collection
├── tools/                # Platform/tool-specific integrations
├── resources/            # Supporting materials and guides
└── docs/                 # Project documentation
```

### Top-Level Organization

**`prompts/`** - The main collection
- Organized by **use case** (development, writing, productivity)
- Each prompt gets its own directory
- Consistent structure across all prompts

**`tools/`** - Platform integrations
- Organized by **tool/platform** (claude-code, cursor, chatgpt)
- Contains configs, commands, and tool-specific features
- Separated from prompts to avoid confusion

**`resources/`** - Supporting materials
- Organized by **type** (guides, examples, templates, configs)
- Educational and reference content
- Helps users learn prompt engineering

**`docs/`** - Project meta-documentation
- Architecture (this file)
- Changelog
- Project-level documentation

## Prompt Organization

### Category Structure

```
prompts/{category}/{prompt-name}/
├── README.md              # Documentation and usage guide
├── prompt.md              # Main system prompt
├── knowledge/             # Optional: Knowledge documents
│   ├── guidelines.md
│   ├── examples.md
│   └── standards.md
└── variants/              # Optional: Platform-specific versions
    ├── gpt.md
    └── local.md
```

### Categories

Current categories reflect common use cases:

- **`development/`** - Software engineering tasks
  - Architecture discussions
  - Code review
  - Documentation maintenance
  - Debugging and troubleshooting

- **`technical-writing/`** - Content creation
  - Documentation systems
  - API docs
  - Technical articles
  - User guides

- **`productivity/`** - Workflow optimization
  - Meeting summaries
  - Task management
  - Email composition
  - Project planning

**Adding New Categories**: Create a new category when you have 2+ prompts that share a clear use case not covered by existing categories. Update this document when you do.

### Prompt Directory Naming

**Format**: Lowercase with hyphens (`my-prompt-name/`)

**Guidelines**:
- Descriptive of the use case
- Memorable and searchable
- Avoid abbreviations unless universally known
- 2-4 words ideal

**Examples**:
- ✅ `ui-architect/`
- ✅ `meeting-summary/`
- ✅ `universal-content-system/`
- ❌ `ua/` (too abbreviated)
- ❌ `the-ultimate-code-review-system-v2/` (too long)

### File Naming Standards

**Required Files**:
- `README.md` - Always the entry point for documentation
- `prompt.md` - Always the main prompt file

**Knowledge Documents**:
- Descriptive names: `context-guidelines.md`
- No prefixes: `guidelines.md` not `KD - Guidelines.md`
- Lowercase with hyphens

**Platform Variants**:
- Named by platform: `gpt.md`, `claude.md`, `gemini.md`
- Only create when meaningfully different
- Default `prompt.md` should work for most platforms

## Tool Organization

### Tool Structure

```
tools/{tool-name}/
├── README.md              # Setup and overview
├── commands/              # Custom commands (if applicable)
│   └── example-command.md
├── configs/               # Configuration files
│   └── settings.json
└── examples/              # Usage examples
    └── workflow-example.md
```

### When to Add a Tool Section

Add a tool directory when:
- The tool has a unique integration method (custom commands, configs)
- There are multiple tool-specific resources to organize
- The integration is reusable by others

**Don't** create a tool directory for:
- Simple usage instructions (add to prompt README instead)
- One-off examples
- Platform-generic content

### Tool Naming

Use the official tool name, lowercase:
- `claude-code/`
- `cursor/`
- `chatgpt/` (not `gpt/` or `openai/`)
- `vscode/`

## Resource Organization

### Resource Types

```
resources/
├── guides/               # How-to guides and tutorials
│   ├── prompt-engineering.md
│   └── platform-comparison.md
├── examples/             # Real-world usage examples
│   ├── workflows/
│   └── integrations/
├── templates/            # Starter templates
│   ├── basic-prompt-template.md
│   └── knowledge-document-template.md
└── configs/              # Reusable configurations
    └── vscode-settings.json
```

**`guides/`** - Educational content
- Prompt engineering techniques
- Best practices
- Platform comparisons
- Integration patterns

**`examples/`** - Practical demonstrations
- Multi-step workflows
- Integration examples
- Before/after comparisons
- Success stories

**`templates/`** - Contribution starters
- Prompt templates
- README templates
- Knowledge document structures
- Tool integration templates

**`configs/`** - Tool configurations
- Editor settings
- CLI configs
- Integration setups
- Environment files

## File Conventions

### Markdown Style

**Headers**: ATX-style (`#` not underlines)
```markdown
# Level 1
## Level 2
### Level 3
```

**Links**: Relative for internal, absolute for external
```markdown
[CONTRIBUTING.md](../CONTRIBUTING.md)
[Claude Code](https://github.com/anthropics/claude-code)
```

**Code Blocks**: Always specify language
```markdown
```bash
npm install
```
```

**Lists**: Blank lines before and after
```markdown
Some text.

- Item 1
- Item 2

More text.
```

### Metadata

All documentation files should include:
```markdown
---

**Last Updated**: YYYY-MM-DD
```

## Navigation Patterns

### Discovery Flow

1. **Entry Point**: [README.md](../README.md) - Overview and category index
2. **Category Browse**: User selects category (development, writing, etc.)
3. **Prompt Selection**: User finds prompt by name/description
4. **Prompt README**: Detailed usage guide with quick start
5. **Files**: User copies `prompt.md` and any knowledge docs

### Cross-References

**From Prompts**:
- Link to related prompts in same or different categories
- Link to relevant tools and resources
- Link to CONTRIBUTING.md for improvements

**From Tools**:
- Link to prompts that work well with the tool
- Link to guides and resources
- Link to official tool documentation

**From Resources**:
- Link to example prompts
- Link to relevant tools
- Cross-reference related guides

## Versioning Strategy

### File Versioning

**Prompts**: No version numbers in filenames
- Iterate in place
- Use git history for version tracking
- Breaking changes → new prompt with new name

**Tools**: Follow tool versioning where applicable
- `claude-code/` supports current Claude Code version
- Note compatibility in README if relevant

### Changelog

Track significant changes in [docs/changelog.md](changelog.md):
- New prompts and categories
- Major restructures
- Breaking changes
- Deprecated content

## Migration from Old Structure

### Old → New Mapping

```
prompts-GPTs/              → prompts/
  ui-architect/
    Rubber duck - Claude/  → prompts/development/ui-architect/
    Rubber duck - GPT5/    → prompts/development/ui-architect/variants/

prompts-terminal-buddy/    → prompts/development/
  Documentation...         → prompts/development/documentation-maintenance/

meeting summary/           → prompts/productivity/meeting-summary/

commands/                  → tools/claude-code/commands/
```

### Backward Compatibility

Old structure is deprecated but not yet removed. Future cleanup:
1. Archive old directories
2. Add README with redirect to new location
3. Eventually remove after transition period

## Scaling Considerations

### When to Create New Categories

**Triggers**:
- 2+ prompts share a clear use case
- Use case is distinct from existing categories
- Expected to grow with more contributions

**Process**:
1. Propose in GitHub Discussion
2. Get feedback from maintainers
3. Update this document
4. Update main README

### When to Split Categories

If a category grows too large (>10 prompts), consider:
1. Subcategories: `development/testing/`, `development/debugging/`
2. More specific categories: Split "development" into "backend", "frontend", "devops"

**Decision criteria**:
- Does split improve discoverability?
- Are subcategories sufficiently distinct?
- Will it scale with future growth?

### Preventing Sprawl

**Before adding new prompts**:
- Could this extend an existing prompt?
- Could this be a variant rather than a new prompt?
- Is this use case specific enough?

**Quality over quantity**: Better to have 20 excellent, focused prompts than 100 mediocre ones.

## Design Decisions

### Why Not Organize by Platform?

**Rejected**: `claude/`, `gpt/`, `gemini/` top-level structure

**Reasoning**:
- Users think in use cases, not platforms
- Most prompts work across platforms
- Platform organization encourages duplication
- Harder to discover "the meeting summary prompt" when split by platform

**Solution**: Use-case organization with optional platform variants

### Why Separate Tools?

**Rationale**:
- Tool integrations are fundamentally different from prompts
- Platform-specific commands don't belong with use-case prompts
- Clear separation prevents confusion
- Easier to find tool-specific setup instructions

### Why Knowledge Documents?

**Benefits**:
- Keeps main prompt focused
- Allows modular composition
- Easier to maintain and update
- Reusable across similar prompts

**When to use**:
- Supporting guidelines (>100 lines)
- Reference materials
- Examples and templates
- Platform-specific additions

**When not to use**:
- Small prompts (<200 lines total)
- Tightly coupled content
- Single-platform prompts

## Maintenance Philosophy

### Living Documentation

This architecture document should evolve with the project:
- Update when adding new categories
- Document new patterns as they emerge
- Remove outdated guidance
- Capture learnings from contributions

### Continuous Improvement

Regularly assess:
- Is navigation still intuitive?
- Are categories well-balanced?
- Do file structures make sense?
- Are there friction points for contributors?

**Refactor when needed**, but:
- Minimize disruption
- Provide migration paths
- Document changes
- Communicate to users

## Future Considerations

### Potential Additions

- **Multi-language support**: Translations of prompts and docs
- **Tagging system**: Cross-cutting tags (beginner/advanced, video/text, etc.)
- **Metrics**: Track prompt usage and effectiveness
- **Testing framework**: Automated prompt quality checks
- **Community ratings**: User feedback on prompt quality

### Extensibility

The structure is designed to accommodate:
- New categories easily
- New tools and platforms
- New resource types
- Different organizational needs (forks, derivatives)

---

**Last Updated**: 2025-11-20

## Questions or Suggestions?

Open a GitHub Discussion or Issue to propose changes to this architecture.
