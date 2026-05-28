---
name: brainstorming
description: "Design refinement through Socratic dialogue. MUST complete before any implementation. Turns rough ideas into validated designs."
---

# Brainstorming: Ideas Into Designs

Turn ideas into fully formed designs through collaborative dialogue.

<HARD-GATE>
Do NOT write any code, scaffold any project, or take any implementation action until you have presented a design and the user has approved it. This applies to EVERY project regardless of perceived simplicity.
</HARD-GATE>

## Anti-Pattern: "This Is Too Simple"

Every project goes through this process. A todo list, a single-function utility — all of them. "Simple" projects are where unexamined assumptions cause the most wasted work. The design can be short, but you MUST present it and get approval.

## Checklist

Complete these steps in order:

1. **Explore project context** — check files, docs, existing patterns
2. **Ask clarifying questions** — one at a time, understand purpose/constraints/success criteria
3. **Propose 2-3 approaches** — with trade-offs and your recommendation
4. **Present design** — in sections, get user approval after each section
5. **Spec self-review** — check for placeholders, contradictions, ambiguity
6. **User reviews spec** — ask user to review before proceeding
7. **Transition to implementation** — invoke writing-plans skill

## The Process

### Understanding the Idea

- Check out the current project state first (files, docs, structure)
- Assess scope: if the request describes multiple independent subsystems, flag this immediately
- If too large, help decompose into sub-projects with separate spec → plan → implementation cycles
- Ask questions one at a time to refine the idea
- Prefer multiple choice questions when possible
- Focus on: purpose, constraints, success criteria

### Exploring Approaches

- Propose 2-3 different approaches with trade-offs
- Present options conversationally with your recommendation and reasoning
- Lead with your recommended option and explain why

### Presenting the Design

- Scale each section to its complexity
- Ask after each section whether it looks right
- Cover: architecture, components, data flow, error handling, testing
- Be ready to go back and clarify

### Design for Isolation

- Break the system into smaller units with one clear purpose
- Each unit should have well-defined interfaces
- Can someone understand what a unit does without reading its internals?
- Smaller, well-bounded units are easier to work with

## Spec Self-Review

After writing the spec, look at it with fresh eyes:

1. **Placeholder scan:** Any "TBD", "TODO", incomplete sections? Fix them.
2. **Internal consistency:** Do sections contradict each other?
3. **Scope check:** Is this focused enough for a single implementation plan?
4. **Ambiguity check:** Could any requirement be interpreted two ways?

Fix any issues inline.

## Key Principles

- **One question at a time** — Don't overwhelm
- **Multiple choice preferred** — Easier to answer
- **YAGNI ruthlessly** — Remove unnecessary features
- **Explore alternatives** — Always propose 2-3 approaches
- **Incremental validation** — Present design, get approval before moving on
