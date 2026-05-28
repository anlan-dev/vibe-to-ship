# /ship Command

**Purpose**: Final checks and deployment preparation.

**When to use**: After polish is complete and you're ready to deploy (Stage 5).

**How it works**:

1. Run all quality gates
2. Generate deployment configuration
3. Create README documentation
4. Provide maintenance checklist

## Usage

```
/ship
```

## What Happens

The AI will:

1. **Run quality gates** — Verify all stage gates pass
2. **Security check** — Quick security audit
3. **Test verification** — Confirm tests pass and coverage is 80%+
4. **Generate deploy config** — Platform-specific configuration
5. **Create README** — How to run, deploy, and modify
6. **Provide maintenance guide** — Backup, updates, monitoring

## Pre-Ship Checklist

The AI will verify all of these:

### Code Quality
- [ ] All tests pass
- [ ] Test coverage ≥80%
- [ ] No console.log in production code
- [ ] No hardcoded secrets
- [ ] Error handling is complete

### Security
- [ ] No hardcoded API keys or passwords
- [ ] All user inputs validated
- [ ] SQL queries parameterized
- [ ] XSS protection in place
- [ ] HTTPS enforced

### Performance
- [ ] First load ≤3s
- [ ] Images optimized
- [ ] No unused dependencies
- [ ] Bundle size reasonable

### Documentation
- [ ] README with setup instructions
- [ ] Environment variables documented
- [ ] Deployment instructions
- [ ] Common modifications documented

### Polish
- [ ] All edge cases handled
- [ ] Mobile responsive
- [ ] Accessible
- [ ] Professional appearance

## Deployment Options

The AI will suggest the best deployment option for your project:

| Platform | Best for | Cost |
|----------|----------|------|
| Vercel | Next.js, React, static sites | Free tier available |
| Netlify | Static sites, JAMstack | Free tier available |
| Fly.io | Full-stack apps with databases | Free tier available |
| DigitalOcean | Custom setups, more control | $4-12/month |
| GitHub Pages | Static sites, documentation | Free |

## Example

```
User: /ship

AI:

## Ship Checklist Results

### ✅ Passed
- All tests pass (47/47)
- Coverage: 87%
- No hardcoded secrets
- Security audit clean
- Mobile responsive
- README complete

### ⚠️ Warnings
- Bundle size: 245KB (consider code splitting for v1.1)
- No error tracking service configured (add Sentry for v1.1)

### Recommended Deployment: Vercel
Your Next.js app is best suited for Vercel:
1. Push to GitHub
2. Connect repo at vercel.com
3. Add environment variables in Vercel dashboard
4. Deploy automatically on push

### Next Steps
1. Push code to GitHub
2. Deploy to Vercel staging URL
3. Test staging URL
4. Deploy to production
5. Share with users!

### v1.1 Backlog (suggested)
1. Add error tracking (Sentry)
2. Add analytics (Plausible/PostHog)
3. Code split for smaller bundle
4. Add PWA support
5. Add dark mode
```
