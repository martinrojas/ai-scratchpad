# Prompt Engineering Guide

A practical guide to writing effective AI prompts, based on the patterns used in this collection.

## Table of Contents

- [Core Principles](#core-principles)
- [Prompt Structure](#prompt-structure)
- [Writing Techniques](#writing-techniques)
- [Knowledge Documents](#knowledge-documents)
- [Testing and Iteration](#testing-and-iteration)
- [Platform-Specific Tips](#platform-specific-tips)
- [Common Patterns](#common-patterns)
- [Troubleshooting](#troubleshooting)

## Core Principles

### 1. Clarity Over Cleverness

**Good**:
```markdown
You are a technical writer who creates API documentation.

When documenting endpoints:
1. Describe the purpose clearly
2. Show request and response examples
3. List all parameters with types
4. Explain error responses
```

**Avoid**:
```markdown
You're like a super smart documentation ninja who knows all the API tricks
and can write docs that are totally awesome...
```

**Why**: Explicit instructions produce consistent results. Vague or playful language introduces ambiguity.

### 2. Specific Role Definition

Define the expertise level and domain:

```markdown
You are a senior software architect with 10+ years of experience in
distributed systems, specializing in microservices architecture and
cloud-native applications.
```

**Not**:
```markdown
You are helpful and know about software.
```

**Impact**: Role definition sets the knowledge baseline and response tone.

### 3. Explicit Output Format

Always specify how you want responses structured:

```markdown
## Output Format

Respond using this structure:

1. **Summary** (2-3 sentences)
2. **Analysis**
   - Key findings
   - Trade-offs
   - Risks
3. **Recommendations** (prioritized list)
4. **Next Steps** (actionable items)
```

**Why**: Consistent format makes outputs more useful and predictable.

### 4. Set Boundaries

Define what the AI should and shouldn't do:

```markdown
**Do**:
- Provide specific code examples
- Explain trade-offs
- Suggest alternatives
- Ask clarifying questions when needed

**Don't**:
- Generate code without explanation
- Make assumptions about requirements
- Recommend deprecated technologies
- Skip error handling
```

## Prompt Structure

### Basic Template

```markdown
# [Role/Purpose]

[1-2 paragraphs defining role and expertise]

## Core Responsibilities

[3-5 key things the AI should do]

## Guidelines

### [Aspect 1]
[Specific guidelines]

### [Aspect 2]
[More guidelines]

## Output Format

[Structure for responses]

## Examples (Optional)

[Sample interactions]
```

### Advanced Template

For complex prompts, add:

```markdown
## Context

[Background information the AI needs]

## Quality Standards

[Specific criteria for good responses]

## Special Cases

[How to handle edge cases]

## Constraints

[Technical or practical limitations]
```

## Writing Techniques

### Progressive Disclosure

Start simple, add complexity gradually:

**Level 1 - Basic prompt**:
```markdown
You are a code reviewer. Review code for quality and best practices.
```

**Level 2 - Add structure**:
```markdown
You are a code reviewer. For each review:
1. Check for bugs and errors
2. Evaluate code quality
3. Suggest improvements
```

**Level 3 - Add detail**:
```markdown
You are a senior code reviewer specializing in Python and JavaScript.

For each review, analyze:

**Correctness**:
- Logic errors
- Edge cases
- Error handling

**Quality**:
- Code clarity
- Naming conventions
- Code organization

**Best Practices**:
- Security considerations
- Performance implications
- Framework-specific patterns

Provide specific, actionable feedback with code examples.
```

### The Sandwich Method

Layer instructions for clarity:

1. **What** (high-level purpose)
2. **How** (specific guidelines)
3. **Why** (context and rationale)

**Example**:
```markdown
# What
You create concise meeting summaries from transcripts.

# How
Extract:
1. Key decisions made
2. Action items with owners
3. Follow-up questions

Format as structured markdown.

# Why
Busy stakeholders need to quickly understand outcomes without
reading full transcripts. Action items must be trackable.
```

### Example-Driven Instruction

Show, don't just tell:

**Without examples**:
```markdown
Write clear, concise error messages.
```

**With examples**:
```markdown
Write clear, concise error messages.

**Good**:
"Invalid email format. Expected: user@domain.com"

**Not**:
"Error 422: Validation failed"

**Good**:
"File too large. Maximum size: 10MB. Your file: 15MB"

**Not**:
"Upload failed"
```

### Constraint Specification

Define the boundaries explicitly:

```markdown
## Constraints

**Response Length**:
- Summaries: 2-3 sentences max
- Explanations: 1 paragraph
- Code examples: <50 lines

**Tone**:
- Professional but conversational
- No jargon without explanation
- Direct, not verbose

**Scope**:
- Focus on asked question only
- Don't add unrequested features
- Ask before major assumptions
```

## Knowledge Documents

### When to Use KDs

Create separate knowledge documents when:

- **Volume**: Supporting content exceeds 100 lines
- **Modularity**: Content applies to multiple scenarios
- **Maintenance**: Guidelines updated independently
- **Complexity**: Detailed reference materials needed

### KD Structure

```markdown
# [Topic]

## Purpose
[Why this knowledge document exists]

## [Main Section 1]

### [Subsection]
[Detailed content]

### [Subsection]
[More content]

## [Main Section 2]

[Organized information]

## Quick Reference
[Condensed version for fast lookup]
```

### KD Best Practices

1. **Stay Focused**: One topic per document
2. **Be Comprehensive**: Cover the topic thoroughly
3. **Provide Examples**: Show practical application
4. **Cross-Reference**: Link to related KDs
5. **Quick Reference**: Include TL;DR section

### Types of Knowledge Documents

**Guidelines**:
```markdown
# Context Guidelines

## When to Ask Questions
- User request is ambiguous
- Multiple valid approaches exist
- Requirements seem incomplete

## When to Proceed
- Request is clear and specific
- Standard approach applies
- All necessary context provided
```

**Standards**:
```markdown
# Code Quality Standards

## Security
- Validate all user input
- Use parameterized queries
- Sanitize output

## Performance
- Cache expensive operations
- Lazy-load when possible
- Minimize database queries
```

**Templates**:
```markdown
# Response Templates

## Code Review Template

### Summary
[1-2 sentence overview]

### Issues Found
- **Critical**: [List]
- **Important**: [List]
- **Minor**: [List]

### Recommendations
[Prioritized suggestions]
```

**Examples**:
```markdown
# Example Workflows

## Scenario 1: API Documentation

**Input**: OpenAPI spec
**Process**: Extract endpoints, parameters, examples
**Output**: Markdown documentation with usage examples
```

## Testing and Iteration

### Testing Strategy

1. **Baseline Test**: Does it work at all?
   ```
   Test: Basic request → Should get reasonable response
   ```

2. **Edge Cases**: How does it handle unusual inputs?
   ```
   Test: Ambiguous request → Should ask clarifying questions
   Test: Missing info → Should identify what's needed
   Test: Invalid input → Should gracefully explain issue
   ```

3. **Consistency**: Are outputs predictable?
   ```
   Test: Same input multiple times → Similar structure/quality
   ```

4. **Format Compliance**: Does it follow output structure?
   ```
   Test: Various requests → All use specified format
   ```

### Iteration Process

**Start with hypothesis**:
```markdown
# V1
You are a code reviewer.
Review code for bugs and improvements.
```

**Test and observe**:
- Issue: Responses too verbose
- Issue: Misses security concerns
- Issue: Format inconsistent

**Refine based on results**:
```markdown
# V2
You are a senior code reviewer.

Focus on:
1. Critical bugs and security issues
2. Code quality improvements
3. Best practice violations

Keep feedback concise and actionable.
Use this format: [specific format]
```

**Test again**:
- Better: Responses more focused
- Better: Security checks included
- New issue: Sometimes too brief

**Continue refining**:
```markdown
# V3
[Add examples of good vs too-brief feedback]
[Add security checklist]
[Add "explain why" for important issues]
```

### Debugging Prompts

**Problem**: AI doesn't follow instructions

**Solutions**:
- Make instructions more explicit
- Add examples showing desired behavior
- Check for conflicting instructions
- Simplify complex multi-step instructions

**Problem**: Inconsistent output format

**Solutions**:
- Provide exact template with placeholders
- Show before/after examples
- Add format validation in guidelines

**Problem**: AI too verbose or too brief

**Solutions**:
- Specify length constraints explicitly
- Show examples at the right detail level
- Add guidelines for when to expand vs summarize

## Platform-Specific Tips

### Claude

**Strengths**:
- Nuanced reasoning and context awareness
- Following complex, principle-based instructions
- Conversational, natural language guidelines

**Optimization**:
```markdown
# Works well on Claude
Approach this with careful consideration of trade-offs.
When multiple solutions exist, analyze each thoughtfully.
```

**Example**:
```markdown
You are a thoughtful technical advisor.

When discussing architecture:
- Consider both immediate and long-term implications
- Weigh technical debt against delivery speed
- Adapt recommendations to team maturity and constraints
```

### ChatGPT (GPT-4/5)

**Strengths**:
- Structured, step-by-step instructions
- Role-playing and persona adherence
- Explicit examples and templates

**Optimization**:
```markdown
# Works well on GPT
Follow these steps in order:
1. First, do X
2. Then, do Y
3. Finally, do Z

Use this exact format: [template]
```

**Example**:
```markdown
You are a technical writer. Follow this process:

Step 1: Analyze the input
- Identify key concepts
- Note target audience
- List requirements

Step 2: Structure the content
- Create outline
- Organize information hierarchically
- Plan examples

Step 3: Write the documentation
- Use this template: [template]
- Include these sections: [list]
- Format as markdown
```

### Platform-Agnostic Prompts

Most prompts work across platforms. Focus on:
- Clear role definition
- Explicit instructions
- Good examples
- Structured output

Create platform variants only when there's a significant difference in approach or capability.

## Common Patterns

### The Advisor Pattern

```markdown
You are a [domain] advisor helping [audience] make informed decisions.

Your approach:
1. Understand the context and constraints
2. Analyze available options
3. Evaluate trade-offs
4. Provide clear recommendation with rationale

Always consider: [key factors]
```

**Use for**: Technical decisions, architecture discussions, tool selection

### The Reviewer Pattern

```markdown
You are a [type] reviewer ensuring [quality standards].

Review process:
1. Check for [critical issues]
2. Evaluate [quality criteria]
3. Suggest [improvements]

Provide:
- Clear assessment
- Specific feedback
- Actionable recommendations
```

**Use for**: Code review, content review, design review

### The Generator Pattern

```markdown
You create [output type] based on [input type].

Requirements:
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

Format:
[Specific structure]

Quality standards:
[Criteria for good output]
```

**Use for**: Documentation generation, content creation, code generation

### The Analyzer Pattern

```markdown
You analyze [subject] to identify [insights].

Analysis framework:
1. [Dimension 1]
2. [Dimension 2]
3. [Dimension 3]

Output:
- Key findings
- Patterns and trends
- Recommendations

Base analysis on: [criteria]
```

**Use for**: Data analysis, performance review, system assessment

### The Teacher Pattern

```markdown
You are an expert teacher explaining [topic] to [audience].

Teaching approach:
1. Start with fundamentals
2. Use clear examples
3. Build complexity gradually
4. Check understanding

Adapt explanations to:
- Prior knowledge: [level]
- Learning goals: [objectives]
- Context: [situation]
```

**Use for**: Educational content, tutorials, onboarding materials

## Troubleshooting

### Issue: Inconsistent Responses

**Symptoms**: Same input gives widely varying outputs

**Fixes**:
- Add more explicit structure
- Provide format templates
- Include more examples
- Reduce ambiguous language

**Example Fix**:
```markdown
# Before
Write a good summary.

# After
Write a summary following this structure:

**Overview** (1 sentence)
**Key Points** (3-5 bullets)
**Conclusion** (1 sentence)

Length: 100-150 words total
```

### Issue: AI Ignores Instructions

**Symptoms**: Responses don't follow guidelines

**Fixes**:
- Put critical instructions early
- Repeat important constraints
- Use stronger language ("Always", "Never", "Must")
- Add examples showing compliance

**Example Fix**:
```markdown
# Before
Try to keep responses concise.

# After
IMPORTANT: Keep all responses under 200 words.

For longer topics:
- Prioritize key information
- Use bullet points
- Link to details instead of expanding

Example: [show concise response]
```

### Issue: Too Generic or Too Specific

**Symptoms**: Responses don't match needed detail level

**Fixes**:
- Specify audience expertise level
- Define depth of detail needed
- Show examples at right level
- Add guidelines for when to expand/summarize

**Example Fix**:
```markdown
Audience: Intermediate developers (2-5 years experience)

Detail level:
- Explain WHY, not just HOW
- Reference but don't teach basics
- Dive deep on advanced concepts
- Include edge cases and gotchas

Example explanation level: [show sample]
```

### Issue: Wrong Tone or Style

**Symptoms**: Responses too formal/casual, wrong voice

**Fixes**:
- Define voice explicitly
- Show tone examples
- Specify formality level
- Include style guidelines

**Example Fix**:
```markdown
Voice and Tone:
- Professional but conversational
- Confident but not arrogant
- Helpful but not condescending

Like this: "Let's explore three approaches. Each has trade-offs..."
Not this: "You should obviously use approach X because..."
```

## Advanced Techniques

### Conditional Logic

```markdown
If the request involves [condition]:
- Follow [specific approach]
- Include [additional elements]

Otherwise:
- Use [standard approach]
```

### Contextual Adaptation

```markdown
Adapt your response based on:
- User expertise: Adjust technical depth
- Urgency: Prioritize quick wins vs comprehensive solutions
- Scope: Focus on immediate issue vs systemic improvements
```

### Meta-Instructions

```markdown
## Meta-Guidelines

If my instructions seem:
- Unclear: Ask for clarification
- Contradictory: Point out the conflict
- Incomplete: Identify missing information
- Impossible: Explain the constraints
```

## Resources

### Learn More

- Browse [example prompts](../../prompts/) in this collection
- Check [prompt templates](../templates/) for starting points
- Read [architecture doc](../../docs/architecture.md) for organizational patterns

### Contributing

Create better prompts and share them! See [CONTRIBUTING.md](../../CONTRIBUTING.md).

---

**Last Updated**: 2025-11-20
