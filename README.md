# AI Scratchpad: Prompt Collection

A curated collection of production-ready AI prompts, tools, and resources for developers, writers, and teams. This repository contains tested prompts for Claude, ChatGPT, and other AI platforms, designed to be used as-is, customized for specific needs, or studied as examples for learning prompt engineering.

## Quick Start

**New here?** Browse by use case below → Click a prompt → Follow the Quick Start in its README

**Contributing?** See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines

**Want to learn?** Check out the [Prompt Engineering Guide](resources/guides/prompt-engineering.md)

## Prompts by Category

### 🛠️ Development & Architecture

**[UI Architect / Rubber Duck](prompts/development/ui-architect/)**

Technical lead assistant for architecture discussions, code reviews, and design decisions

- Architecture planning and RFC authoring
- Code quality reviews with detailed feedback
- Technical decision-making with trade-off analysis
- Context-aware technical discussions

**[Documentation Maintenance](prompts/development/documentation-maintenance/)**

Standards and workflows for keeping project documentation current

- Living documentation practices
- Documentation-as-code workflows
- Maintenance triggers and schedules
- Quality standards and checklists

### ✍️ Technical Writing

**[Universal Content System](prompts/technical-writing/universal-content-system/)**

Comprehensive writing assistant with multi-level audience adaptation

- API documentation and developer guides
- Technical articles and tutorials
- Structured content architecture
- Quality assurance framework
- Performance tracking metrics

### 📊 Productivity

**[Meeting Summary](prompts/productivity/meeting-summary/)**

Transform meeting transcripts into structured, actionable summaries

- Extract key decisions and action items
- Assign ownership and track follow-ups
- Generate shareable meeting notes
- Works with any transcript format

## Platform-Specific Tools

### [Claude Code](tools/claude-code/)

Custom commands and configurations for Claude Code CLI and VS Code extension

- **[reload-context](tools/claude-code/commands/reload-context.md)**: Example context-loading command
- Custom command templates and patterns

More platform integrations coming soon: Cursor, VS Code, ChatGPT configurations

## Resources

### 📚 Guides

**[Prompt Engineering Guide](resources/guides/prompt-engineering.md)**

Comprehensive guide to writing effective prompts

- Core principles and best practices
- Prompt structure patterns
- Platform-specific optimization
- Testing and iteration strategies
- Troubleshooting common issues

### 📝 Templates

Ready-to-use templates for contributing:

- **[Basic Prompt Template](resources/templates/basic-prompt-template.md)** - Minimal prompt structure
- **[Knowledge Document Template](resources/templates/knowledge-document-template.md)** - Supporting doc structure
- **[Prompt README Template](resources/templates/prompt-readme-template.md)** - Comprehensive documentation
- **[Tool README Template](resources/templates/tool-readme-template.md)** - Tool integration docs

### 💡 Examples & Configs

- **`resources/examples/`** - Real-world usage examples and workflows
- **`resources/configs/`** - Tool configurations and setup files

## Usage Guide

### Using with Claude Projects

1. Browse to a prompt directory (e.g., [prompts/development/ui-architect/](prompts/development/ui-architect/))
2. Open the prompt's README for specific instructions
3. Copy `prompt.md` into Claude Project Instructions
4. Add any `knowledge/` files to Project Knowledge
5. Start chatting!

### Using with ChatGPT Custom GPTs

1. Choose a prompt and open its README
2. Go to ChatGPT → Explore GPTs → Create
3. Copy the prompt content (or `variants/gpt.md` if available) to Instructions
4. Upload knowledge documents to the Knowledge section
5. Configure and save your GPT

### Using with Command-Line Tools

```bash
# Direct usage
cat prompts/development/ui-architect/prompt.md | claude-cli

# Or install platform-specific commands
cp -r tools/claude-code/commands/ .claude/commands/
```

### Customizing Prompts

All prompts are designed to be customizable:

- **Replace placeholders**: Look for `[VARIABLE]` or `{context}` markers
- **Adjust knowledge docs**: Modify guidelines to match your standards
- **Combine prompts**: Mix elements for hybrid use cases
- **Add domain knowledge**: Append company-specific or domain context

See each prompt's README for specific customization guidance.

## Project Organization

### Structure

```text
ai-scratchpad/
├── prompts/              # Main prompt collection (organized by use case)
│   ├── development/      # Dev tools, architecture, debugging
│   ├── technical-writing/ # Documentation, articles, guides
│   └── productivity/     # Meetings, tasks, communication
├── tools/                # Platform-specific integrations
│   └── claude-code/      # Claude Code commands and configs
├── resources/            # Guides, templates, examples
│   ├── guides/           # Learning materials
│   ├── templates/        # Contribution starters
│   ├── examples/         # Real-world usage
│   └── configs/          # Tool configurations
└── docs/                 # Project documentation
    ├── architecture.md   # Organizational philosophy
    └── changelog.md      # Version history
```

