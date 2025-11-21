# Universal Content System

Comprehensive technical writing assistant with structured content architecture and quality frameworks.

## Overview

This prompt creates a sophisticated technical writing assistant that helps you produce high-quality documentation, articles, guides, and API docs. It uses a structured approach to ensure consistency, clarity, and effectiveness across all technical content.

## Use Cases

- **Developer Documentation**: API docs, SDK guides, integration tutorials
- **Technical Articles**: Blog posts, whitepapers, technical deep-dives
- **User Guides**: Product documentation, feature explanations
- **Internal Documentation**: Architecture docs, runbooks, process guides
- **Educational Content**: Tutorials, learning paths, course materials

## Quick Start

### Using with Claude Projects

1. Create a new Project in Claude
2. Copy the contents of [prompt.md](prompt.md) into the Project Instructions
3. Add all knowledge documents from [knowledge/](knowledge/) to Project Knowledge
4. Start writing or editing your content

### Using with ChatGPT Custom GPTs

1. Go to ChatGPT > Explore GPTs > Create
2. Copy [prompt.md](prompt.md) into the Instructions field
3. Upload all files from [knowledge/](knowledge/) to the Knowledge section
4. Configure conversation starters like:
   - "Help me write API documentation for..."
   - "Review this technical article for clarity"
   - "Create a tutorial for..."

## Files

- **[prompt.md](prompt.md)** - Main system prompt

### Knowledge Documents

- **[tech-levels.md](knowledge/tech-levels.md)** - Technical audience proficiency levels (beginner to expert)
- **[voice-matrix.md](knowledge/voice-matrix.md)** - Voice and tone guidelines for different contexts
- **[content-architecture.md](knowledge/content-architecture.md)** - Structural frameworks for organizing content
- **[qa-checklist.md](knowledge/qa-checklist.md)** - Quality assurance standards and review checklist
- **[performance-tracking.md](knowledge/performance-tracking.md)** - Metrics for measuring content effectiveness

## Key Features

### Multi-Level Audience Adaptation
Automatically adjusts technical depth based on audience:
- **Beginner**: Concepts explained from first principles
- **Intermediate**: Balanced theory and practical application
- **Advanced**: Deep technical details and edge cases
- **Expert**: Nuanced discussions and optimization techniques

### Voice & Tone Matrix
Consistent voice across different content types:
- Educational (tutorials, guides)
- Reference (API docs, specifications)
- Conversational (blog posts, announcements)
- Formal (whitepapers, research)

### Structured Content Architecture
Framework for organizing information:
- Clear hierarchy and flow
- Scannable formatting
- Progressive disclosure
- Logical information architecture

### Quality Assurance
Built-in checklist covering:
- Technical accuracy
- Clarity and readability
- Code example quality
- Completeness
- Accessibility

### Performance Tracking
Metrics and improvement framework:
- Readability scores
- Engagement indicators
- User feedback integration
- Iterative improvement process

## Customization

### Adapting to Your Style Guide

Edit [knowledge/voice-matrix.md](knowledge/voice-matrix.md) to match your:
- Brand voice
- Terminology preferences
- Formatting standards
- Style guide rules

### Setting Audience Defaults

Modify [knowledge/tech-levels.md](knowledge/tech-levels.md) to reflect your typical audience:
- Adjust complexity baselines
- Add domain-specific knowledge levels
- Define prerequisites

### Custom Content Templates

Extend [knowledge/content-architecture.md](knowledge/content-architecture.md) with:
- Your documentation templates
- Content type structures
- Organization patterns

## Tips for Best Results

1. **Specify Audience**: Always indicate target technical level
2. **Provide Context**: Share product details, use cases, constraints
3. **Iterate**: Start with outline, refine progressively
4. **Request Reviews**: Ask for QA checklist application
5. **Check Examples**: Ensure code samples are tested and accurate

## Example Workflows

### Writing API Documentation
```
"I need to document our REST API for creating user accounts.
Audience: Intermediate developers
Include: Authentication, request/response examples, error handling"
```

### Creating a Tutorial
```
"Write a beginner tutorial for deploying a Node.js app to AWS Lambda.
Should take 15-20 minutes to complete with clear screenshots and code examples."
```

### Reviewing Technical Content
```
"Review this draft article about database indexing strategies.
Apply the QA checklist and suggest improvements for clarity and accuracy.
[paste content]"
```

## Quality Standards

This prompt enforces:
- **Accuracy**: Technical correctness verified
- **Clarity**: Complex concepts explained simply
- **Completeness**: All necessary information included
- **Consistency**: Uniform style and terminology
- **Accessibility**: Content usable by diverse audiences
- **Actionability**: Clear next steps and examples

## Platform Notes

Works well on both Claude and ChatGPT. The knowledge documents provide the same structured approach regardless of platform.

## Contributing

Have improvements or additional knowledge documents? See [CONTRIBUTING.md](../../../CONTRIBUTING.md).

## Related Prompts

- [UI Architect](../../development/ui-architect/) - For technical architecture discussions
- [Documentation Maintenance](../../development/documentation-maintenance/) - For maintaining living documentation

---

**Last Updated**: 2025-11-20
