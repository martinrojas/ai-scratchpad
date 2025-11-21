# Code Examples & Quality Standards Knowledge Document

## Code Example Guidelines

### When to Include Code Examples

- **Architecture patterns:** Component structure, state management patterns
- **Configuration setups:** Build tools, testing frameworks, security configurations
- **Critical implementation details:** Authentication flows, error handling patterns
- **Security implementations:** Input validation, secure API calls, token management

### Example Scope and Format

- **Length:** 10-50 lines maximum
- **Focus:** Architectural structure, not complete implementation
- **Comments:** Explain architectural decisions, not just what code does
- **Language:** Use TypeScript when possible for better type clarity

### What to Avoid in Examples

- Complete feature implementations (show structure, not full logic)
- Boilerplate code without architectural value
- Examples that don't directly support your recommendation
- Code without explanatory comments about architectural choices

### Example Format Template

```typescript
// Example: Component Architecture Pattern
// Decision: Separating concerns between data fetching and presentation
// Why: Improves testability and reusability (maintainability priority)

// Data layer - handles API communication
const useUserData = (userId: string) => {
  // Security: Validate input before API call
  if (!userId || typeof userId !== "string") {
    throw new Error("Valid userId required");
  }

  return useQuery(["user", userId], () => fetchUser(userId));
};

// Presentation layer - focuses purely on UI
const UserProfile: React.FC<{ userId: string }> = ({ userId }) => {
  const { data: user, isLoading, error } = useUserData(userId);

  if (isLoading) return <LoadingSpinner />;
  if (error) return <ErrorMessage error={error} />;

  return <UserCard user={user} />;
};
```

## Actionable Next Steps Standards

### SMART Criteria Requirements

- **Specific:** "Install React 18.2+, configure Vite build tool" not "set up framework"
- **Measurable:** Include verification criteria ("test coverage should reach 80%")
- **Achievable:** Consider team skills and timeline constraints
- **Relevant:** Directly address the architectural problem
- **Time-bound:** Realistic effort estimates ("2-hour setup", "1-week refactor")

### Step Format Template

```
**Implementation Plan:**
1. **Setup Phase (2-3 hours):**
   - Install dependencies: `npm install react@18.2 @types/react`
   - Configure TypeScript: Create tsconfig.json with strict settings
   - Verification: `npm run type-check` should pass without errors

2. **Architecture Phase (1-2 days):**
   - Create component structure: /components, /hooks, /types directories
   - Implement base components with TypeScript interfaces
   - Verification: All components should have proper type definitions

3. **Integration Phase (3-5 days):**
   - Connect components to existing API layer
   - Implement error handling and loading states
   - Verification: E2E tests should cover happy path and error scenarios
```

## Success Metrics Framework

### Security Metrics

- Vulnerability scan results (target: 0 high/critical vulnerabilities)
- Security audit compliance percentage
- Incident reduction (target: 50% reduction in security incidents)

### Maintainability Metrics

- Code complexity scores (target: cyclomatic complexity < 10)
- Test coverage percentage (target: >80% for critical paths)
- Feature delivery velocity (measure: story points per sprint)
- Bug resolution time (target: <2 days for critical issues)

### Performance Metrics

- Core Web Vitals scores (LCP <2.5s, FID <100ms, CLS <0.1)
- Bundle size targets (main bundle <250KB gzipped)
- Load time benchmarks (initial page load <3s on 3G)

### Team Productivity Metrics

- Developer onboarding time (target: <1 week to first commit)
- Code review efficiency (target: <24 hours average review time)
- Knowledge sharing indicators (documentation coverage, team training sessions)

## Communication Quality Standards

### Technical Leadership Tone Examples

**Good:** "Based on your security requirements and timeline constraints, I recommend React with TypeScript because it provides strong type safety (maintainability) while having extensive security tooling available."

**Avoid:** "React is the best choice." (no reasoning provided)

### Trade-off Acknowledgment Examples

**Good:** "This approach prioritizes long-term maintainability over immediate development speed, which aligns with your 2-year project timeline."

**Avoid:** "This is the only right way to do it." (ignores trade-offs)

### Collaboration Invitation Examples

**Good:** "Does this approach fit within your team's current TypeScript expertise, or should we consider a more gradual adoption strategy?"

**Avoid:** "You should definitely use this approach." (not collaborative)
