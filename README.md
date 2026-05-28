<h1 align="center">AI Co-Founder</h1>

<p align="center">
  A structured prompt that turns any AI into your technical co-founder.<br/>
  Not just code generation — a 5-stage workflow from idea to shipped product.
</p>

<p align="center">
  <a href="./README-CN.md">中文版</a> ·
  <a href="./prompts/cofounder.md">Get the Prompt</a> ·
  <a href="./examples/habit-streak/index.html">Live Demo</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"/>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs Welcome"/>
  <img src="https://img.shields.io/badge/platform-Any%20AI-lightgrey.svg" alt="Any AI"/>
  <img src="https://img.shields.io/badge/stars-%E2%98%85-yellow.svg" alt="Stars"/>
</p>

---

## Table of Contents

- [What is this?](#what-is-this)
- [The 5-Stage Workflow](#the-5-stage-workflow)
- [Quick Start](#quick-start)
- [Example Conversation](#example-conversation)
- [Cases](#cases)
- [Who is this for?](#who-is-this-for)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

## What is this?

Most AI prompts give you a **personality**. This one gives you a **process**.

| Approach | What you get |
|----------|-------------|
| "Build me an app" | Code (maybe broken, maybe not what you need) |
| AI character prompts | A fun conversation, no real output |
| **AI Co-Founder** | A structured workflow with quality gates at every stage |

You don't just get an app. You learn **how to think like a product owner**.

## The 5-Stage Workflow

```
① Explore → ② Plan → ③ Build → ④ Polish → ⑤ Ship
```

| Stage | What happens | Who decides |
|-------|-------------|-------------|
| **Explore** | AI asks probing questions to understand the real problem | You answer, AI challenges assumptions |
| **Plan** | Define features, tech stack, complexity, resources | You approve the plan |
| **Build** | Vertical slices, each tested before moving on | You review each slice, choose at forks |
| **Polish** | Design consistency, edge cases, performance, accessibility | You approve the final look |
| **Ship** | Deploy, document, maintain | You own the product |

Each stage has **quality gates** — you can't move forward until the previous stage is solid.

## Quick Start

### Option 1: Copy the prompt (any AI platform)

1. Copy the prompt from [`prompts/cofounder.md`](./prompts/cofounder.md)
2. Paste into ChatGPT / Claude / Cursor / any AI
3. Tell it what you want to build
4. Follow the 5-stage workflow

### Option 2: Install as Trae Skill

```bash
# Copy the skill to your Trae skills directory
cp -r skills/tech-cofounder ~/.trae/skills/
```

Then in Trae, just say "I want to build a tool" and the AI will automatically enter co-founder mode.

## Example conversation

```
You: I want a tool to track my habits

AI (as co-founder): Good idea. Before I build anything, let me understand:
1. How do you currently track habits? What's broken about that?
2. Is this just for you, or do you want to share it?
3. What's the smallest version that would still be useful?
4. What's your timeline?

You: I use a spreadsheet. It's ugly and I forget to update it.
Just for me. I just need a streak counter and a daily reminder.
This weekend.

AI: Perfect. Here's my plan for v1:
- Single-file HTML (no server, no install)
- One habit, one streak, one reminder
- Neumorphic design, mobile-first
- Complexity: simple (2-3 hours)

Shall I proceed?
```

## Cases

### Case 1: Habit Streak Tracker

A minimal habit tracker built with the AI Co-Founder workflow — from idea to polished demo in a single session.

| | |
|---|---|
| **What it does** | Track one habit, visualize streaks with a GitHub-style heatmap, AI-powered check-in suggestions |
| **Tech** | Single-file HTML · localStorage · Zero dependencies · Neumorphic design |
| **Built in** | ~2 hours, 1 session |

**Features:** Confetti celebrations at milestones · Dark mode · Export JSON/CSV · Mobile-first responsive · Data stays on device

[**Live Demo**](./examples/habit-streak/index.html) · [Source](./examples/habit-streak/index.html)

### More cases coming

Want to contribute your case? See [CONTRIBUTING.md](./CONTRIBUTING.md).

## Project Structure

```
ai-cofounder/
├── prompts/
│   └── cofounder.md          # The prompt — copy & paste into any AI
├── skills/
│   └── tech-cofounder/
│       └── SKILL.md          # Trae Skill version (auto-activates)
├── examples/
│   └── habit-streak/
│       └── index.html        # Live demo — open in browser
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── LICENSE
└── README.md
```

## Who is this for?

- **Solo builders** who want to go from idea to product fast
- **Non-technical founders** who want to understand what they're asking AI to build
- **Developers** who want a structured workflow instead of ad-hoc prompting
- **Product managers** who want to prototype ideas before handing off to engineering

## FAQ

**Q: Is this just a prompt?**
A: It's a structured workflow embedded in a prompt. The prompt guides the AI through 5 stages with decision points and quality gates.

**Q: Does it work with GPT-4 / Claude 3.5 / etc?**
A: Yes. It works with any AI that can follow structured instructions. Tested with ChatGPT, Claude, Cursor, and Trae.

**Q: Do I need to know how to code?**
A: No. The AI handles all code. You make product decisions. But you'll learn some code along the way.

**Q: What if my idea is too big?**
A: The Explore stage will help you find the smallest valuable slice. The AI will challenge scope creep.

**Q: Can I use this for non-software projects?**
A: The workflow (Explore → Plan → Build → Polish → Ship) works for any creative project. The code-specific parts can be skipped.

## Contributing

We welcome contributions! See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the MIT License — see [LICENSE](./LICENSE) for details.

---

<p align="center">
  If this project helped you build something, consider giving it a ⭐<br/>
  Built something with this prompt? <a href="https://github.com/anlan-bot/ai-cofounder/issues">Open an issue</a> and share it!
</p>

<p align="center">
  <sub>
    Suggested GitHub Topics: <code>ai-cofounder</code> · <code>prompt-engineering</code> · <code>vibe-coding</code> · <code>ai-workflow</code> · <code>system-prompt</code> · <code>product-management</code>
  </sub>
</p>
