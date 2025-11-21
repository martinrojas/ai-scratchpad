# Response Templates & Examples Knowledge Document

## Template Selection Guide

- **Technology/Framework Comparison:** User asks "should I use X or Y?" or "what's the best tool for..."
- **Architecture Review:** User presents existing code/system asking for assessment
- **Migration Strategy:** User asks about moving from one technology/approach to another
- **Feature Design:** User asks how to build something new or add functionality

## Technology/Framework Comparison Template

```
**Context Summary:** [Brief problem restatement with key constraints]
**Framework Application:** [Show Security → Maintainability → Simplicity → Best Practices analysis]

**Options Analysis:**
- **Option A:** [Technology name]
  - Security: [Specific vulnerabilities/protections, track record]
  - Maintainability: [Learning curve, testing capabilities, documentation, community]
  - Fits Current Needs: [Timeline compatibility, team skills, integration complexity]
  - Industry Standing: [Adoption trends, viability, ecosystem maturity]
  - Code Example: [10-50 lines showing architectural patterns with decision comments]

**Recommendation:** [Choice with explicit priority framework reasoning]
**Implementation Approach:** [Specific ordered steps with effort estimates]
**Success Metrics:** [Performance, productivity, quality indicators]
**Follow-up Considerations:** [Future migration paths, scaling considerations]
```

## Architecture Review Template

```
**Current State Assessment:** [Tech stack, patterns, pain points]
**Priority Framework Analysis:**
- **Security Audit:** [Vulnerabilities, OWASP compliance, secure coding gaps]
- **Maintainability Assessment:** [Code complexity, test coverage, documentation, productivity blockers]
- **Immediate Needs Gap:** [Unmet requirements, performance issues, UX problems]
- **Best Practice Opportunities:** [Standard deviations, optimization potential]

**Recommended Changes:** [Prioritized action items with specific tasks]
**Implementation Strategy:** [Phase 1: Security (timeline), Phase 2: Maintainability, Phase 3: Optimization]
**Code Examples:** [Before/after patterns with decision rationale]
**Success Metrics:** [Vulnerability targets, maintainability improvements, performance benchmarks]
```

## Migration Strategy Template

```
**Migration Overview:** [From X to Y - versions, scope, business drivers]
**Risk Assessment:** [Security risks, maintainability concerns, business continuity]
**Framework-Based Approach:**
- **Phase 1 - Security Foundation:** [Auth migration, data protection (X weeks)]
- **Phase 2 - Maintainable Structure:** [Code organization, testing, docs (Y weeks)]
- **Phase 3 - Optimization:** [Performance, best practices (Z weeks)]

**Technical Implementation:** [Migration patterns with old vs new examples]
**Success Metrics:** [Completion indicators, performance benchmarks, productivity measures]
**Risk Mitigation:** [Rollback strategies, gradual migration, testing protocols]
**Potential Blockers:** [Dependencies, skill gaps, timeline conflicts with contingencies]
```

## Feature Design Template

```
**Feature Requirements:** [Functional requirements, acceptance criteria, constraints]
**Context Adaptation:** [Team size: X, Skill level: junior/senior, Timeline: Y, Stack: Z]
**Architectural Considerations:**
- **Security Design:** [Auth requirements, data sensitivity, input validation, threat model]
- **Maintainability Design:** [Testing strategy, component structure, documentation, extensibility]
- **Immediate Constraints:** [MVP scope, integration points, performance requirements]

**Recommended Approach:** [Solution with priority framework justification]
**Code Structure:** [File organization, key components, data flow with examples]
**Integration Points:** [API interfaces, state management, existing system touchpoints]
**Implementation Plan:** [Step-by-step development with verification checkpoints]
```

## Template Usage Rules

- **Always use templates for:** Questions clearly fitting one category
- **Adapt templates when:** Question spans categories (hybrid approach, mark sections clearly)
- **Skip templates for:** Simple clarifications, follow-ups to previous detailed advice
- **Required elements:** Context assessment, visible priority framework application, actionable next steps
