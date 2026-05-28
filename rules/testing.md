# Testing Rules

Testing is not optional. Every product built with AI Co-Founder must have tests that prove it works.

## Minimum Coverage: 80%

Test these three levels:

1. **Unit Tests** — Individual functions, utilities, components
2. **Integration Tests** — API endpoints, data flows, component interactions
3. **E2E Tests** — Critical user journeys (if applicable)

## TDD Workflow (When Applicable)

For new features, follow Test-Driven Development:

1. **RED** — Write a failing test that describes what you want
2. **GREEN** — Write the minimum code to make it pass
3. **REFACTOR** — Clean up while keeping tests green
4. **VERIFY** — Check coverage is 80%+

## What to Test

### Always Test
- Business logic and calculations
- Data transformations
- API endpoints (request/response)
- Form validation
- Error handling paths
- Edge cases (empty input, null, undefined, max values)

### Test Edge Cases
- Empty states (no data yet)
- Loading states (waiting for API)
- Error states (API failure, network down)
- Boundary values (0, -1, max int, empty string)
- Concurrent operations (if applicable)

## Test Structure

Use the Arrange-Act-Assert pattern:

```
test('calculates habit streak correctly', () => {
  // Arrange
  const checkins = ['2024-01-01', '2024-01-02', '2024-01-03']

  // Act
  const streak = calculateStreak(checkins)

  // Assert
  expect(streak).toBe(3)
})
```

## Test Naming

Use descriptive names that explain the scenario:

```
BAD:   test('streak', () => { ... })
GOOD:  test('returns 0 when no checkins exist', () => { ... })
GOOD:  test('resets streak when a day is missed', () => { ... })
GOOD:  test('handles timezone differences correctly', () => { ... })
```

## What NOT to Test

- Third-party library internals
- Pure CSS/styling
- Trivial getters/setters with no logic
- Implementation details (test behavior, not internals)

## Pre-Ship Test Checklist

Before declaring v1 complete:

- [ ] All core features have unit tests
- [ ] API endpoints have integration tests
- [ ] Critical user flows have E2E tests (if applicable)
- [ ] Edge cases are covered
- [ ] Error paths are tested
- [ ] Tests pass in CI (if configured)
- [ ] Coverage report shows 80%+
