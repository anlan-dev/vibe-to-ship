---
name: subagent-driven-development
description: "Execute implementation plans by dispatching fresh subagent per task with two-stage review: spec compliance first, then code quality."
---

# Subagent-Driven Development

Execute plan by dispatching fresh subagent per task, with two-stage review after each: spec compliance review first, then code quality review.

**Why subagents:** Delegate tasks to specialized agents with isolated context. By precisely crafting their instructions, you ensure they stay focused. They never inherit your session's context — you construct exactly what they need.

**Core principle:** Fresh subagent per task + two-stage review = high quality, fast iteration

## When to Use

- Have an implementation plan? → Yes
- Tasks mostly independent? → Yes
- Want to stay in current session? → Yes

If tasks are tightly coupled, use manual execution instead.

## The Process

1. Read plan, extract all tasks, create TodoWrite
2. For each task:
   - Dispatch implementer subagent with full task text + context
   - Implementer asks questions if needed (answer before proceeding)
   - Implementer implements, tests, commits, self-reviews
   - Dispatch spec reviewer (does code match spec?)
   - If spec issues found → implementer fixes → re-review
   - Dispatch code quality reviewer
   - If quality issues found → implementer fixes → re-review
   - Mark task complete
3. After all tasks: dispatch final code reviewer
4. Finish development branch

## Model Selection

Use the least powerful model that can handle each role:

| Task Type | Model | Examples |
|-----------|-------|----------|
| Mechanical implementation | Fast/cheap | Isolated functions, clear specs, 1-2 files |
| Integration tasks | Standard | Multi-file coordination, pattern matching |
| Architecture & review | Most capable | Design decisions, broad codebase understanding |

## Handling Implementer Status

Implementers report one of four statuses:

- **DONE:** Proceed to spec compliance review
- **DONE_WITH_CONCERNS:** Read concerns first, address if about correctness
- **NEEDS_CONTEXT:** Provide missing context and re-dispatch
- **BLOCKED:** Assess the blocker — provide context, use better model, or escalate

**Never** ignore an escalation or force retry without changes.

## Two-Stage Review

### Stage 1: Spec Compliance

- Does the code match the specification?
- Nothing missing? Nothing extra added?
- If issues found → implementer fixes → re-review

### Stage 2: Code Quality

- Clean code, proper naming, error handling
- Test coverage adequate
- No security issues
- If issues found → implementer fixes → re-review

## Red Flags

**Never:**
- Skip reviews (spec compliance OR code quality)
- Proceed with unfixed issues
- Dispatch multiple implementers in parallel (conflicts)
- Make subagent read plan file (provide full text instead)
- Accept "close enough" on spec compliance
- Start code quality review before spec compliance passes

## Example Workflow

```
[Read plan, extract 5 tasks]
[Create TodoWrite]

Task 1: Hook installation script
[Dispatch implementer with full context]
Implementer: "Should hook be user or system level?"
You: "User level (~/.config/hooks/)"
Implementer: "Done. Tests passing. Committed."
[Dispatch spec reviewer] → ✅ Spec compliant
[Dispatch quality reviewer] → ✅ Approved
[Mark Task 1 complete]

Task 2: Recovery modes
[Dispatch implementer]
Implementer: "Done. 8 tests passing."
[Dispatch spec reviewer] → ❌ Missing progress reporting
[Implementer fixes] → [Re-review] → ✅
[Dispatch quality reviewer] → ✅ Approved
[Mark Task 2 complete]

... repeat for all tasks ...
[Final code reviewer] → Ready to merge
```
