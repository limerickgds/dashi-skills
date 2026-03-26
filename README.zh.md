# dashi-skills

一个以“理论先行”方式构建的 skills 仓库。这里的很多 skill 并不只是为了自动化执行某个步骤，而是尝试把苏格拉底提问、控制论、系统论、结构化复盘等较为稳固的理论，转化成 AI 助手可以复用的分析框架与工作方法。

这个仓库关注的不只是完成任务，也关注 AI 助手如何更好地提问、评审、建模、反思，以及把理论映射到实际协作中。

## 目标

- 将理论框架转译为可复用的 agent 行为，而不只是收集流程清单
- 提供可复用的 skill 模块，增强 AI 与人的协作效率

## 当前 Skill 列表

| Skill | 说明 |
|-------|------|
| `socratic-mirror` | 通过苏格拉底式提问与逻辑审视，帮助用户检查假设、盲点与推理模式。 |
| `double-loop-execution-reviewer` | 以 after action review 与 double-loop learning 为框架，围绕执行证据生成复盘、交接说明或改进备忘录，并进一步检视目标、假设与工作规则是否需要调整。 |
| `cybernetics-agent-seminar` | 一个控制论 × AI Agent 研讨 skill，把反馈、稳态、黑箱方法、必要多样性等理论映射到 Agent 架构分析、设计指导和理论讨论中。 |
| `zettelkasten-knowledge-gardener` | 以 Zettelkasten、evergreen notes、PARA 和 progressive summarization 为基础，把零散笔记、对话和阅读材料整理成可复用、可维护的知识资产。 |
| `editorial-git-committer` | 把 Git history 视为可刻意编排的项目叙事，帮助检查改动、拆分混合提交、改进 commit message，并在安全边界内整理最近的本地提交历史。 |
| `visual-knowledge-excalidraw` | 一个 Obsidian Excalidraw 制图 skill：把文本需求转成 `.excalidraw.md`，并在存在 Obsidian 导出自动化时，通过导出 PNG 回看并继续优化布局、连线与可读性。 |

## 使用方式

从这个仓库安装 skills：

```bash
npx skills limerickgds/dashi-skills
```

这条命令会安装 `limerickgds/dashi-skills` 发布出来的 skills。

## 许可证

[MIT](./LICENSE)
