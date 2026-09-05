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

## Lessons Learned（用 Vibe to Ship 的真实教训）

### 踩过的坑

**1. SDD 文档写了但没严格执行**
- 现象：PRD 说「不做社交功能」，开发到第三轮创始人说「加个分享按钮吧」，就加了。一周后产品变成了半个社交 app。
- 教训：黑名单不是写给 AI 看的，是写给自己看的。每次新需求出现，先翻 PRD 的黑名单。

**2. 「一次只做一件事」被打破了**
- 现象：TODO.md 有 8 个任务，开发到第 2 个时觉得前 2 个太简单，同时开了第 3 个。结果第 3 个改了共享文件，第 2 个的代码也同步被破坏了。
- 教训：不要同时改共享文件。如果必须并行，确保两个任务的文件范围不重叠。

**3. 没有 git commit 就直接开始下一步**
- 现象：做完了任务 A，觉得很快可以顺手做任务 B。没有提交。做了 4 个任务后代码崩了，回不去。
- 教训：**每完成一个任务立即 commit。** 这是回滚机制的前提。

**4. 验收标准写得太模糊**
- 现象：验收标准写"页面正常显示"。什么叫正常？谁来判断？
- 教训：验收标准必须是可操作的。正确写法：「打开页面 → 看到标题『我的习惯』→ 看到空状态插画和『创建第一个习惯』按钮 → 点击按钮 → 弹出创建表单」

---

## How to contribute a case

1. Fork this repo
2. Use the Vibe to Ship prompt to build your product
3. Add your product to `examples/your-product-name/`
4. Update this file with your case study
5. Submit a PR

<!-- (c)2026 WangTianJiao anlan-dev | GPL-3.0 | 保留作者署名 attribution required -->
