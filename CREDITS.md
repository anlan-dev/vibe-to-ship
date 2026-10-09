# 来源与第三方声明 · Credits & Attribution

本仓库（vibe-to-ship）的部分内容改编自其他开源项目。本文件列出这些来源及其许可，以满足原项目的署名要求。

This repository adapts ideas and content from other open-source projects. This file lists those sources and their licenses to satisfy attribution requirements.

---

## 1. obra/superpowers

- 来源 / Source: https://github.com/obra/superpowers
- 作者 / Author: Jesse Vincent
- 许可 / License: MIT

`skills/` 目录下的以下技能，与 obra/superpowers 中的同名技能同源，并在此基础上改写、裁剪以适配本仓库的五阶段流程（其中部分内容改写自该项目更早的版本）。它们的名称、结构与核心方法来自上游，正文经过重写，并非逐字复制。

The following skills under `skills/` are adapted from the same-named skills in obra/superpowers (some from earlier revisions of that project), then rewritten and trimmed for this repository's 5-stage workflow. Their names, structure, and core methods come from upstream; the prose has been rewritten rather than copied verbatim.

| 本仓库文件 | 上游来源 |
|---|---|
| `skills/brainstorming/SKILL.md` | obra/superpowers · `skills/brainstorming` |
| `skills/writing-plans/SKILL.md` | obra/superpowers · `skills/writing-plans` |
| `skills/subagent-driven-development/SKILL.md` | obra/superpowers · `skills/subagent-driven-development` |
| `skills/test-driven-development/SKILL.md` | obra/superpowers · `skills/test-driven-development` |
| `skills/verification-before-completion/SKILL.md` | obra/superpowers · `skills/verification-before-completion` |
| `skills/requesting-code-review/SKILL.md` | obra/superpowers · `skills/requesting-code-review` |
| `skills/receiving-code-review/SKILL.md` | obra/superpowers · `skills/receiving-code-review` |

按其 MIT 许可要求，附上原始版权与许可声明：

As required by its MIT license, the original copyright and permission notice is reproduced below:

```
MIT License

Copyright (c) 2025 Jesse Vincent

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 2. 本项目原创内容 · Original content

以下内容为本项目自行编写或改写，未改编自上述项目：

The following is written or rewritten for this project, not adapted from the projects above:

- `prompts/cofounder.md`
- `rules/`（security / coding-style / testing / quality）
- `agents/`（planner / code-reviewer / security-reviewer / polish-agent）
- `commands/`
- `docs/`、`examples/`
- `skills/tech-cofounder`、`skills/model-selection`、`skills/context-window-management`

---

## 3. 许可关系 · License relationship

本仓库整体以 GPL-3.0 发布。MIT 与 GPL-3.0 兼容：改编自 MIT 的内容可并入 GPL-3.0 作品，但必须保留上方的 MIT 版权与许可声明（本文件即为此用途）。本项目原创部分仍适用 GPL-3.0。

This repository is distributed under GPL-3.0. MIT is compatible with GPL-3.0: MIT-licensed material may be included in a GPL-3.0 work as long as the MIT notice above is retained (which is the purpose of this file). Original parts remain under GPL-3.0.

如你发现本文件遗漏了任何来源，欢迎提 Issue 补充。
If you find a source missing from this file, please open an issue.
