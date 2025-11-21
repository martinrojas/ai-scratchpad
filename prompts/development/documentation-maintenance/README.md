# Documentation Maintenance

Standards and guidelines for maintaining living documentation in software projects.

## Overview

This prompt establishes standards for keeping project documentation accurate, up-to-date, and useful over time. It's particularly valuable for maintaining architectural docs, runbooks, wikis, and project knowledge bases that evolve with your codebase.

## Use Cases

- **Living Documentation**: Keep docs synchronized with code changes
- **Knowledge Base Maintenance**: Update wikis and internal docs
- **Onboarding Materials**: Ensure new developer docs stay current
- **Architecture Documentation**: Maintain system design docs and ADRs
- **Runbooks & Playbooks**: Keep operational docs accurate

## Quick Start

### Using with Command-Line AI Tools

Ideal for integration with code editors and terminal workflows:

```bash
# Use with Claude Code, Cursor, or similar tools
# The prompt guides documentation updates during development
```

### Using with Claude Projects

1. Create a "Documentation" project in Claude
2. Copy [prompt.md](prompt.md) into Project Instructions
3. Add your current documentation to Project Knowledge
4. Ask for documentation reviews and updates

### Using with Development Workflow

Integrate into your process:
1. Before code review: Check if docs need updates
2. During feature development: Create/update relevant docs
3. After deployment: Verify documentation accuracy
4. Quarterly: Comprehensive documentation audit

## Key Principles

### 1. Documentation as Code
- Version controlled alongside codebase
- Reviewed in pull requests
- Automated validation where possible
- Consistent formatting and structure

### 2. Living Documentation
- Updated with code changes, not after
- Reflects current system state
- Removes outdated information
- Includes "last verified" dates

### 3. Progressive Disclosure
- Overview → Details → Deep dives
- Newcomers and experts both served
- Clear navigation and hierarchy
- Searchable and scannable

### 4. Maintenance Triggers
Update documentation when:
- Architecture changes
- APIs are modified
- Dependencies are updated
- Deployment processes change
- Team processes evolve
- Questions reveal gaps

## Documentation Standards

### Required Elements

**Project README**
- Clear project description
- Quick start instructions
- Development setup
- Common commands
- Contributing guidelines

**Architecture Docs**
- System overview diagram
- Component relationships
- Key design decisions
- Technology choices with rationale

**API Documentation**
- Endpoint descriptions
- Request/response examples
- Authentication details
- Error handling
- Rate limits and constraints

**Runbooks**
- Step-by-step procedures
- Troubleshooting guides
- Emergency contacts
- Known issues and workarounds

### Documentation Structure

```
docs/
├── README.md                 # Documentation index
├── getting-started/
│   ├── setup.md
│   ├── quickstart.md
│   └── faq.md
├── architecture/
│   ├── overview.md
│   ├── decisions/           # ADRs
│   └── diagrams/
├── api/
│   ├── reference.md
│   └── examples/
├── guides/
│   ├── development.md
│   ├── deployment.md
│   └── testing.md
└── runbooks/
    ├── incidents.md
    └── maintenance.md
```

## Maintenance Workflows

### During Development

**When adding a feature:**
1. Create/update feature documentation
2. Add to changelog
3. Update API docs if applicable
4. Add examples or tutorials
5. Update architecture docs if structure changed

**When fixing a bug:**
1. Update troubleshooting guides
2. Add to known issues (if recurring)
3. Document root cause and solution
4. Update related how-to guides

**When refactoring:**
1. Update architecture documentation
2. Revise code examples
3. Update dependency information
4. Document migration path if breaking

### Regular Maintenance

**Weekly:**
- Review new GitHub issues for documentation gaps
- Update FAQ based on team questions
- Quick scan of recent PRs for doc needs

**Monthly:**
- Review analytics/search queries
- Update getting-started guides
- Verify external links
- Check screenshot accuracy

**Quarterly:**
- Comprehensive documentation audit
- Remove deprecated content
- Restructure based on usage patterns
- Update all "last verified" dates

## Quality Checklist

- [ ] **Accurate**: Reflects current system state
- [ ] **Complete**: Covers all critical paths
- [ ] **Clear**: Written for target audience
- [ ] **Current**: Recently verified/updated
- [ ] **Accessible**: Easy to find and navigate
- [ ] **Actionable**: Includes examples and next steps
- [ ] **Maintainable**: Not too detailed, won't rot quickly

## Tips for Best Results

1. **Update docs in the same PR as code changes**
2. **Use automation**: Generate API docs from code
3. **Make docs discoverable**: Clear navigation, good search
4. **Keep it DRY**: Link rather than duplicate
5. **Date-stamp content**: Add "Last updated" or "Verified on"
6. **Archive obsolete docs**: Don't delete, move to archive
7. **Encourage feedback**: Make it easy to suggest improvements

## Example Prompts

### Documentation Review
```
"Review our API documentation for accuracy and completeness.
The system has changed significantly in the last 6 months.
[paste documentation]"
```

### Gap Analysis
```
"Based on these recent GitHub issues, what documentation gaps do we have?
[paste list of common questions/issues]"
```

### Update Guide
```
"We just refactored our authentication system from JWT to session-based.
What documentation needs to be updated? Create a checklist."
```

## Anti-Patterns to Avoid

❌ **Documentation Last**: Writing docs only after code is done
❌ **Over-Documentation**: Documenting every implementation detail
❌ **Orphaned Docs**: Documentation separate from codebase
❌ **Copy-Paste Docs**: Duplicating content across multiple locations
❌ **Stale Examples**: Code examples that no longer work
❌ **No Ownership**: Nobody responsible for keeping docs current

## Integration Ideas

### CI/CD Integration
- Link checking in CI
- Markdown linting
- Spell checking
- Broken code example detection

### Editor Integration
- Doc snippets and templates
- Quick links to relevant docs
- Documentation preview

### Team Processes
- Documentation review in code review
- "Doc day" quarterly maintenance
- Documentation metrics in retrospectives

## Contributing

Improvements to these standards? See [CONTRIBUTING.md](../../../CONTRIBUTING.md).

## Related Prompts

- [Universal Content System](../../technical-writing/universal-content-system/) - For writing the documentation itself
- [UI Architect](../ui-architect/) - For architectural documentation needs

---

**Last Updated**: 2025-11-20
