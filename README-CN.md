# Vibe to Ship

> 一个结构化的 prompt，让任何 AI 成为你的技术联合创始人。
> 不只是生成代码 — 一套五阶段工作流，从想法到上线。

[English](./README.md)

## 它和直接用 AI 有什么区别？

大多数 AI prompt 给你的是一个**角色**。这个给你的是一个**流程**。

| 方式 | 你得到什么 |
|------|-----------|
| 「帮我做一个 app」 | 代码（可能能跑，可能不是你要的） |
| AI 角色扮演 prompt | 一次有趣的对话，没有实际产出 |
| **Vibe to Ship** | 一套有质量门的结构化工作流 |

区别在于：你不只是得到一个 app，你学会了**怎么像产品负责人一样思考**。

## 五阶段工作流

```
① 探索 → ② 规划 → ③ 构建 → ④ 打磨 → ⑤ 交付
```

| 阶段 | 发生什么 | 谁做决定 |
|------|---------|---------|
| **探索** | AI 提问，理解你真正需要什么 | 你回答，AI 挑战假设 |
| **规划** | 定义功能、技术栈、复杂度、资源 | 你审批计划 |
| **构建** | 分阶段开发，每步测试通过再继续 | 你审查每一步 |
| **打磨** | 设计一致性、边界情况、性能、可访问性 | 你确认最终效果 |
| **交付** | 部署、文档、维护 | 你拥有这个产品 |

每个阶段都有**质量门** — 前一阶段不达标，不能进入下一阶段。

## 快速开始

### 方式一：复制 prompt（任意 AI 平台）

1. 复制 [`prompts/cofounder.md`](./prompts/cofounder.md) 中的 prompt
2. 粘贴到 ChatGPT / Claude / Cursor / 任意 AI
3. 告诉它你想做什么
4. 跟着五阶段走

### 方式二：安装 Trae Skill（推荐 Trae 用户）

```bash
# 将 skill 复制到 Trae skills 目录
cp -r skills/tech-cofounder ~/.trae/skills/
```

然后在 Trae 中说「我想做一个工具」，AI 会自动进入联合创始人模式。

### 方式三：安装为 Claude Code Skill

```bash
# 将 skill 复制到 Claude Code skills 目录
cp -r skills/tech-cofounder ~/.claude/skills/

# 将规则复制到 Claude Code rules 目录
cp -r rules/* ~/.claude/rules/

# 将智能体复制到 Claude Code agents 目录
cp -r agents/* ~/.claude/agents/

# 将命令复制到 Claude Code commands 目录
cp -r commands/* ~/.claude/commands/
```

## 里面有什么

Vibe to Ship 现在是一个完整的系统 — 不只是一个 prompt，而是一个模块化框架，包含规则、智能体、命令和技能。

```
vibe-to-ship/
├── prompts/
│   └── cofounder.md              # 核心 prompt — 复制粘贴到任意 AI
├── skills/
│   ├── tech-cofounder/
│   │   └── SKILL.md              # Trae/Claude Code skill（自动激活）
│   ├── brainstorming/
│   │   └── SKILL.md              # 通过苏格拉底式对话精炼设计（硬门禁）
│   ├── writing-plans/
│   │   └── SKILL.md              # 创建详细实施计划
│   ├── subagent-driven-development/
│   │   └── SKILL.md              # 用独立子智能体执行计划
│   ├── test-driven-development/
│   │   └── SKILL.md              # 红-绿-重构循环
│   ├── verification-before-completion/
│   │   └── SKILL.md              # 确保工作真正完成
│   ├── requesting-code-review/
│   │   └── SKILL.md              # 结构化审查流程
│   ├── receiving-code-review/
│   │   └── SKILL.md              # 建设性地回应反馈
│   ├── model-selection/
│   │   └── SKILL.md              # 为每个任务选择合适的模型
│   └── context-window-management/
│       └── SKILL.md              # 优化上下文窗口使用
├── rules/                        # 始终遵循的规则
│   ├── security.md               # 安全检查清单
│   ├── coding-style.md           # 代码风格规范
│   ├── testing.md                # 测试要求（TDD + 80% 覆盖率）
│   └── quality.md                # 阶段质量门、视觉打磨、可访问性
├── agents/                       # 专用子智能体
│   ├── planner.md                # 实施规划
│   ├── code-reviewer.md          # 代码质量审查
│   ├── security-reviewer.md      # 安全漏洞检测
│   └── polish-agent.md           # 视觉打磨、边界情况
├── commands/                     # 快捷命令
│   ├── plan.md                   # /plan — 创建实施计划
│   ├── review.md                 # /review — 代码质量审查
│   ├── security-check.md         # /security-check — 安全审计
│   ├── test.md                   # /test — 运行测试检查覆盖率
│   ├── polish.md                 # /polish — 视觉打磨
│   └── ship.md                   # /ship — 部署前检查
├── examples/
│   └── habit-streak/
│       └── index.html            # 在线演示
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── LICENSE
└── README.md
```

### 规则

