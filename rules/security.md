# Security Rules

Every product built with AI Co-Founder must follow these security basics. No exceptions.

## Pre-Ship Checklist

Before declaring any product "done":

- [ ] No hardcoded secrets (API keys, passwords, tokens) in source code
- [ ] All user inputs are validated before processing
- [ ] SQL queries use parameterized statements (no string concatenation)
- [ ] HTML output is escaped/sanitized (no raw user input in DOM)
- [ ] Authentication endpoints have rate limiting
- [ ] Error messages don't leak internal details (stack traces, DB errors)
- [ ] HTTPS is enforced for any deployed product
- [ ] Sensitive data (passwords, tokens) is never logged

## Secret Management

```
BAD:  const apiKey = "sk-proj-xxxxx"
GOOD: const apiKey = process.env.API_KEY
      if (!apiKey) throw new Error('API_KEY not configured')
```

- Use environment variables for all secrets
- Provide a `.env.example` file with placeholder values
- Never commit `.env` files to version control
- Add `.env` to `.gitignore` immediately

## Input Validation

- Validate all user input on the server side (never trust client)
- Use schema validation libraries when available (Zod, Joi, Yup)
- Reject unexpected fields (don't pass through raw request bodies)
- Validate file types and sizes for any upload feature

## Common Vulnerabilities to Avoid

| Vulnerability | What to check |
|---------------|---------------|
| SQL Injection | Queries built with string concatenation |
| XSS | User input rendered without escaping |
| CSRF | State-changing requests without tokens |
| Broken Auth | Missing auth checks on protected routes |
| Secrets Exposure | API keys in client-side code or git history |

## Emergency Protocol

If a security issue is found in a shipped product:

1. **STOP** — Don't ship or deploy
2. Assess the severity (critical / high / medium / low)
3. Fix critical issues before anything else
4. Rotate any exposed credentials immediately
5. Review the entire codebase for similar issues
