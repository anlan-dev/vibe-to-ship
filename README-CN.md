# Vibe to Ship

> © 2026 王天娇（anlan-dev）· GPL-3.0 开源 · 使用时保留作者署名与版权声明 / keep attribution


> 一个结构化的 AI 辅助开发流程框架。用规范文档约束 AI，用验收/回滚保护自己。
> 不是"帮我写代码"，而是"帮我做产品"。

[English](./README.md)

---

## 一句话

**Vibe to Ship = SDD（规范驱动开发）+ 5 阶段质量门 + 每步可回滚。**

把"我有一个想法"变成"我有一个可部署的产品"，每一步都有明确的出入口，卡住就知道往哪走。

---

## 流程总览

```
[1] 产品定位 ──→ [2] 视觉设计 ──→ [3] SDD 固化边界 ──→ [4] 小步迭代开发 ──→ [5] 部署交付
      │                │                 │                    │                    │
   PRD 草稿        UI 原型       PRD+DESIGN+ARCH         TODO.md              上线
      │                │                 │                    │                    │
      └────────────────┴─────────────────┴────────────────────┴────────────────────┘
                             每个阶段嵌入：验收标准 + 回滚机制
```

| 阶段 | 你做什么 | AI 做什么 | 质量门（不通过不可进入下一阶段） |
|------|---------|----------|------|
| **[1] 产品定位** | 回答 AI 的澄清问题 | 脑暴、追问、挑战假设 | PRD 草稿中能回答"谁用、解决什么、不做什么" |
| **[2] 视觉设计** | 搜集参考图，审批方向 | 提炼设计关键词，生成 UI 原型 | 主色调+组件风格+关键动效明确 |
| **[3] SDD 固化** | 审批 3 份文档 | 生成 PRD.md + DESIGN.md + ARCHITECTURE.md | 三份文档无矛盾，创始人签字 |
| **[4] 迭代开发** | 逐任务验收，随时回滚 | 按 TODO.md 顺序逐任务实现+测试 | 每个任务四态通过（正常/加载/空/报错） |
| **[5] 部署交付** | 在 Vercel/Netlify 部署 | 检查质量门、生成 README、更新文档 | 部署链接可访问，README 完整 |

---

## 快速开始

### 方式一：复制 Prompt（3 分钟，任何平台）

1. 打开 [`prompts/cofounder.md`](./prompts/cofounder.md)
2. 全文复制粘贴到 ChatGPT / Claude / Cursor / Trae
3. 告诉它你想做什么
4. 跟着五阶段走

### 方式二：安装为 Trae Skill

```bash
cp -r skills/tech-cofounder ~/.trae/skills/
```

然后在 Trae 中说「我想做一个工具」，AI 自动进入联合创始人模式。

### 方式三：安装为 Claude Code Skill

```bash
cp -r skills/tech-cofounder ~/.claude/skills/
```

---

## 核心原则（防失控清单）

| 原则 | 违反的后果 |
|------|-----------|
| **先文档，后代码** | MVP 范围膨胀，变成收不了尾的烂尾楼 |
| **一次只做一件事** | 多个半成品互相阻塞，哪个都交付不了 |
| **每个迭代必写验收标准** | 做完不知道对不对，上线发现一堆bug |
| **随时准备回滚** | 改崩了不敢回退，越改越乱 |
| **大变更必须走文档** | PRD 和实际代码越偏越远，最终无人维护 |

---

## 文档导航

| 你要做什么 | 看这个 |
|-----------|--------|
| 5 分钟了解框架 | 本文件（README-CN.md） |
| 粘贴到 AI 开始做产品 | [`prompts/cofounder.md`](./prompts/cofounder.md) |
| 第一次被卡住了 | [`docs/BLOCKING-POINTS.md`](./docs/BLOCKING-POINTS.md) |
| 看看别人做出来的产品 | [`examples/CASES.md`](./examples/CASES.md) |
| 了解 Agents 调度体系 | [`docs/AGENT-ARCHITECTURE.md`](./docs/AGENT-ARCHITECTURE.md) |
| Trae 用户安装 Skill | [`skills/tech-cofounder/SKILL.md`](./skills/tech-cofounder/SKILL.md) |

---

## 目录结构

```
vibe-to-ship/
├── prompts/cofounder.md          ← 🔑 核心 Prompt（粘贴即用）
├── skills/                       ← Trae / Claude Code Skill 定义
├── agents/                       ← 专项 Agent（planner, reviewer, polish, security）
├── commands/                     ← 快捷指令（/plan, /review, /polish, /ship, /test）
├── rules/                        ← 编码规范（coding-style, quality, security, testing）
├── examples/                     ← 案例 & 参考产品
└── docs/                         ← 补充文档（阻塞点手册、Agent 架构等）
```

---

## FAQ

**Q: 和直接让 AI 写代码有什么区别？**
A: 直接写 = 无约束、无验收、无回滚。Vibe to Ship = 先锁范围（SDD），再小步走（每次只做一个任务），每步验收，随时可撤。

**Q: 我必须按 5 个阶段严格走吗？**
A: 阶段 1-3（定位→设计→固边）建议严格走，这是防失控的核心。阶段 4-5 可以灵活调整。

**Q: 卡在某一步怎么办？**
A: 每个阶段的 prompt 里都内置了"阻塞点诊断树"。如果还是卡住，去看 [`docs/BLOCKING-POINTS.md`](./docs/BLOCKING-POINTS.md)。

**Q: 这个框架适合什么规模的项目？**
A: MVP/原型阶段最佳（1-5 个页面，单人开发）。大型项目建议拆成多个子项目分别走流程。

**Q: 不用 git 可以吗？**
A: 不建议。回滚机制依赖 `git reset --hard`。至少要在本地用 `git init`。
