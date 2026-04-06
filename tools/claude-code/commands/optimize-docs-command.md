# Optimize & Maintain Project Documentation

Audit this repository's documentation. If the project lacks structure, scaffold it. If structure already exists, perform a maintenance pass to keep docs lean, current, and well-organized.

## Phase 1: Discovery

Use the Explore Agent to scan the full repo. **Read every documentation file** — don't just list them. You need to understand what each one says to make decisions.

Search for:

- **Instruction files**: `AGENTS.md`, `CLAUDE.md`, `.claude/README.md` at project root
- **README.md**: Current state, setup instructions, feature list
- **Documentation directories**: `docs/`, `docs/plans/`, `docs/architecture/`, `docs/decisions/`
- **Plan and decision files**: `*_PLAN.md`, ADRs, architecture docs
- **Package-level instructions**: Instruction files in subdirectories (monorepos)
- **Any other `.md`, `.txt`, `.rst` files** outside dependency directories

Skip `node_modules/`, `.git/`, `vendor/`, `dist/`, `.output/`, and other dependency/build directories.

## Phase 2: Assessment & Mode Selection

Evaluate what exists to determine the operating mode:

### Triage checklist

| Question | Action if No |
|----------|-------------|
| Does `AGENTS.md` exist at root? | **Setup mode** — Create it (Phase 3) |
| Does `CLAUDE.md` exist with real content (not just `@AGENTS.md`)? | Merge into `AGENTS.md`, replace with `@AGENTS.md` |
| Does the instruction file include documentation maintenance standards? | **Setup mode** — Add them (Phase 3) |
| Does the instruction file include a project policies section? | **Setup mode** — Add placeholder (Phase 3) |
| Is `README.md` current with setup, features, and usage? | Update it |
| Are there 3+ doc files that should be organized into `docs/`? | Propose directory structure |

### Mode decision

- **Setup mode**: `AGENTS.md` doesn't exist, or exists but lacks the standard structure (no routing table, no maintenance standards, no policies section). → Go to **Phase 3: Scaffold**.
- **Maintenance mode**: `AGENTS.md` exists with routing table, conventions, and maintenance standards. `docs/` directory is organized. → Go to **Phase 4: Maintenance**.
- **Hybrid**: Some structure exists but is incomplete. → Run Phase 3 for missing pieces, then Phase 4 for existing content.

---

## Phase 3: Scaffold Instruction Files (Setup Mode)

_Skip this phase if the project already has a well-structured `AGENTS.md` and `docs/` directory._

### AGENTS.md (source of truth)

`AGENTS.md` is the canonical instruction file. It is tool-agnostic and works with any AI assistant or developer workflow. All project guidance, conventions, and standards live here.

Create or update `AGENTS.md` with these sections, preserving any existing project-specific content:

```markdown
# Project Name

> Brief description of what this project does.

Last updated: YYYY-MM-DD

## Project Overview

<!-- What this project is, its purpose, and key technologies. -->

## Quick Start

<!-- Bare minimum to get running. No explanations — just the commands. -->

## Architecture (Summary)

<!-- 5-10 lines max. Key components and how they connect. -->
<!-- For details: @docs/architecture/<relevant-file>.md -->

## Conventions

<!-- Only the rules that apply to EVERY file in the repo. -->
<!-- Language-specific or domain-specific conventions go in subdirectory AGENTS.md files. -->

## Key Context Files

<!-- Point agents to the right doc based on what they're working on. -->

| When working on... | Read first |
|---|---|
| System architecture | `@docs/architecture/<file>.md` |
| A new feature | `@docs/plans/<active-plan>.md` |
| Trade-off or tech choice | `@docs/decisions/` |

<!-- Add rows as docs are created. Remove rows when docs are deleted. -->

## Project Policies

<!-- CUSTOMIZE: Add company and team policies here. Examples below. -->

<!--
### Code Review Policy
- All changes require at least one approval before merge
- Security-sensitive changes require team lead review

### Branch Strategy
- main: production-ready code
- feature/*: new features
- fix/*: bug fixes

### Dependency Policy
- No new dependencies without team discussion
- Pin major versions, allow minor/patch updates

### Security & Compliance
- No secrets in code; use environment variables
- All user input must be validated and sanitized

### AI Assistant Guidelines
- Agents may create and modify code but must not push to main directly
- Generated code must pass all existing tests before commit
- Agents should update documentation when making significant changes
-->

## Documentation Maintenance

When making significant changes:

1. Update the **relevant doc** in `docs/`, not this file
2. If a new doc is created, add a row to **Key Context Files** above
3. If a doc is deleted, remove its row
4. Rewrite content to reflect current state — don't append updates

### Documentation Structure

```
docs/
├── plans/          # Active feature plans, roadmaps, migration strategies
├── architecture/   # System design, data flow, component diagrams
├── decisions/      # ADRs (architecture decision records)
├── guides/         # How-tos, onboarding, workflow docs
└── reference/      # API docs, config reference, glossary
```

### File Naming

- kebab-case for documentation files (`api-migration-plan.md`)
- Prefix ADRs with numbers (`001-database-selection.md`)
- Be descriptive and specific (`AUTH_PLAN.md` not `PLAN.md`)
```

