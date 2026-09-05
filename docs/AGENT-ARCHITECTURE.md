# Agent 调度架构

> Vibe to Ship 内置 4 个专项 Agent，在阶段 4（开发）和阶段 5（交付）中被调度。
> 本文档说明：谁调谁、什么时候调、调完怎么衔接。

---

## Agent 总览

| Agent | 文件 | 职责 | 触发时机 |
|-------|------|------|---------|
| **Planner** | `agents/planner.md` | 需求分析 → 制定实现计划 | `/plan` 命令 或 阶段 4 开始时 |
| **Code Reviewer** | `agents/code-reviewer.md` | 代码审查（安全/质量/性能） | `/review` 命令 或 每个任务提交前 |
| **Polish Agent** | `agents/polish-agent.md` | UI/UX 打磨（视觉/响应式/空状态/无障碍） | `/polish` 命令 或 阶段 4 末尾 |
| **Security Reviewer** | `agents/security-reviewer.md` | 安全审计（OWASP/密钥/注入/认证） | `/security-check` 命令 或 阶段 5 部署前 |

---

## 调度流程

```
阶段 4 开始
    │
    ├── 1. Planner 生成 TODO.md（一次性）
    │
    ├── 2. 逐任务循环：
    │       │
    │       ├── 实现当前任务
    │       ├── 跑测试（/test）
    │       ├── Code Reviewer → 要求 0 CRITICAL + 0 HIGH
    │       │   ├── APPROVE → 提交 → 下一任务
    │       │   ├── WARNING → 修 HIGH 问题 → 提交 → 下一任务
    │       │   └── BLOCK   → 修 CRITICAL → 重新审查
    │       │
    │       └── 所有任务完成后 ↓
    │
    ├── 3. Polish Agent 全面检查（/polish）
    │
    └── 4. 进入阶段 5 ↓

阶段 5 开始
    │
    ├── 5. Security Reviewer 审计（/security-check）
    │   ├── 0 CRITICAL → 继续
    │   └── 有 CRITICAL → 修 → 重新审计
    │
    ├── 6. 部署上线
    │
    └── 7. 文档闭环（README.md + ARCHITECTURE.md 更新）
```

---

## Command → Agent 映射

| Command | 调度的 Agent | 命令文件 |
|---------|-------------|---------|
| `/plan` | Planner | `commands/plan.md` |
| `/review` | Code Reviewer | `commands/review.md` |
| `/polish` | Polish Agent | `commands/polish.md` |
| `/security-check` | Security Reviewer | `commands/security-check.md` |
| `/test` | 不调度 Agent（执行测试套件） | `commands/test.md` |
| `/ship` | 依次调用 Code Reviewer → Polish Agent → Security Reviewer | `commands/ship.md` |

---

## Agent 间的依赖关系

```
Planner（出计划）
    │
    │ TODO.md
    ▼
[开发者实现]
    │
    │ 代码变更
    ▼
Code Reviewer（查代码）
    │
    │ APPROVE
    ▼
Polish Agent（打磨 UI）
    │
    │ POLISHED
    ▼
Security Reviewer（审计安全）
    │
    │ APPROVE
    ▼
部署上线
```

- **Planner 是输入**：没有它的 TODO.md，后续 Agent 不知道审什么
- **Code Reviewer 是门禁**：任何代码变更通过它才能提交
- **Polish Agent 是收尾**：所有功能实现后跑一次，确保产品不"粗糙"
- **Security Reviewer 是最终防线**：部署前必须跑

---

## 审查标准速查

### Code Reviewer 判决

| 判决 | 条件 | 行动 |
|------|------|------|
| APPROVE | 0 CRITICAL, 0 HIGH | 继续 |
| WARNING | 0 CRITICAL, ≥1 HIGH | 修 HIGH 后可继续 |
| BLOCK | ≥1 CRITICAL | 必须先修 |

### Security Reviewer 判决

| 判决 | 条件 | 行动 |
|------|------|------|
| APPROVE | 0 CRITICAL | 可部署 |
| BLOCK | ≥1 CRITICAL | 禁止部署，先修 |

---

## 模型选择建议

根据任务复杂度选择不同能力的模型，控制成本：

| 任务类型 | 推荐模型等级 | 例子 |
|---------|------------|------|
| 机械实现 | 快速/便宜 | 孤立函数、明确 spec、1-2 文件 |
| 集成任务 | 标准 | 多文件协调、模式匹配 |
| 架构与审查 | 最强 | 设计决策、全局代码理解 |

---

## 与 subagent-driven-development 的关系

`skills/subagent-driven-development/SKILL.md` 描述的是**高级用户**在阶段 4 中使用的并行加速方案。核心区别：

| 维度 | 默认流程（阶段 4） | subagent-driven-development |
|------|-------------------|---------------------------|
| 执行者 | 联合创始人（单个 AI） | 多个子 Agent 并行 |
| 适用场景 | 所有 MVP | 任务高度独立 + 用户熟悉框架 |
| 审查方式 | 每任务后统一审查 | 两阶段审查（spec 合规 + 代码质量） |
| 风险 | 低 | 中（并行冲突） |

**建议**：默认用阶段 4 流程。只有当你已经用 vibe-to-ship 完成过 2-3 个产品后，再尝试 subagent 模式。

<!-- (c)2026 WangTianJiao anlan-dev | GPL-3.0 | 保留作者署名 attribution required -->
