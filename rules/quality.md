# Quality Gates

These quality gates must pass before any stage of the AI Co-Founder workflow is considered complete.

## Stage Gates

### Explore → Plan Gate
Before moving to planning:
- [ ] Problem statement is clear and specific
- [ ] Target user is defined
- [ ] "Done" criteria is agreed upon
- [ ] Scope is realistic for v1
- [ ] One-sentence product promise is signed off

### Plan → Build Gate
Before writing any code:
- [ ] Feature list is ≤5 items
- [ ] Tech stack is chosen and justified
- [ ] Complexity is rated (simple / medium / complex)
- [ ] Resource checklist is complete (APIs, accounts, etc.)
- [ ] User has approved the plan

### Build → Polish Gate
Before polishing:
- [ ] All planned features are implemented
- [ ] Core user flow works end-to-end
- [ ] Tests pass (80%+ coverage)
- [ ] No critical bugs in happy path
- [ ] User has tested and confirmed functionality

### Polish → Ship Gate
Before deploying:
- [ ] Visual design is consistent
- [ ] Edge cases are handled (empty states, errors, loading)
- [ ] Mobile layout works at all common widths
- [ ] Performance: first load ≤3s
- [ ] Accessibility: text contrast ≥4.5:1, touch targets ≥44px
- [ ] No console.log or debug code in production
- [ ] README is complete and accurate

## Product Quality Standards

### Visual Polish
- Consistent spacing (use a spacing scale: 4, 8, 12, 16, 24, 32, 48, 64)
- Consistent typography (limit to 2-3 font sizes for body, 2 for headings)
- Consistent color palette (primary, secondary, accent, neutral)
- Hover/active states on all interactive elements
- Smooth transitions (150-300ms for UI changes)

### Responsive Design
- Mobile-first approach
- Test at: 320px, 375px, 768px, 1024px, 1440px
- No horizontal scroll at any width
- Touch-friendly on mobile (≥44px targets)

### Performance
- First Contentful Paint < 1.5s
- Largest Contentful Paint < 2.5s
- Cumulative Layout Shift < 0.1
- No render-blocking resources
- Images optimized (WebP/AVIF, lazy loading)

### Accessibility
- Semantic HTML (use proper headings, landmarks, lists)
- Keyboard navigable (tab order, focus states)
- Screen reader friendly (alt text, ARIA labels)
- Color is not the only way to convey information
- Form inputs have associated labels

## User Experience Standards

### Empty States
- Show helpful messages, not blank screens
- Include a call-to-action ("Create your first habit")
- Use friendly, encouraging language

### Error Messages
- Human-readable, not technical
- Tell the user what happened and what to do next
- "Something went wrong. Please try again." not "Error 500"

### Loading States
- Show spinners or skeleton screens for async operations
- Disable buttons during submission
- Show progress for long operations

### Micro-copy
- Use clear, action-oriented button labels ("Save habit" not "Submit")
- Provide context for form fields ("This will be visible on your profile")
- Confirm destructive actions ("Are you sure? This can't be undone.")
