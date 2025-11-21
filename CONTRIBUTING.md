# Contributing to AI Scratchpad

Thank you for your interest in contributing! This guide will help you add prompts, tools, and resources to the collection.

## Quick Start

1. **Fork the repository** and create a new branch
2. **Choose what you're contributing**:
   - New prompt? → Add to `prompts/{category}/`
   - Tool integration? → Add to `tools/{tool-name}/`
   - Guide or resource? → Add to `resources/`
3. **Follow the structure** outlined below
4. **Submit a pull request** with a clear description

## What We're Looking For

**Good Contributions**:
- ✅ Prompts that solve specific, common problems
- ✅ Well-tested on at least one major AI platform
- ✅ Clear documentation with examples
- ✅ Reusable by others (no hardcoded personal details)
- ✅ Focused on a single use case

**Not Suitable**:
- ❌ Highly specific to one company/project
- ❌ Untested or experimental prompts
- ❌ Duplicates of existing prompts
- ❌ Overly broad or unfocused prompts

## Contributing a New Prompt

### 1. Choose the Right Category

Place your prompt in the appropriate category:

```
prompts/
├── development/          # Dev tools, architecture, debugging
├── technical-writing/    # Documentation, articles, guides
├── productivity/         # Meeting summaries, task management
├── data-analysis/        # Data processing, analysis, visualization
├── communication/        # Emails, messages, presentations
└── [propose-new]/        # Suggest a new category if needed
```

### 2. Create the Prompt Directory

Create a directory with a descriptive, lowercase, hyphenated name:

```bash
mkdir -p prompts/{category}/{prompt-name}
cd prompts/{category}/{prompt-name}
```

### 3. Required Files

Every prompt must include:

#### `README.md` - Prompt Documentation

```markdown
# [Prompt Name]

[One-sentence description]

## Overview

[2-3 paragraphs explaining what this prompt does and why it's useful]

## Use Cases

- **Use Case 1**: Description
- **Use Case 2**: Description
- **Use Case 3**: Description

## Quick Start

### Using with Claude

[Instructions]

### Using with ChatGPT

[Instructions]

## Files

- **[prompt.md](prompt.md)** - Main system prompt
- **[knowledge/](knowledge/)** - Knowledge documents (if applicable)

## Key Features

[Bullet points highlighting main capabilities]

## Customization

[How to adapt this prompt for specific needs]

## Tips for Best Results

[Best practices and usage tips]

## Examples

[Input/output examples or usage scenarios]

## Contributing

Found improvements? See [CONTRIBUTING.md](../../../CONTRIBUTING.md).

---

**Last Updated**: YYYY-MM-DD
```

#### `prompt.md` - The Main Prompt

This is the core system prompt. Follow these guidelines:

**Structure**:
```markdown
# [Prompt Title]

[Opening paragraph defining the role/purpose]

## Core Responsibilities

[What the AI should do]

## Guidelines

[How the AI should behave]

## Output Format

[Expected response structure]

## Examples (Optional)

[Sample interactions]
```

**Best Practices**:
- Clear role definition at the start
- Specific, actionable instructions
- Explicit output format when needed
- Include constraints and boundaries
- Use examples for complex behaviors

### 4. Optional: Knowledge Documents

If your prompt needs supporting materials, create a `knowledge/` directory:

```
prompts/{category}/{prompt-name}/
├── README.md
├── prompt.md
└── knowledge/
    ├── guidelines.md
    ├── examples.md
    └── standards.md
```

**When to use knowledge documents**:
- Complex guidelines that would clutter the main prompt
- Reference materials (templates, checklists, standards)
- Examples that need detailed explanation
- Platform-specific variations

**Naming**: Use descriptive, lowercase, hyphenated names (no "KD -" prefix)

### 5. Optional: Platform Variants

If your prompt is significantly different across platforms:

```
prompts/{category}/{prompt-name}/
├── README.md
├── prompt.md           # Default (Claude-optimized)
└── variants/
    ├── gpt.md         # ChatGPT-specific
    ├── gemini.md      # Gemini-specific
    └── local.md       # Local models
```

**Note**: Only create variants if there are meaningful differences. Most prompts work across platforms.

## Contributing Tools & Integrations

### Tool Structure

Create a directory under `tools/` for platform-specific content:

```
tools/{tool-name}/
├── README.md           # Setup guide and overview
├── commands/           # Custom commands (if applicable)
├── configs/            # Configuration files
└── examples/           # Usage examples
```

### Tool README Template

