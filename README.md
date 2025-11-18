# AI Scratchpad: Prompt Collection

A curated collection of production-ready AI prompts for various use cases. This repository contains tested prompts for custom GPTs, Claude projects, and command-line AI assistants, designed to be used as-is, customized for specific needs, or studied as examples for learning prompt engineering.

## Table of Contents

- [Getting Started](#getting-started)
- [Prompt Categories](#prompt-categories)
  - [Development & Architecture](#development--architecture)
  - [Technical Writing](#technical-writing)
  - [Productivity](#productivity)
  - [Terminal & CLI](#terminal--cli)
- [Usage Guide](#usage-guide)
- [Prompt Engineering Tips](#prompt-engineering-tips)
- [Contributing](#contributing)
- [License](#license)

## Getting Started

Each prompt is organized by use case and includes:
- **Main prompt file**: The core system prompt or instructions
- **Knowledge documents (KD)**: Supporting context and guidelines
- **Platform variants**: Optimized versions for different AI models (GPT-4, Claude, etc.)

### Quick Start

1. Browse the [Prompt Categories](#prompt-categories) below
2. Navigate to the prompt that fits your needs
3. Copy the prompt file contents
4. Customize variables or context as needed
5. Use in your preferred AI platform

## Prompt Categories

### Development & Architecture

#### UI Architect / Rubber Duck
**Path**: `prompts-GPTs/ui-architect/Rubber duck - [Platform]/`

A technical lead assistant for architecture discussions, code review, and design decisions.

**Platforms**:
- Claude (`Rubber duck - Claude/`)
- GPT-4/5 (`Rubber duck - GPT5/`)

**Key Features**:
- RFC authoring guidance
- Code quality standards
- Context-aware technical discussions
- Response templates for consistent output

**Best For**: Architecture planning, code reviews, technical decision-making, design pattern discussions

**Files**:
- `RubberDuck Prompt.md` - Main system prompt
- `KD - Context Guidelines for Technical Lead.md` - Conversation guidelines
- `KD - Response Templates Examples Knowledge Document.md` - Output formatting
- `KD - Code Examples Quality Standards Knowledge Document.md` - Code quality standards
- `KD — RFC Authoring Guide.md` (GPT5 only) - RFC writing guidelines

### Technical Writing

#### Universal Content System
**Path**: `prompts-GPTs/technical-writer/`

Comprehensive technical writing assistant with structured content architecture and quality frameworks.

**Key Features**:
- Multi-level technical audience adaptation
- Consistent voice and tone matrix
- Performance tracking metrics
- Universal QA checklist
- Structured content architecture

**Best For**: Documentation writing, technical articles, developer guides, API documentation

**Files**:
- `Prompt - Universal Content System.md` - Main system prompt
- `KD - Universal Tech Levels.md` - Audience technical proficiency levels
- `KD - Universal Voice Matrix.md` - Voice and tone guidelines
- `KD - Universal Content Architecture.md` - Content structure framework
- `KD - Universal QA Checklist.md` - Quality assurance standards
- `KD - Universal Performance Tracking.md` - Metrics and improvement tracking

### Productivity

#### Meeting Summary GPT
**Path**: `meeting summary/Meeting Summary GPT.md`

Generates structured, actionable meeting summaries from transcripts or notes.

**Best For**: Meeting notes processing, action item extraction, summary generation

### Terminal & CLI

#### Documentation Maintenance
**Path**: `prompts-terminal-buddy/Documentation Maintenance.md`

Standards and guidelines for maintaining living documentation in software projects.

**Best For**: Project documentation standards, documentation maintenance workflows, team documentation guidelines

## Usage Guide

### Using with Custom GPTs (ChatGPT)

1. Go to ChatGPT > Explore GPTs > Create
2. Copy the main prompt into the Instructions field
3. Upload Knowledge Documents as files in the Knowledge section
4. Configure conversation starters based on the prompt's use case

### Using with Claude Projects

1. Create a new Project in Claude
2. Copy the main prompt and knowledge documents into Project Knowledge
3. Start a conversation within the project context

### Using with Command-Line AI Tools

1. Copy the prompt content
2. Save as a reusable template or command
3. Pass to your CLI tool (e.g., `claude-cli`, `chatgpt-cli`, etc.)

### Customizing Prompts

Most prompts include variables or sections you can customize:
- **Replace placeholders**: Look for `[VARIABLE]` or `{context}` markers
- **Adjust knowledge docs**: Modify guidelines to match your standards
- **Combine prompts**: Mix elements from different prompts for hybrid use cases
- **Add domain knowledge**: Append company-specific or domain-specific context

## Prompt Engineering Tips

### Structure Principles

**Clear Role Definition**: Start with explicit role and expertise level
```markdown
You are a senior technical architect specializing in distributed systems...
```

**Explicit Output Format**: Specify exactly how responses should be structured
```markdown
Always respond using this format:
1. Summary (2-3 sentences)
2. Analysis (detailed breakdown)
3. Recommendations (actionable items)
```

**Context Boundaries**: Define what the AI should and shouldn't do
```markdown
Do not: Generate code without explanation
Always: Explain trade-offs and alternatives
```

### Knowledge Documents

**Separation of Concerns**: Break complex prompts into modular knowledge docs
- Main prompt = core behavior and role
- Knowledge docs = specific guidelines, standards, examples

**Progressive Enhancement**: Layer knowledge docs by priority
- Essential guidelines (always needed)
- Contextual guidelines (specific scenarios)
- Reference materials (examples, templates)

### Testing and Iteration

1. **Start simple**: Basic prompt first, add complexity gradually
2. **Test edge cases**: Try unusual inputs, check consistency
3. **Version control**: Track what works, document changes
4. **Collect examples**: Save good outputs to refine prompts

### Platform-Specific Optimization

**GPT-4/5**:
- Works well with structured formats and step-by-step instructions
- Strong with role-playing and persona adherence
- Benefits from explicit examples

**Claude**:
- Excels with nuanced context and reasoning
- Responds well to conversational guidelines
- Effective with principle-based instructions

## Contributing

Contributions are welcome! If you have prompts that work well for your use cases:

1. **Format**: Follow the existing structure (main prompt + knowledge docs)
2. **Documentation**: Include a brief description of the prompt's purpose and best use cases
3. **Testing**: Ensure the prompt works as intended on at least one major platform
4. **Submit**: Open a Pull Request with your additions

Please keep prompts:
- **Focused**: Each prompt should have a clear, specific purpose
- **Reusable**: Avoid hardcoded personal/company-specific details
- **Well-documented**: Include context on when and how to use it

## License

MIT License - Feel free to use, modify, and distribute these prompts for any purpose.

---

**Last Updated**: 2025-11-17

Found these prompts useful? Star the repo or share with your team!
