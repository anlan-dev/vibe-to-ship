# /test Command

**Purpose**: Run tests and verify coverage.

**When to use**: After implementing features, before shipping, during development.

**How it works**:

1. Run all tests
2. Check coverage report
3. Identify untested code paths
4. Suggest additional tests if coverage < 80%

## Usage

```
/test
```

## What Happens

The AI will:

1. **Run tests** — Execute the test suite
2. **Check results** — Report pass/fail counts
3. **Analyze coverage** — Show coverage percentage and gaps
4. **Suggest fixes** — For failing tests
5. **Suggest additions** — For uncovered code paths

## Example

```
User: /test

AI:

## Test Results

### Unit Tests
✅ 34 passed, 0 failed

### Integration Tests
✅ 12 passed, 0 failed

### E2E Tests
✅ 3 passed, 0 failed

### Coverage
| File | Coverage | Status |
|------|----------|--------|
| src/utils/streak.ts | 95% | ✅ |
| src/utils/stats.ts | 88% | ✅ |
| src/api/habits.ts | 72% | ⚠️ |
| src/components/HabitCard.tsx | 65% | ⚠️ |

**Overall: 82%** ✅ (meets 80% minimum)

### Gaps
- `src/api/habits.ts`: Missing test for error handling (line 45-52)
- `src/components/HabitCard.tsx`: Missing test for empty state

### Suggested Tests
```typescript
test('shows error message when API fails', async () => {
  mockFetch.mockRejectedValueOnce(new Error('Network error'))
  render(<HabitList />)
  await waitFor(() => {
    expect(screen.getByText('Failed to load habits')).toBeInTheDocument()
  })
})
```
```

## TDD Mode

When building new features, use the TDD workflow:

1. **RED** — Write a failing test
2. **GREEN** — Write minimum code to pass
3. **REFACTOR** — Clean up while keeping tests green

```
/test --tdd "habit streak calculation"
```

The AI will:
1. Write the failing test first
2. Wait for you to see it fail
3. Implement the code to make it pass
4. Refactor and verify
