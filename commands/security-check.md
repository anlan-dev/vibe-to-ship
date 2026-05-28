# /security-check Command

**Purpose**: Run a focused security audit on the codebase.

**When to use**: Before shipping, after adding auth/API/payment features, or when handling user data.

**How it works**:

1. Scan for hardcoded secrets
2. Check OWASP Top 10 vulnerabilities
3. Review auth and input validation
4. Report findings with severity

## Usage

```
/security-check
```

## What Happens

The AI will:

1. **Scan for secrets** — API keys, passwords, tokens in source code
2. **Check injection** — SQL injection, XSS, command injection
3. **Review auth** — Authentication and authorization logic
4. **Check input validation** — User input handling
5. **Review dependencies** — Known vulnerabilities
6. **Report findings** — With severity and fix suggestions

## Example Output

```
## Security Audit Results

### CRITICAL: Hardcoded API Key
File: src/config.ts:5
Issue: Stripe API key "sk_live_..." is hardcoded in source.
Fix: Move to environment variable.
  const STRIPE_KEY = process.env.STRIPE_SECRET_KEY
  if (!STRIPE_KEY) throw new Error('STRIPE_SECRET_KEY not configured')

### HIGH: No Rate Limiting
File: src/api/auth/login.ts
Issue: Login endpoint has no rate limiting. Vulnerable to brute force.
Fix: Add rate limiting middleware.

### MEDIUM: Verbose Error Messages
File: src/api/habits.ts:45
Issue: Database error details sent to client.
Fix: Log technical details, show generic message to user.

## Summary
| Severity | Count |
|----------|-------|
| CRITICAL | 1     |
| HIGH     | 1     |
| MEDIUM   | 1     |

Verdict: BLOCK — 1 CRITICAL issue must be fixed before shipping.
```

## Emergency Protocol

If CRITICAL issues are found:
1. Stop all shipping activities
2. Fix the critical issue immediately
3. Rotate any exposed credentials
4. Re-run `/security-check` to verify fix
5. Review entire codebase for similar issues
