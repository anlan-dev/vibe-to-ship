# Case Studies

Products built using the Vibe to Ship workflow.

## Completed

### 1. Habit Streak Tracker (习惯·原子钟)

**Problem**: 80% of people abandon habit apps within 7 days because they're too complex.

**Solution**: One habit, one streak, one reminder. That's it.

**Tech**: Single-file HTML, localStorage, no dependencies

**Built in**: 1 session (~2 hours)

**Key decisions**:
- Only support ONE habit (forces focus)
- Streak counter instead of points (simpler mental model)
- No social features (reduces anxiety)

[Live Demo](./habit-streak/index.html)

---

## Planned (contributions welcome!)

### 2. Pomodoro Focus Timer

**Idea**: A neumorphic Pomodoro timer with session history and focus analytics.

**Target users**: Students, remote workers, anyone who needs focus blocks.

**Core features**:
- 25/5 minute timer with neumorphic UI
- Session history (localStorage)
- Focus score based on completion rate
- Daily/weekly stats

### 3. Markdown Quick Note

**Idea**: A single-file markdown editor for quick notes, saved to localStorage.

**Target users**: Developers, writers, anyone who thinks in markdown.

**Core features**:
- Split-pane editor (markdown + preview)
- Auto-save to localStorage
- Export to .md file
- Dark/light theme

### 4. Expense Splitter

**Idea**: Split bills with friends, no signup required.

**Target users**: Roommates, travel groups, friend groups.

**Core features**:
- Add people and expenses
- Auto-calculate who owes whom
- Share via URL (data in URL params)
- Mobile-first design

### 5. Reading List Tracker

**Idea**: Track books you want to read, are reading, and have finished.

**Target users**: Avid readers, book club members.

**Core features**:
- Three lists: Want to Read, Reading, Finished
- Add books with cover image URL
- Progress bar for current book
- Stats: pages per day, books per month

### 6. QR Code Generator

**Idea**: Generate QR codes for URLs, text, or WiFi passwords.

**Target users**: Anyone who needs quick QR codes.

**Core features**:
- Input: URL, text, or WiFi credentials
- Customizable colors and size
- Download as PNG
- No server needed (client-side generation)

### 7. Daily Reflection Journal

**Idea**: 3-question daily journal: What went well? What could improve? What's tomorrow's priority?

**Target users**: Anyone building a reflection habit.

**Core features**:
- 3 prompts per day
- Calendar view of past entries
- Export to PDF
- Local storage, private by default

---

## How to contribute a case

1. Fork this repo
2. Use the Vibe to Ship prompt to build your product
3. Add your product to `examples/your-product-name/`
4. Update this file with your case study
5. Submit a PR
