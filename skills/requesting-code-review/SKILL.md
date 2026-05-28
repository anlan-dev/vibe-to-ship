---
name: requesting-code-review
description: "Structured code review process. Reviews code for quality, security, and maintainability before shipping."
---

# Requesting Code Review

After completing implementation, request a structured code review.

## When to Use

- After completing a feature
- Before merging to main
- After bug fixes
- Before deployment

## Review Checklist

### Critical (Must Fix)

- [ ] **Security vulnerabilities** — Hardcoded secrets, SQL injection, XSS
- [ ] **Data loss risks** — Missing validation, unsafe deletes
- [ ] **Authentication issues** — Broken auth, permission bypasses
- [ ] **Critical bugs** — Logic errors, crashes, data corruption

### Important (Should Fix)

- [ ] **Code quality** — Readability, naming, organization
- [ ] **Error handling** — Missing try/catch, unclear error messages
- [ ] **Performance** — Obvious inefficiencies, N+1 queries
- [ ] **Testing** — Missing tests, low coverage, flaky tests

### Nice to Have (Consider)

- [ ] **Code style** — Formatting, consistency
- [ ] **Documentation** — Missing comments for complex logic
- [ ] **Optimizations** — Minor improvements

## Review Process

1. **Understand the change** — What was built? Why?
2. **Check the critical items** — Security, data safety, auth
3. **Check important items** — Quality, errors, performance
4. **Provide feedback** — Specific, actionable, with examples
5. **Rate the change** — Approve, Request Changes, or Comment

## Feedback Format

```markdown
## Code Review: [Feature Name]

### Summary
Brief description of what was reviewed.

### Critical Issues
- **[File:Line]** Description of issue
  - Suggestion: How to fix

### Important Issues
- **[File:Line]** Description of issue
  - Suggestion: How to fix

### Positive Notes
- What was done well

### Verdict
✅ Approved — Ready to merge
⚠️ Approved with suggestions — Non-blocking improvements possible
❌ Changes requested — Critical issues must be fixed
```

## What to Look For

### Security

- Hardcoded secrets or API keys
- SQL injection vulnerabilities
- XSS vulnerabilities
- Missing input validation
- Insecure dependencies

### Code Quality

- Clear, descriptive naming
- Functions that do one thing
- Proper error handling
- No code duplication
- Consistent style

### Performance

- Efficient algorithms
- No unnecessary re-renders
- Proper caching
- Database query optimization

### Testing

- Tests exist for new code
- Edge cases covered
- Tests are not flaky
- Coverage meets threshold
