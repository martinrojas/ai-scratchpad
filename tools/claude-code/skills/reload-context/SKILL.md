---
name: reload-context
description: Reload full project context at the start of a new conversation by reading living documentation, verifying current state, and identifying next steps.
allowed-tools: Read, Glob, Grep, Task
---

# Reload Project Context

**Purpose**: Reload full project context at the start of a new conversation by reading living documentation, verifying current implementation state, and identifying next steps.

## Instructions

Follow these steps in order to rebuild complete project context:

### Phase 1: Read Core Documentation

1. **Read project instruction file(s)** - `CLAUDE.md` and/or `AGENTS.md`
   - If both exist: read both and note any conflicts
   - If only one exists: use that file as the primary instruction source
   - If neither exists: state this explicitly and continue with available project docs
   - Note: Key technologies, development commands, coding patterns
   - Pay special attention to: Documentation standards, styling guidelines, recent improvements

2. **List active plans** - Find all files in `/docs/plans/`
   - These are the ONLY plans currently in progress
   - Archived plans are in `/docs/archive/` (reference only, not active work)

3. **Read each active plan** - Understand current objectives and status
   - Note: What's marked as IN PROGRESS
   - Note: What's marked as COMPLETED
   - Note: What's marked as PAUSED
   - Identify: Next immediate steps listed in each plan

### Phase 2: Verify Implementation State

4. **Use Explore subagent** to verify current codebase state
   - Launch with `subagent_type: "Explore"` and medium thoroughness
   - Ask: "What is the current state of components and features mentioned in active plans?"
   - Cross-reference: Do active plans accurately reflect what's in the codebase?
   - Identify: Any discrepancies between documentation and actual code

### Phase 3: Assess Next Steps

5. **Use Plan subagent** (if needed) to identify optimal next steps
   - Launch with `subagent_type: "Plan"`
   - Ask: "Based on active plans and current implementation, what are the logical next steps?"
   - Consider: Dependencies, priorities, completion criteria
   - Flag: Any blockers or missing information

### Phase 4: Present Comprehensive Summary

Provide a structured summary with these sections:

#### Project Overview
- Project type and tech stack
- Current development phase
- Key architectural decisions

#### Active Work
- List each active plan with status
- What's in progress right now
- What's blocked or paused

#### Recent Completions
- What was recently finished (from "Recent Improvements" in `CLAUDE.md` and/or `AGENTS.md`)
- What was archived since last session

#### Implementation State
- What the Explore subagent found
- Any discrepancies between docs and code
- Current codebase health

#### Recommended Next Steps
- Prioritized list of next actions
- Dependencies and prerequisites
- Estimated effort/complexity

#### Flags & Blockers
- Any issues discovered
- Missing information
- Decisions needed

## Output Format

Present findings in a clear, scannable format using:
- Headers for organization
- Bullet points for lists
- Status indicators where appropriate
- Code references with `file_path:line_number` where relevant
- Brief explanations (not just data dumps)

## Success Criteria

After running this command, the user should have:
- Complete understanding of current project state
- Clear picture of what's in progress
- Verified implementation matches documentation
- Actionable next steps with context
- Awareness of any blockers or issues

## Tips

- **Be thorough but concise** - Quality over quantity
- **Flag discrepancies** - If docs don't match code, say so
- **Prioritize recent activity** - Focus on what's active, not historical
- **Ask clarifying questions** - If something is unclear after exploration
- **Update stale plans** - If you find outdated info, note it for cleanup
