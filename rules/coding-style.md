# Coding Style Rules

These rules apply to every product built with Vibe to Ship. They ensure the code is readable, maintainable, and professional.

## Immutability First

Always create new objects. Never mutate existing ones:

```
BAD:
  function updateUser(user, name) {
    user.name = name  // mutates the original!
    return user
  }

GOOD:
  function updateUser(user, name) {
    return { ...user, name }
  }
```

Use spread operators, map, filter, reduce — not push, splice, or direct assignment.

## File Organization

- Prefer many small files over few large files
- Each file should have a single responsibility
- Recommended: 200-400 lines per file, max 800
- Extract utilities from large components
- Organize by feature/domain, not by type

```
BAD:                           GOOD:
src/                           src/
  components/                    auth/
    Button.tsx                     LoginForm.tsx
    Card.tsx                       auth.ts
    Modal.tsx                      useAuth.ts
  hooks/                       dashboard/
    useAuth.ts                     Dashboard.tsx
    useTheme.ts                    Stats.tsx
  utils/                         useStats.ts
    auth.ts                      habit/
    format.ts                      HabitList.tsx
                                 habit.ts
                                 useHabit.ts
```

## Error Handling

Always handle errors explicitly:

```
BAD:
  const data = await fetch('/api/data')
  const json = await data.json()

GOOD:
  try {
    const response = await fetch('/api/data')
    if (!response.ok) throw new Error(`HTTP ${response.status}`)
    const data = await response.json()
    return data
  } catch (error) {
    console.error('Failed to fetch data:', error)
    showUserFriendlyMessage('Something went wrong. Please try again.')
  }
```

- Never use empty catch blocks
- Always show user-friendly error messages, not stack traces
- Log technical details for debugging, show simple messages to users

## Naming Conventions

- **Variables and functions**: camelCase (`getUserData`, `isLoading`)
- **Components**: PascalCase (`UserProfile`, `HabitCard`)
- **Constants**: UPPER_SNAKE_CASE (`MAX_RETRY_COUNT`, `API_BASE_URL`)
- **Files**: kebab-case (`user-profile.tsx`, `habit-card.ts`)
- **CSS classes**: kebab-case or BEM (`habit-card__title--active`)

## Code Quality Checklist

Before marking any work as complete:

- [ ] Code is readable and well-named
- [ ] Functions are small (<50 lines)
- [ ] Files are focused (<800 lines)
- [ ] No deep nesting (>4 levels)
- [ ] Proper error handling everywhere
- [ ] No console.log statements in production code
- [ ] No hardcoded values (use constants or config)
- [ ] No mutation of input parameters
