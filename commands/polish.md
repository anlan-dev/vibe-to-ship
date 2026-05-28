# /polish Command

**Purpose**: Apply visual polish, handle edge cases, and make the product feel professional.

**When to use**: After core features are working (Stage 4 of the workflow).

**How it works**:

1. Review visual consistency
2. Check edge cases (empty, loading, error states)
3. Verify responsive design
4. Optimize performance
5. Add micro-copy and transitions

## Usage

```
/polish
```

## What Happens

The AI will act as the **Polish Agent** and:

1. **Visual consistency** — Check spacing, typography, color, component styles
2. **Edge cases** — Empty states, loading states, error states, form validation
3. **Responsive design** — Test at 320px, 375px, 768px, 1024px, 1440px
4. **Performance** — First load time, image optimization, bundle size
5. **Accessibility** — Contrast, keyboard nav, screen reader, touch targets
6. **Micro-copy** — Button labels, error messages, confirmations
7. **Transitions** — Smooth animations for key interactions

## Polish Checklist

The AI will verify:

- [ ] Consistent spacing (no random pixel values)
- [ ] Consistent typography (2-3 body sizes, 2 heading sizes)
- [ ] Consistent color palette
- [ ] All interactive elements have hover/active states
- [ ] Empty states have helpful messages + call-to-action
- [ ] Error messages are human-readable
- [ ] Loading states for async operations
- [ ] Mobile layout works at all common widths
- [ ] Touch targets ≥44px on mobile
- [ ] Text contrast ≥4.5:1
- [ ] No console.log or debug code
- [ ] Smooth transitions (150-300ms)
- [ ] Destructive actions require confirmation
- [ ] Forms have proper validation and error states

## Example

```
User: /polish

AI (polish agent):

## Polish Report

### Visual Consistency
✅ Spacing is consistent throughout
⚠️ Card padding varies: 12px in some places, 16px in others
  Fix: Standardize to 16px padding for all cards

### Edge Cases
✅ Empty state exists for habit list
⚠️ No loading state when fetching habits
  Fix: Add skeleton loader to HabitList component
❌ Error state shows raw API error to user
  Fix: Show "Couldn't load habits. Check your connection."

### Responsive
✅ Works at 375px and 768px
⚠️ Habit card overflows at 320px
  Fix: Add min-width: 0 to card container

### Performance
⚠️ Hero image is 2.4MB PNG
  Fix: Convert to WebP, add lazy loading

### Accessibility
❌ Form inputs have no labels
  Fix: Add <label> elements or aria-label attributes

## Summary
| Category | Status |
|----------|--------|
| Visual   | ⚠️ Minor fixes |
| Edge Cases | ⚠️ Needs work |
| Responsive | ⚠️ One fix needed |
| Performance | ⚠️ Image optimization |
| Accessibility | ❌ Must fix |

Action: Fix the 3 marked issues, then re-run /polish.
```
