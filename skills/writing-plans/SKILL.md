---
name: writing-plans
description: "Create detailed implementation plans before coding. Break work into bite-sized tasks with exact file paths and verification steps."
---

# Writing Implementation Plans

Break approved designs into detailed, actionable implementation plans.

## When to Use

- After brainstorming/design is approved
- Before any code is written
- When facing a complex feature

## The Plan Format

Each task in the plan must include:

1. **Task description** — What to build (1-2 sentences)
2. **Files to create/modify** — Exact file paths
3. **Implementation details** — Key code structure, not full code
4. **Verification steps** — How to confirm it works
5. **Dependencies** — What must be done first

## Plan Structure

```markdown
## Implementation Plan: [Feature Name]

### Context
- What we're building and why
- Key decisions from the design phase

### Tasks

#### Task 1: [Task Name]
- **Description:** What this task accomplishes
- **Files:** `src/feature.js`, `tests/feature.test.js`
- **Implementation:**
  - Create class/module structure
  - Implement core logic
  - Handle edge cases
- **Verification:**
  - Run tests: `npm test`
  - Manual check: [specific action]
- **Dependencies:** None

#### Task 2: [Task Name]
- **Description:** ...
- **Files:** ...
- **Implementation:** ...
- **Verification:** ...
- **Dependencies:** Task 1
```

## Task Sizing

Each task should be:

- **Completable in 2-5 minutes** by a competent developer
- **Independently testable** — can verify in isolation
- **Self-contained** — clear inputs, outputs, and file changes
- **Not too large** — if a task takes longer, break it down

## Ordering Tasks

1. **Core data model first** — Foundation everything else builds on
2. **Core user flow** — Happy path only
3. **UI shell** — Basic structure and styling
4. **Feature by feature** — Each fully working before next
5. **Error handling** — Edge cases and validation
6. **Polish** — Responsive, accessibility, performance

## Plan Quality Checklist

Before presenting the plan:

- [ ] Every task has clear file paths
- [ ] Every task has verification steps
- [ ] Dependencies are explicit
- [ ] Tasks are right-sized (2-5 min each)
- [ ] Order makes sense (dependencies first)
- [ ] No task is too vague
- [ ] Edge cases are addressed
- [ ] Testing is included

## Example Plan

```markdown
## Implementation Plan: User Authentication

### Context
Building login/logout functionality for the app.
Design approved: JWT tokens, bcrypt passwords, session cookies.

### Tasks

#### Task 1: User Model
- **Description:** Create User model with email/password fields
- **Files:** `src/models/User.js`, `tests/models/User.test.js`
- **Implementation:**
  - Define schema with email (unique), password (hashed), timestamps
  - Add method to compare passwords
  - Add method to hash passwords before save
- **Verification:**
  - `npm test -- --grep "User Model"`
  - Create user in test, verify password comparison
- **Dependencies:** None

#### Task 2: Auth Service
- **Description:** Create authentication service
- **Files:** `src/services/auth.js`, `tests/services/auth.test.js`
- **Implementation:**
  - `login(email, password)` → returns JWT token
  - `register(email, password)` → creates user, returns token
  - `verify(token)` → returns user data
- **Verification:**
  - `npm test -- --grep "Auth Service"`
  - Register user, login, verify token
- **Dependencies:** Task 1

#### Task 3: Auth Routes
- **Description:** Create API endpoints
- **Files:** `src/routes/auth.js`, `tests/routes/auth.test.js`
- **Implementation:**
  - POST `/auth/register` — calls auth.register
  - POST `/auth/login` — calls auth.login
  - POST `/auth/logout` — clears session
  - GET `/auth/me` — returns current user
- **Verification:**
  - `npm test -- --grep "Auth Routes"`
  - Test each endpoint with curl or Postman
- **Dependencies:** Task 2
```

## Red Flags

- Plan has tasks without file paths
- Tasks are too large (>10 min each)
- No verification steps
- Dependencies aren't clear
- Order doesn't make sense
- Missing error handling tasks
- No testing tasks included
