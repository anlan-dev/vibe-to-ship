---
name: test-driven-development
description: "RED-GREEN-REFACTOR cycle. Write tests first, always. Every product must have tests that prove it works."
---

# Test-Driven Development

Testing is not optional. Every product must have tests that prove it works.

## The RED-GREEN-REFACTOR Cycle

```
RED → GREEN → REFACTOR → COMMIT
```

1. **RED:** Write a failing test that describes what you want
2. **GREEN:** Write the minimum code to make it pass
3. **REFACTOR:** Clean up without changing behavior
4. **COMMIT:** Save your progress

**Critical:** If you write code before tests, DELETE IT and start over with tests.

## Minimum Coverage: 80%

Every product must have at least 80% test coverage. This is not negotiable.

### What to Test

- Core functionality (CRUD operations, business logic)
- Edge cases (empty inputs, boundary values, special characters)
- Error handling (invalid inputs, network failures, permission errors)
- User interactions (clicks, form submissions, navigation)

### What NOT to Test

- Third-party library internals
- Simple getters/setters with no logic
- Implementation details that might change
- Trivial configuration

## Test Structure

Use the Arrange-Act-Assert pattern:

```javascript
// Arrange: Set up test data and conditions
const user = { name: 'Test', email: 'test@example.com' }

// Act: Perform the action being tested
const result = validateUser(user)

// Assert: Verify the expected outcome
expect(result.isValid).toBe(true)
```

## Test Naming

Use descriptive names that explain the scenario:

```
❌ test1, test validation, test user
✅ should return error when email is missing
✅ should accept valid user with all required fields
✅ should reject user under 18 years old
```

## Edge Cases to Always Test

1. **Empty/null inputs** — What happens with nothing?
2. **Boundary values** — Min/max numbers, empty strings, very long strings
3. **Special characters** — Unicode, emojis, HTML tags, SQL injection
4. **Concurrent access** — Race conditions, duplicate submissions
5. **Network issues** — Timeouts, slow responses, connection drops
6. **Permission errors** — Unauthorized access, expired tokens

## Pre-Ship Test Checklist

Before shipping any feature:

- [ ] Core functionality has tests
- [ ] Edge cases are covered
- [ ] Error handling is tested
- [ ] Tests pass consistently (no flaky tests)
- [ ] Coverage meets minimum 80%
- [ ] Tests run fast (under 30 seconds for unit tests)
- [ ] Test names are descriptive
- [ ] No skipped or pending tests

## TDD Workflow for New Features

1. Write a test for the smallest piece of functionality
2. Watch it fail (RED)
3. Write just enough code to pass (GREEN)
4. Refactor if needed (REFACTOR)
5. Commit
6. Repeat for next piece

## Example: Building a Validator

```javascript
// RED: Write failing test
test('should reject empty email', () => {
  const result = validateEmail('')
  expect(result.isValid).toBe(false)
  expect(result.error).toBe('Email is required')
})

// GREEN: Minimal implementation
function validateEmail(email) {
  if (!email) return { isValid: false, error: 'Email is required' }
  return { isValid: true }
}

// REFACTOR: Add more tests, improve implementation
test('should reject invalid email format', () => {
  const result = validateEmail('not-an-email')
  expect(result.isValid).toBe(false)
  expect(result.error).toBe('Invalid email format')
})
```

## Anti-Patterns

❌ **Test-after development** — Writing tests after code is written
❌ **Testing implementation details** — Tests break when refactoring
❌ **Missing edge cases** — Only testing the happy path
❌ **Slow tests** — Tests that take too long discourage running them
❌ **Flaky tests** — Tests that sometimes pass, sometimes fail
❌ **No assertions** — Tests that run but don't verify anything