See [docs/architecture.md](docs/architecture.md) for detailed rationale and design principles.

### Prompt Structure

Each prompt follows a consistent structure:

```text
prompts/{category}/{prompt-name}/
├── README.md              # Usage guide and documentation
├── prompt.md              # Main system prompt
├── knowledge/             # Optional: Supporting documents
│   ├── guidelines.md
│   └── examples.md
└── variants/              # Optional: Platform-specific versions
    └── gpt.md
```

## Contributing

We welcome contributions! Whether you have:

- ✨ A new prompt to share
- 🔧 Tool integrations or commands
- 📖 Guides or best practices
- 🐛 Bug fixes or improvements

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for:

- Contribution guidelines
- File structure requirements
- Quality standards
- Pull request process

**Good First Contributions**:

- Test existing prompts and report issues
- Add examples to prompt READMEs
- Improve documentation clarity
- Share your customizations

## Prompt Engineering Tips

### Core Principles

#### 1. Clear Role Definition

```markdown
You are a senior technical architect specializing in distributed systems...
```

#### 2. Explicit Output Format

```markdown
Always respond using this format:
1. Summary (2-3 sentences)
2. Analysis (detailed breakdown)
3. Recommendations (actionable items)
```

#### 3. Set Boundaries

```markdown
Do not: Generate code without explanation
Always: Explain trade-offs and alternatives
```

#### 4. Use Examples

Show desired behavior with concrete examples in your prompts.

See the full [Prompt Engineering Guide](resources/guides/prompt-engineering.md) for comprehensive techniques.

## Platform Comparison

### Claude

- Excels at nuanced reasoning and context
- Strong with principle-based instructions
- Natural conversational guidelines
- Great for architecture and analysis tasks

### ChatGPT (GPT-4/5)

- Excellent with structured formats
- Strong persona adherence
- Effective with step-by-step instructions
- Great for procedural and template-based tasks

### Cross-Platform

Most prompts in this collection work across platforms. Variants are only provided when there are meaningful platform-specific optimizations.

## Examples in Action

### Code Review Workflow

```text
1. Use UI Architect prompt
2. Paste code for review
3. Get structured feedback:
   - Critical issues
   - Quality improvements
   - Best practice recommendations
   - Security considerations
```

### Documentation Sprint

```text
1. Use Universal Content System prompt
2. Specify audience level (beginner/intermediate/advanced)
3. Provide API specs or code
4. Get structured docs with examples
```

### Meeting Follow-up

```text
1. Use Meeting Summary prompt
2. Paste transcript from Zoom/Teams
3. Get structured output:
   - Key decisions
   - Action items with owners
   - Follow-up questions
```

## FAQ

**Q: Do these prompts work with local AI models?**
A: Many do! Results vary by model capability. Test and adjust complexity as needed.

**Q: Can I use these commercially?**
A: Yes! MIT License - use, modify, and distribute freely.

**Q: How do I know which prompt to use?**
A: Browse by category based on your use case. Each prompt README explains when to use it.

**Q: Can I combine multiple prompts?**
A: Absolutely! Many users mix elements from different prompts for custom solutions.

**Q: What if a prompt doesn't work well for my use case?**
A: Customize it! See the prompt's README for customization guidance, or create a variant.

## Roadmap

Planned additions:

- More prompt categories (data analysis, communication, automation)
- Additional platform integrations (Cursor, VS Code, Gemini)
- Workflow examples and integration patterns
- Community ratings and feedback system
- Multi-language translations

See [issues](https://github.com/martinrojas/ai-scratchpad/issues) for active development.

## Learn More

- **[Contributing Guide](CONTRIBUTING.md)** - How to add prompts and resources
- **[Architecture Doc](docs/architecture.md)** - Project organization philosophy
- **[Prompt Engineering Guide](resources/guides/prompt-engineering.md)** - Learn to write effective prompts
- **[Browse Templates](resources/templates/)** - Start creating your own prompts

## Recognition

This project builds on the collective knowledge of the AI community. Special thanks to all [contributors](https://github.com/martinrojas/ai-scratchpad/graphs/contributors).

## License

MIT License - See [LICENSE](LICENSE) for details.

Feel free to use, modify, and distribute these prompts for any purpose.

---

**Last Updated**: 2025-11-20

Found these prompts useful? ⭐ Star the repo or share with your team!

**Questions or feedback?** Open an [issue](https://github.com/martinrojas/ai-scratchpad/issues) or [discussion](https://github.com/martinrojas/ai-scratchpad/discussions).
