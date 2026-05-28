---
name: receiving-code-review
description: "How to respond to code review feedback constructively. Fix issues, learn from feedback, and maintain quality."
---

# Receiving Code Review

Respond to code review feedback constructively and professionally.

## Principles

1. **Don't take it personally** — Feedback is about code, not you
2. **Ask questions** — If feedback is unclear, ask for clarification
3. **Fix critical issues** — Security and bugs must be addressed
4. **Discuss disagreements** — Explain your reasoning if you disagree
5. **Learn from feedback** — Use it to improve future code

## Responding to Feedback

### For Critical Issues

1. Acknowledge the issue
2. Fix it immediately
3. Add tests to prevent regression
4. Request re-review

### For Suggestions

1. Consider the suggestion seriously
2. If you agree, implement it
3. If you disagree, explain why with reasoning
4. Be open to compromise

### For Questions

1. Answer clearly
2. Provide context if needed
3. Update code/comments if the question reveals confusion

## Response Format

```markdown
## Re: [Review Comment]

**Issue:** [Description]

**Action:** [What you did]

**Explanation:** [Why you did it this way]

---

[Repeat for each comment]
```

## Common Scenarios

### "This could be simpler"

- Consider if there's a simpler approach
- Explain complexity if it's necessary
- Refactor if you find a better way

### "Missing test for edge case"

- Add the test
- Consider if there are other edge cases missing
- Update documentation if needed

### "Security concern here"

- Take it seriously
- Research the vulnerability
- Fix immediately if valid
- Explain mitigation if it's not a real risk

### "Performance issue"

- Profile to confirm the issue
- Optimize if it's a real bottleneck
- Document if it's acceptable for now

## After Review

1. **Fix all critical issues** — Non-negotiable
2. **Address important suggestions** — Show you considered them
3. **Thank the reviewer** — They're helping you improve
4. **Learn from patterns** — If same feedback repeats, change your habits

## Red Flags

❌ Ignoring feedback without explanation
❌ Getting defensive instead of discussing
❌ Fixing symptoms instead of root causes
❌ Not adding tests for bug fixes
❌ Dismissing feedback without consideration