### CLAUDE.md (reference file)

If the project uses Claude Code, create `CLAUDE.md` containing only:

```
@AGENTS.md
```

The `@` syntax makes Claude Code load `AGENTS.md` content. This avoids duplication while maintaining compatibility.

**Migration**: If `CLAUDE.md` exists with real content, run `git mv CLAUDE.md AGENTS.md`, then create the new `CLAUDE.md` reference file.

### Adapt to Project Type

Scale the documentation to fit the project:

| Project Type | Instruction File | Docs Structure | Policies Section | Notes |
|---|---|---|---|---|
| **Software project** | Full `AGENTS.md` | `docs/` with subdirectories | Full policies | Include architecture, conventions, testing |
| **Monorepo** | Root `AGENTS.md` + package-level files | Per-package as needed | Root-level, referenced by packages | Reference root standards from package docs |
| **Documentation repo** | Adapted `AGENTS.md` | Matches content structure | Content maintenance policies | Focus on document maintenance and data integrity |
| **Small/personal project** | Simplified `AGENTS.md` or standards in `README.md` | Root-level files only | Minimal | Setup, current status, next steps |
| **Data/tracking system** | Full `AGENTS.md` | `docs/` focused on data | Data freshness policies | Emphasize archive strategies and update workflows |

After scaffolding, continue to **Phase 4** if there are existing docs that need cleanup.

---

## Phase 4: Maintenance (Ongoing Upkeep)

_This phase assumes `AGENTS.md` already exists and the basic `docs/` structure is in place._

**Goal**: Keep `AGENTS.md` lean as a routing file, ensure `docs/` content is current, remove stale or duplicate content, and harvest valuable context from completed work before discarding it.

### Step 1: Inventory

For each documentation file found in Phase 1, record:

| Field | How to determine |
|---|---|
| **Path** | File location in the repo |
| **Purpose** | Summarize in one line what it covers (you read it in Phase 1) |
| **Last touched** | Check git history for the last meaningful commit (not just formatting) |
| **Stale?** | Compare content against current code — does it reference removed features, old dates, completed migrations, or contradict what's actually in the repo? |
| **Duplicated?** | Does another file cover the same topic? Note the overlap |

### Step 2: Clean Up

#### Harvest implemented plans before removing them

Plans that have been fully implemented still contain valuable context. Before deleting them:

1. **Extract decisions** — If the plan explains *why* an approach was chosen or trade-offs that were made, capture that as an ADR in `docs/decisions/`. Keep it brief: what was decided, why, and what alternatives were rejected.
2. **Extract architecture** — If the plan describes system design, data models, or component relationships that are now part of the codebase, merge that content into the relevant file in `docs/architecture/`. Update it to reflect how things actually landed, not how they were planned.
3. **Then delete the plan** — Once the durable knowledge is captured elsewhere, remove the plan file. Don't keep it around as "history" — that's what git is for.

> **Quick test**: Read the implemented plan and ask — "If a new developer joined tomorrow, would anything in here help them understand the system?" If yes, that piece belongs in `docs/architecture/` or `docs/decisions/`. Everything else (status updates, task lists, rollout steps) gets dropped.

#### Delete

- Implemented plans — after harvesting per above
- Duplicates — if two files cover the same topic, merge the better one and delete the other
- Empty or placeholder files with no real content

#### Rewrite, don't append

For any doc that's partially stale:

- Remove completed items, old status updates, and struck-through text
- Rewrite to reflect **current state only**
- Update `Last updated:` to today's date

