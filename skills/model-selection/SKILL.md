---
name: model-selection
description: "Choose the right model for each task. Use the least powerful model that can handle the job to save cost and increase speed."
---

# Model Selection Strategy

Use the least powerful model that can handle each role. This conserves cost and increases speed without sacrificing quality.

## The Principle

Not every task needs the most capable model. A mechanical implementation task with clear specs doesn't require the same reasoning power as an architecture decision.

## Model Tiers

### Tier 1: Fast & Cheap

**Use for:** Isolated functions, clear specs, 1-2 files, mechanical tasks

- Simple CRUD operations
- Following well-defined patterns
- Adding tests to existing code
- Formatting and style fixes
- Documentation updates

### Tier 2: Standard

**Use for:** Multi-file coordination, integration, pattern matching

- Feature implementation
- Refactoring across files
- Debugging with context
- Code review
- Test suite creation

### Tier 3: Most Capable

**Use for:** Architecture, design decisions, broad codebase understanding

- System design
- Complex debugging
- Performance optimization
- Security review
- Cross-cutting concerns

## Decision Matrix

| Task Characteristics | Model Tier | Examples |
|---------------------|------------|----------|
| 1-2 files, clear spec | Fast | Add validation, write tests |
| Multiple files, integration | Standard | Feature implementation |
| Architecture decisions | Capable | System design, refactoring |
| Security review | Capable | Auth, API keys, payments |
| Simple formatting | Fast | Linting fixes, style updates |
| Complex debugging | Standard/Capable | Race conditions, memory leaks |

## When to Upgrade

Upgrade to a more capable model when:

- Task requires understanding multiple systems
- Security is involved
- Performance optimization is needed
- Design decisions have long-term impact
- Previous attempts with lower tier failed

## When to Downgrade

Use a cheaper model when:

- Task is mechanical with clear instructions
- Only 1-2 files need changes
- Pattern is well-established
- Tests already exist to verify
- Task is repetitive

## Cost Awareness

- Fast models: ~10x cheaper than capable models
- Standard models: ~3x cheaper than capable models
- Use capable models sparingly for high-value decisions

## Example Workflow

```
Task: "Add email validation to registration form"

Analysis:
- Single file change
- Clear pattern (validation function)
- Well-defined inputs/outputs
- Tests will verify

Decision: Tier 1 (Fast & Cheap)

---

Task: "Implement OAuth2 authentication flow"

Analysis:
- Multiple files (routes, middleware, models)
- Security-critical
- Complex state management
- Needs careful error handling

Decision: Tier 3 (Most Capable)

---

Task: "Refactor user service to use new database"

Analysis:
- Multiple files affected
- Need to understand existing patterns
- Data migration concerns
- Testing required

Decision: Tier 2 (Standard) for implementation
Decision: Tier 3 (Capable) for migration plan
```

## Anti-Patterns

❌ **Always using the most capable model** — Wasteful for simple tasks
❌ **Using cheap models for security** — Risky for critical code
❌ **Not upgrading when stuck** — If Tier 1 fails, try Tier 2
❌ **Ignoring cost** — Track usage and optimize over time