确保每个产品都安全、代码规范、经过测试的模块化准则：

| 规则 | 内容 |
|------|------|
| **安全** | 禁止硬编码密钥、输入验证、OWASP 基础、应急协议 |
| **代码风格** | 不可变性、文件组织、命名规范、错误处理 |
| **测试** | TDD 工作流、80% 覆盖率、边界情况测试 |
| **质量** | 阶段门禁、视觉一致性、响应式设计、可访问性 |

### 智能体

可以委派任务的专用子智能体：

| 智能体 | 何时使用 |
|--------|---------|
| **规划者** | 写代码之前 — 创建详细实施计划 |
| **代码审查员** | 写完代码后 — 审查质量、安全、模式 |
| **安全审查员** | 认证/API/支付代码 — OWASP 审计、漏洞检测 |
| **打磨智能体** | 阶段 4 — 视觉一致性、边界情况、响应式、可访问性 |

### 命令

快速访问常用工作流的斜杠命令：

| 命令 | 用途 |
|------|------|
| `/plan` | 写代码前创建实施计划 |
| `/review` | 代码质量和安全审查 |
| `/security-check` | 专项安全审计 |
| `/test` | 运行测试检查覆盖率 |
| `/polish` | 视觉打磨和边界情况处理 |
| `/ship` | 部署前检查和部署 |

### 技能

增强工作流各阶段的模块化技能：

| 类别 | 技能 | 用途 |
|------|------|------|
| **设计** | 头脑风暴 | 通过苏格拉底式对话精炼设计（硬门禁） |
| **设计** | 编写计划 | 创建详细实施计划 |
| **设计** | 子智能体开发 | 用独立子智能体执行计划 |
| **开发** | 测试驱动开发 | 红-绿-重构循环 |
| **开发** | 完成前验证 | 确保工作真正完成 |
| **审查** | 请求代码审查 | 结构化审查流程 |
| **审查** | 接收代码审查 | 建设性地回应反馈 |
| **优化** | 模型选择 | 为每个任务选择合适的模型 |
| **优化** | 上下文窗口管理 | 优化上下文窗口使用 |

## 使用方法

1. 从一个产品想法开始（任何清晰度都行）
2. AI 会问你问题 — 诚实回答
3. 写代码之前先审批计划
4. 每个功能做好后立刻测试
5. 打磨到你觉得专业
6. 上线

### 示例对话

```
你：我想做一个习惯打卡工具

AI（作为联合创始人）：好想法。在动手之前，我想先搞清楚几件事：
1. 你现在怎么记录习惯？痛点是什么？
2. 只给你自己用，还是也想分享给别人？
3. 最小可用版本长什么样？
4. 你有多少时间？

你：我用表格记录，太丑了而且老忘。
只给我自己用，只要一个 streak 计数器和每日提醒。
这个周末。

AI：明白了。这是 v1 计划：
- 单文件 HTML（不需要服务器，不需要安装）
- 一个习惯、一个 streak、一个提醒
- 新拟物风格，移动端优先
- 复杂度：简单（2-3 小时）

要开始吗？
```

## 案例

### 案例 1：习惯·原子钟

用 Vibe to Ship 工作流构建的极简习惯打卡工具。

**功能**：追踪一个习惯，用热力图可视化连续天数，AI 推荐最佳打卡时间。

**构建时间**：1 个会话（约 2 小时）

**技术栈**：单文件 HTML，localStorage，零依赖

[在线体验](https://anlan-dev.github.io/vibe-to-ship/examples/habit-streak/) | [源码](./examples/habit-streak/index.html)

### 案例 2：待补充

更多案例正在构建中。想贡献你的案例？提交 PR！

## 适合谁？

- **独立开发者**：快速从想法到产品
- **非技术创始人**：理解你在让 AI 做什么
- **开发者**：用结构化流程替代随意提问
- **产品经理**：在交给工程团队之前先验证想法

## 常见问题

**Q: 这不就是一个 prompt 吗？**
A: 这是一个嵌入在 prompt 中的结构化工作流。prompt 引导 AI 经过 5 个阶段，每个阶段有决策点和质量门。

**Q: 支持哪些 AI？**
A: 任何能理解结构化指令的 AI 都支持。已在 ChatGPT、Claude、Cursor、Trae 上测试。

**Q: 我需要会写代码吗？**
A: 不需要。AI 负责所有代码，你做产品决策。但过程中你会学到一些代码。

**Q: 如果我的想法太大怎么办？**
A: 探索阶段会帮你找到最小可用版本。AI 会挑战范围蔓延。

**Q: 能用于非软件项目吗？**
A: 五阶段工作流（探索→规划→构建→打磨→交付）适用于任何创意项目。代码相关的部分可以跳过。

## 贡献

1. Fork 这个仓库
2. 把你的案例加到 `examples/`
3. 提交 PR，附上你做了什么的描述

## 许可证

MIT

## 如果这个项目帮到了你，请点个 Star！

如果你用这个 prompt 做了一个产品，开一个 issue 分享出来，我会加到案例区。
