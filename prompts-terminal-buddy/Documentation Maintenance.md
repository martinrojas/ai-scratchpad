# Documentation Maintenance Standards

**Project Documentation Philosophy**: All projects I work on should maintain living documentation that stays current with their actual state. These standards should be added to each project's instruction files (`AGENTS.md`, `CLAUDE.md`, `.claude/README.md`, etc.) to ensure consistency across teams and collaboration sessions.

## Propagating Documentation Standards

**Add to project instructions**: When working on a new project, check if these documentation maintenance standards exist in the project's guidance files. If not, adapt and add them:

- For **software projects**: Add to root `AGENTS.md` or `CLAUDE.md`
- For **monorepos**: Add to root guidance, reference from package-specific files
- For **documentation repos**: Adapt to focus on document maintenance rather than code
- For **small projects**: Add simplified version to `README.md`

**Purpose**: Ensures all users (human and AI) follow consistent documentation practices, making collaboration smoother and knowledge more accessible.

## Keep Documentation Current

When making significant changes, update relevant documentation:

**For code projects:**

- **Root instruction files** (`AGENTS.md`, `CLAUDE.md`) - Project-wide conventions and architecture
- **Package/module-specific files** - Component-specific details
- **Plan documents** (e.g., `*_PLAN.md`) - Update with current status and learnings
- **API documentation** - Update if interfaces or usage patterns change
- **Build configuration** - Keep package.json, Cargo.toml, etc. current

**For documentation projects:**

- **Instruction files** - System conventions and maintenance rules
- **Data/content files** - Keep structure consistent with guidelines
- **Configuration files** - Update if format requirements change

**For all projects:**

- **README.md** - Setup instructions, current features, usage examples
- **Architecture docs** - System design, integration points
- **Known issues** - Current blockers, workarounds, technical debt

This ensures documentation stays synchronized with reality and provides accurate context.

## Living Documentation Philosophy

**Document plans and decisions in markdown files** - All architectural decisions, migration plans, design choices, and technical strategies should be documented in dedicated `.md` files at the appropriate level:

- Project root for system-wide concerns
- Package/module level for local concerns
- Data-specific for tracking/reporting projects

**Rewrite, don't append** - Treat documentation like code that needs refactoring:

- **Update existing content** rather than adding dated sections
- **Rewrite outdated sections** to reflect current reality, not historical evolution
- **Remove completed or obsolete information** rather than striking through or marking as "old"
- **Keep documentation fresh and relevant** - focus on what users need to know _now_
- **Archive if needed** - Move historical information to separate archive files if valuable

**What to document:**

- Architectural decisions and rationale
- Migration plans with current status
- Component/system patterns and conventions
- API contracts and integration points
- Known issues and workarounds
- Setup and configuration requirements

**How to maintain living docs:**

- Include `Last updated: YYYY-MM-DD` at the top of plan/decision files
- Remove status markers (✅ Done, ⏳ In Progress) after integrating learnings
- Consolidate multiple decision files as understanding evolves
- Use clear, descriptive file names (`SHELL_MIGRATION_PLAN.md` not `NOTES_2025_01.md`)
- Rewrite plans when they change significantly - don't document change history in the plan itself

**Bad example** (history in the document):

```markdown
## Old Approach (Deprecated 2025-01-15)

We used to do X because Y.

## New Approach (As of 2025-02-20)

Now we do Z because W.
```

**Good example** (current state only):

```markdown
## Current Approach

We do Z because W.

Last updated: 2025-02-20
```

## Documentation Structure

**Organize documentation consistently** - Projects with multiple documentation files should use organized directories:

```plaintext
/docs/                      # (or project-appropriate location)
├── plans/                  # Feature plans, roadmaps, migration strategies
├── architecture/           # System design, technical specifications
└── decisions/              # Architecture Decision Records (ADRs)
```

**File placement guidelines:**

- **plans/** - Implementation plans, migration strategies, testing plans
  - Examples: `integration-testing-plan.md`, `api-migration-plan.md`
- **architecture/** - System design, architecture diagrams, specifications
  - Examples: `authentication-flow.md`, `state-management.md`, `data-flow.md`
- **decisions/** - ADRs for significant technical choices
  - Examples: `001-use-vitest-over-jest.md`, `002-database-selection.md`

**File naming conventions:**

- Use kebab-case for all documentation files (`integration-testing-plan.md`)
- Prefix ADRs with numbers for ordering (`001-decision-name.md`)
- Be descriptive and specific in file names
- Include context in name (`AUTH_PLAN.md` not `PLAN.md`)

**When to create subdirectories:**

- Create `docs/` directory when you have 3+ related documentation files
- Keep `AGENTS.md`/`CLAUDE.md` and `README.md` at project root
- Move detailed plans and decisions into subdirectories for organization
- For simple projects, root-level markdown files are sufficient

## Adapting for Different Project Types

**Software projects**: Full structure with plans, architecture, decisions, and code-specific guidance

**Documentation projects**: Focus on document maintenance, data integrity, update workflows

**Monorepos**: Root-level standards + package-specific adaptations

**Data/tracking systems**: Emphasize data freshness, archive strategies, summary maintenance

**Personal projects**: Simplified version focused on setup, current status, and next steps

## Implementation Checklist

When starting work on a project:

1. ☐ Check if project has `AGENTS.md`, `CLAUDE.md`, or similar instruction file
2. ☐ If present, verify it includes documentation maintenance standards
3. ☐ If missing or incomplete, suggest adding/updating with adapted version of these standards
4. ☐ Follow the project's existing documentation conventions
5. ☐ Update documentation whenever making significant changes
6. ☐ Keep "Last updated" dates current
7. ☐ Refactor documentation when it becomes stale or inconsistent