```markdown
# [Tool Name]

## Overview

[What this tool is and how it integrates with AI]

## Installation

[Setup instructions]

## Available Resources

[List of commands, configs, or examples]

## Usage

[How to use the integrations]

## Learn More

[Links to official documentation]

---

**Last Updated**: YYYY-MM-DD
```

## Contributing Resources

### Guides

Add how-to guides to `resources/guides/`:

```markdown
# [Guide Title]

[Comprehensive guide on a specific topic]

Topics:
- Prompt engineering techniques
- Platform comparisons
- Integration patterns
- Best practices
```

### Examples

Add real-world examples to `resources/examples/`:

```
resources/examples/
├── workflows/          # Multi-step AI workflows
└── integrations/       # Integration examples
```

### Templates

Add starter templates to `resources/templates/`:

- `basic-prompt-template.md` - Minimal prompt structure
- `knowledge-document-template.md` - KD structure
- `tool-readme-template.md` - Tool documentation

## Code Quality Standards

### Markdown Formatting

- Use ATX-style headers (`#` not underlines)
- Include blank lines around lists and code blocks
- Use relative links for internal references
- Keep line length readable (no hard limit, but be reasonable)

### File Naming

- Lowercase with hyphens: `my-prompt-name/`
- Descriptive: `meeting-summary` not `ms`
- No special characters except hyphens and underscores
- Markdown files: `.md` extension

### Documentation Quality

- **Clear**: Write for someone unfamiliar with your use case
- **Complete**: Include all necessary context
- **Accurate**: Test before submitting
- **Concise**: Respect the reader's time
- **Current**: Date-stamp your contributions

## Testing Your Contribution

Before submitting, verify:

- [ ] Prompt works on at least one major platform (Claude, ChatGPT, etc.)
- [ ] README is complete and follows the template
- [ ] Examples are accurate and helpful
- [ ] No personal/company-specific information
- [ ] File structure matches guidelines
- [ ] Markdown lints cleanly (optional but appreciated)
- [ ] Links work correctly

## Submitting Your Contribution

### Pull Request Process

1. **Create a descriptive branch name**:
   ```bash
   git checkout -b add-prompt-code-reviewer
   ```

2. **Make your changes** following the guidelines above

3. **Test thoroughly** on at least one AI platform

4. **Commit with clear messages**:
   ```bash
   git add .
   git commit -m "Add code reviewer prompt for development category"
   ```

5. **Push and create PR**:
   ```bash
   git push origin add-prompt-code-reviewer
   ```

6. **Open PR with description**:

   ```markdown
   ## What This Adds

   [Description of your contribution]

   ## Category

   - [ ] New prompt
   - [ ] Tool integration
   - [ ] Resource/guide
   - [ ] Documentation improvement

   ## Testing

   Tested on: [Platform(s)]

   ## Use Case

   [Brief description of when someone would use this]
   ```

### PR Guidelines

- **One contribution per PR**: Don't mix multiple unrelated additions
- **Clear description**: Explain what you're adding and why
- **Include examples**: Show the prompt in action if possible
- **Respond to feedback**: Be open to suggestions and improvements

## Style Guide

### Writing Tone

- **Clear and Direct**: Avoid unnecessary jargon
- **Action-Oriented**: Focus on what users can do
- **Inclusive**: Write for diverse skill levels
- **Professional but Friendly**: Approachable but authoritative

### Prompt Writing

**Good**:
```
You are a senior software architect specializing in distributed systems.
Your role is to help developers make informed architectural decisions.

When reviewing designs:
1. Analyze trade-offs between options
2. Consider scalability and maintainability
3. Provide specific recommendations
```

**Avoid**:
```
You're an AI that knows about software stuff. Help people with whatever
they ask. Try to be helpful and give good answers.
```

### Documentation Writing

**Good**:
- "This prompt generates API documentation from OpenAPI specs"
- "Best for: REST APIs, microservices, developer portals"
- "Follow these steps to customize for your needs..."

**Avoid**:
- "This amazing prompt will revolutionize your documentation!"
- "Just use it and see what happens"
- Assuming deep context without explanation

## Getting Help

- **Questions?** Open a GitHub Discussion
- **Bug Reports?** Open a GitHub Issue
- **Need Guidance?** Check existing prompts as examples
- **Want Feedback?** Open a draft PR early

## Recognition

All contributors will be recognized in:
- GitHub contributors list
- Project acknowledgments
- Release notes (for significant contributions)

## License

By contributing, you agree that your contributions will be licensed under the same MIT License that covers this project.

---

Thank you for helping make AI tools more accessible and useful for everyone!
