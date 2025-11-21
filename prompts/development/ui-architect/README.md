# UI Architect / Rubber Duck

A technical lead assistant for architecture discussions, code review, and design decisions.

## Overview

This prompt creates an AI assistant that acts as a senior technical architect, helping you think through architectural decisions, review code, author RFCs, and maintain high-quality technical discussions.

## Use Cases

- **Architecture Planning**: Design system architecture and technical approaches
- **Code Reviews**: Get detailed feedback on code quality and best practices
- **Technical Decision-Making**: Evaluate trade-offs between different solutions
- **RFC Authoring**: Structure and refine technical proposals
- **Design Pattern Discussions**: Apply appropriate patterns to your codebase

## Quick Start

### Using with Claude Projects

1. Create a new Project in Claude
2. Copy the contents of [prompt.md](prompt.md) into the Project Instructions
3. Add the knowledge documents from the [knowledge/](knowledge/) folder to Project Knowledge
4. Start a conversation within the project

### Using with ChatGPT Custom GPTs

1. Go to ChatGPT > Explore GPTs > Create
2. Copy the contents of [variants/gpt.md](variants/gpt.md) into the Instructions field
3. Upload the files from [knowledge/](knowledge/) to the Knowledge section
4. Add conversation starters like:
   - "Review this code for quality and best practices"
   - "Help me design an architecture for..."
   - "I need to write an RFC for..."

### Using with Command-Line Tools

```bash
# Example with Claude Code or similar CLI tools
cat prompts/development/ui-architect/prompt.md | your-ai-cli
```

## Files

- **[prompt.md](prompt.md)** - Main system prompt (optimized for Claude)
- **[variants/gpt.md](variants/gpt.md)** - GPT-4/5 optimized version

### Knowledge Documents

- **[context-guidelines.md](knowledge/context-guidelines.md)** - Conversation and context management guidelines
- **[response-templates.md](knowledge/response-templates.md)** - Structured output formatting examples
- **[code-standards.md](knowledge/code-standards.md)** - Code quality and review standards
- **[rfc-authoring-guide.md](knowledge/rfc-authoring-guide.md)** - RFC writing guidelines

## Key Features

### Context-Aware Discussions
The assistant maintains awareness of previous conversations and can reference earlier decisions, making it ideal for ongoing architectural work.

### Structured Responses
Uses consistent templates for different types of responses (code review, architecture proposal, RFC feedback, etc.).

### Quality Standards
Applies rigorous code quality standards including:
- Security considerations
- Performance implications
- Maintainability
- Best practices
- Testing requirements

### RFC Support
Guides you through writing technical RFCs with proper structure, trade-off analysis, and decision documentation.

## Customization

### Adapting to Your Tech Stack

Edit the [prompt.md](prompt.md) file to include your specific:
- Programming languages
- Frameworks
- Architecture patterns
- Team standards
- Company-specific guidelines

### Modifying Quality Standards

Update [knowledge/code-standards.md](knowledge/code-standards.md) to match your team's:
- Code style guides
- Review checklists
- Security requirements
- Performance benchmarks

### Adding Domain Knowledge

Create additional knowledge documents for:
- Your system architecture
- API contracts
- Database schemas
- Deployment processes

## Tips for Best Results

1. **Be Specific**: Provide context about your system, constraints, and goals
2. **Ask Follow-ups**: Dig deeper into trade-offs and alternatives
3. **Share Code**: Include relevant code snippets for concrete feedback
4. **Reference Decisions**: Build on previous architectural discussions
5. **Request Templates**: Ask for RFCs, ADRs, or design doc structures

## Examples

### Architecture Discussion
```
"I need to design a notification system that handles 10k+ events per second.
Should I use WebSockets, Server-Sent Events, or a polling approach?"
```

### Code Review
```
"Review this authentication middleware for security and best practices:
[paste code]"
```

### RFC Authoring
```
"Help me write an RFC for migrating from REST to GraphQL for our user API"
```

## Platform Differences

### Claude vs GPT Variants

- **Claude version** ([prompt.md](prompt.md)): More conversational, excels at nuanced reasoning
- **GPT version** ([variants/gpt.md](variants/gpt.md)): Includes RFC authoring guide, structured for step-by-step guidance

Choose based on your preferred AI platform. Both provide high-quality architectural guidance.

## Contributing

Found ways to improve this prompt? See [CONTRIBUTING.md](../../../CONTRIBUTING.md) for guidelines.

## Related Prompts

- [Documentation Maintenance](../documentation-maintenance/) - Standards for maintaining project docs
- [Universal Content System](../../technical-writing/universal-content-system/) - For writing technical documentation

---

**Last Updated**: 2025-11-20
