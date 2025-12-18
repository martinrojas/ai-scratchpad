# Optimize Repository Documentation

Analyze and optimize this repository's documentation following the AGENTS.md pattern and documentation maintenance standards.

## Your Task

Perform a comprehensive documentation audit and optimization:

### 1. Discovery Phase

First, search for existing documentation files:
- Look for `AGENTS.md`, `CLAUDE.md`, `.claude/README.md` at project root
- Check for `README.md` and its current state
- Find any `docs/` directory structure
- Locate plan files (`*_PLAN.md`), decision records, or architecture docs
- Check for package-level instruction files in subdirectories

### 2. Assessment Phase

Evaluate the current documentation state:
- Does the project have a root instruction file (`AGENTS.md` or `CLAUDE.md`)?
- If `CLAUDE.md` exists, should it be renamed to `AGENTS.md` for tool-agnostic consistency?
- Does the instruction file include documentation maintenance standards?
- Is the README.md current with setup instructions and features?
- Are there stale or outdated docs that need updating?
- Is documentation organized consistently (docs/ structure if 3+ files)?

### 3. Optimization Actions

Based on your assessment, perform these actions as appropriate:

**If no instruction file exists:**
- Create `AGENTS.md` with project-specific guidance AND documentation standards section

**If CLAUDE.md exists with content:**
- Rename to AGENTS.md: `git mv CLAUDE.md AGENTS.md`
- Create new CLAUDE.md with single line: `@AGENTS.md`
- Add documentation maintenance standards to AGENTS.md if missing

**If both CLAUDE.md and AGENTS.md exist:**
- Check if CLAUDE.md already references AGENTS.md (`@AGENTS.md`)
- If not: Merge unique content into AGENTS.md, replace CLAUDE.md with `@AGENTS.md`

**If instruction file exists but lacks standards:**
- Add the Documentation Maintenance Standards section

**For all projects:**
- Ensure README.md has current setup instructions
- Suggest docs/ directory structure if 3+ documentation files exist
- Update any "Last updated" dates to today
- Identify and flag stale documentation for review

### 4. Documentation Standards to Incorporate

Add this section to the project's instruction file (AGENTS.md) if not present:

```markdown
## Documentation Maintenance Standards

### Keep Documentation Current

When making significant changes, update relevant documentation:
- **AGENTS.md** - Project-wide conventions and architecture
- **README.md** - Setup instructions, current features, usage examples
- **Plan documents** (`*_PLAN.md`) - Update with current status and learnings
- **API documentation** - Update if interfaces or usage patterns change

### Living Documentation Philosophy

- **Rewrite, don't append** - Update existing content rather than adding dated sections
- **Remove completed/obsolete information** - Don't strike through or mark as "old"
- **Keep documentation fresh** - Focus on what users need to know now
- Include `Last updated: YYYY-MM-DD` at the top of plan/decision files

### Documentation Structure

For projects with 3+ documentation files, use organized directories:
```
/docs/
├── plans/          # Feature plans, migration strategies
├── architecture/   # System design, specifications
└── decisions/      # Architecture Decision Records (ADRs)
```

### File Naming Conventions

- Use kebab-case for documentation files (`api-migration-plan.md`)
- Prefix ADRs with numbers (`001-database-selection.md`)
- Be descriptive and specific (`AUTH_PLAN.md` not `PLAN.md`)
```

### 5. Report

After completing the optimization, provide a summary:
- What documentation files were found
- What changes were made (renamed, created, updated)
- What manual follow-ups the user should consider
- Current documentation health score (basic/good/comprehensive)

## Important Guidelines

- **AGENTS.md is source of truth** - All instruction content goes in AGENTS.md
- **CLAUDE.md references AGENTS.md** - Create with single line `@AGENTS.md` for Claude Code compatibility
- Preserve all existing project-specific content when adding standards
- Don't overwrite custom documentation without confirmation
- Adapt the standards section based on project type (software/monorepo/docs/small)
- Use today's date for any "Last updated" entries: $CURRENT_DATE

## Reference Pattern

The `@` syntax includes another file's content. This allows:
- `AGENTS.md` - Tool-agnostic, works with any AI assistant
- `CLAUDE.md` containing `@AGENTS.md` - Claude Code loads AGENTS.md content

Example CLAUDE.md (entire file):
```
@AGENTS.md
```
