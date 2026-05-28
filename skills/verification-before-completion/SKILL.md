---
name: verification-before-completion
description: "Ensure work is actually done before declaring success. Verify with evidence, not assumptions."
---

# Verification Before Completion

Never declare work complete without evidence. Verify it actually works.

## The Problem

It's tempting to say "done" when the code looks right. But looking right and working right are different things. Bugs hide in the gap between intention and reality.

## The Rule

**Show, don't tell.** Provide evidence that your work is complete:

1. **Run the tests** — Show the output
2. **Run the app** — Show it working
3. **Check edge cases** — Show they're handled
4. **Check error states** — Show graceful failures

## Verification Checklist

Before saying "done":

### Code Verification

- [ ] Code compiles/builds without errors
- [ ] All tests pass (show output)
- [ ] No linting errors (show output)
- [ ] No type errors (if applicable)

### Functionality Verification

- [ ] Core feature works (demonstrate it)
- [ ] Edge cases handled (show examples)
- [ ] Error states handled (show examples)
- [ ] Performance acceptable (if relevant)

### Quality Verification

- [ ] Code follows project conventions
- [ ] No hardcoded values that should be configurable
- [ ] No console.logs or debug code left behind
- [ ] Comments explain "why", not "what"

## How to Verify

### For UI Changes

1. Open the app in browser
2. Navigate to the changed area
3. Interact with the feature
4. Test edge cases (empty states, long text, errors)
5. Test responsive (mobile, tablet, desktop)
6. Take screenshot or describe what you see

### For API Changes

1. Start the server
2. Make requests to the endpoints
3. Test with valid data
4. Test with invalid data
5. Test with missing data
6. Show the responses

### For Logic Changes

1. Run the unit tests
2. Show the test output
3. If no tests exist, write them first
4. Test edge cases manually if needed

### For Bug Fixes

1. Reproduce the bug (show the broken behavior)
2. Apply the fix
3. Verify the bug is gone (show the fixed behavior)
4. Verify no regressions (run existing tests)

## Evidence Format

When reporting completion, include:

```
## Completed: [Task Name]

### Evidence

**Tests:**
```
$ npm test
✓ should handle valid input (23ms)
✓ should reject invalid input (15ms)
✓ should handle edge cases (18ms)

3 passing (56ms)
```

**Manual Verification:**
- Opened app at http://localhost:3000
- Created new item with valid data ✅
- Tried empty form — got validation error ✅
- Tried long text — truncated correctly ✅

**Screenshot:** [if applicable]
```

## Red Flags

❌ "It should work" — Did you test it?
❌ "The code looks correct" — Did you run it?
❌ "Tests are passing" — Show the output
❌ "I fixed the bug" — Can you reproduce the fix?
❌ "It's ready to ship" — Have you verified edge cases?

## The Mindset

Think like a skeptical QA engineer, not an optimistic developer. Your job is to find problems before users do. If you can't prove it works, it doesn't work yet.