> **Rule**: If you're unsure whether something is stale, flag it for human review — don't delete it.

### Step 3: Organize

Ensure files are in the standard `docs/` structure. Create directories only as needed — don't scaffold empty folders.

```
docs/
├── plans/          # Active feature plans, roadmaps, migration strategies
├── architecture/   # System design, data flow, component diagrams
├── decisions/      # ADRs (architecture decision records)
├── guides/         # How-tos, onboarding, workflow docs
└── reference/      # API docs, config reference, glossary
```

**Sorting rules:**

| If the doc is about... | It goes in... |
|---|---|
| What we're building next, migration steps, rollout plan | `docs/plans/` |
| How the system works, component relationships, data model | `docs/architecture/` |
| Why we chose X over Y, trade-off analysis | `docs/decisions/` |
| How to do something (setup, deploy, debug) | `docs/guides/` |
| API surface, config options, environment variables | `docs/reference/` |

After moving, update any cross-references or links in other docs.

### Step 4: Lean out AGENTS.md

`AGENTS.md` should be a **routing table with context**, not a copy of every doc. Agents read it first on every task — keep it fast to parse.

#### What stays in AGENTS.md

- Project overview (brief — 2-3 sentences)
- Quick start commands
- Architecture summary (5-10 lines max, with `@` reference to details)
- Universal conventions (rules that apply to every file)
- **The routing table** (Key Context Files) — this is the key piece
- Project policies
- Documentation maintenance standards (brief)

#### What moves OUT of AGENTS.md

- Detailed architecture explanations → `docs/architecture/`
- Feature plans → `docs/plans/`
- Setup guides longer than 10 lines → `docs/guides/`
- API documentation → `docs/reference/`
- Decision rationale → `docs/decisions/`
- Troubleshooting tables longer than ~10 rows → `docs/guides/troubleshooting.md` (keep top 5 most common in AGENTS.md)
- Environment variable details → `docs/reference/` or `.env.example`

#### The `@` reference pattern

Use `@path/to/file.md` syntax in the routing table so agents and Claude Code know to pull in that file when relevant.

For subdirectories in monorepos, each package can have its own `AGENTS.md` that references back:

```markdown
<!-- packages/api/AGENTS.md -->
@../../AGENTS.md

## API-Specific Conventions
<!-- Only what differs from or extends the root conventions. -->
```

---

## Phase 5: Validate

After all changes, verify:

- [ ] `AGENTS.md` is under ~150 lines (not counting template comments)
- [ ] Every file in `docs/` is referenced from the routing table or another doc
- [ ] No orphaned docs — nothing in `docs/` that isn't reachable
- [ ] No duplicated content between `AGENTS.md` and files in `docs/`
- [ ] All `@` references point to files that exist
- [ ] `CLAUDE.md` contains only `@AGENTS.md` (if it exists)
- [ ] `Last updated` dates are current on all modified files
- [ ] No empty directories in `docs/`

## Phase 6: Report

Provide a summary based on which mode ran:

### If Setup mode ran:

1. **Files found** — What documentation already existed
2. **Changes made** — Files created, renamed, updated, or reorganized
3. **Manual follow-ups** — Items requiring human review or decisions
4. **Documentation health** — Rate as `basic` / `good` / `comprehensive`

### If Maintenance mode ran:

1. **Plans harvested** — Which plans were processed, what decisions/architecture were extracted, and where that content now lives
2. **Files deleted** — With reason (implemented plan, stale, duplicate, empty)
3. **Files moved** — Old path → new path
4. **Files rewritten** — What changed and why
5. **AGENTS.md diff summary** — What was removed vs. kept, line count before/after
6. **Flagged for review** — Anything you weren't sure about
7. **Routing table** — The final Key Context Files table
8. **Documentation health** — Rate as `basic` / `good` / `comprehensive`

---

## Rules

- **`AGENTS.md` is the single source of truth** for all project instructions
- **Preserve existing content** — Merge and enhance, don't overwrite without confirmation
- **Don't fabricate project details** — Use placeholders where specifics are unknown
- **Use today's date** for all `Last updated` entries
- **Customize the Policies section** — This is where company-specific and team-specific rules go; prompt the user to fill it in if creating from scratch
- **Flag, don't delete, when unsure** — If you can't confirm something is stale by checking code or git history, flag it for human review
- **Harvest before you delete** — Never remove a plan without first checking for extractable decisions or architecture
