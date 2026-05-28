# /review Command

**Purpose**: Review code for quality, security, and maintainability.

**When to use**: After writing or modifying code, before shipping.

**How it works**:

1. Collect all changed files
2. Apply the code review checklist
3. Report findings by severity
4. Provide fix suggestions

## Usage

```
/review
```

## What Happens

The AI will:

1. **Collect changes** — Review all modified files
2. **Check security** — Hardcoded secrets, injection, XSS, auth bypass
3. **Check quality** — Function size, nesting, error handling, mutation
4. **Check patterns** — Consistency with existing code
5. **Report findings** — Organized by severity (CRITICAL → LOW)
6. **Suggest fixes** — With code examples

## Example Output

```
## Review Summary

| Severity | Count | Status |
|----------|-------|--------|
| CRITICAL | 0     | pass   |
| HIGH     | 1     | warn   |
| MEDIUM   | 2     | info   |
| LOW      | 1     | note   |

### HIGH: Missing error handling
File: src/api/habits.ts:23
Issue: API call has no try-catch. Network errors will crash the app.
Fix:
  try {
    const res = await fetch('/api/habits')
    if (!res.ok) throw new Error(`HTTP ${res.status}`)
    return await res.json()
  } catch (error) {
    showError('Failed to load habits. Please try again.')
  }

### MEDIUM: Magic number
File: src/utils/streak.ts:15
Issue: `7` used without explanation.
Fix: const MAX_STREAK_DISPLAY = 7

Verdict: WARNING — 1 HIGH issue should be resolved before shipping.
```

## Approval Criteria

- **APPROVE**: No CRITICAL or HIGH issues
- **WARNING**: Only HIGH issues (ship with caution)
- **BLOCK**: CRITICAL issues — must fix before shipping
