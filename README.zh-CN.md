# Superpowers

> 本中文文档只保留三个部分：说明、技能介绍、使用方法。完整安装、贡献、许可证、社区等信息请以英文 [README.md](README.md) 为准。

## 说明

Superpowers 是一套面向编码智能体的软件开发方法论。它通过一组可组合的技能，让智能体在写代码前先澄清目标、确认设计、制定计划，并在实现过程中持续测试、审查和验证。

它的核心目标是让智能体少猜测、少返工，更多地按照可验证的流程交付软件改动。

## 技能介绍

### 基础工作流技能

1. **brainstorming**
   - 用途：在写代码前澄清需求、探索方案、拆解设计。
   - 适合：需求还不明确、只有粗略想法、需要先形成设计方案时。

2. **using-git-worktrees**
   - 用途：为开发任务创建隔离的 Git worktree 和分支。
   - 适合：需要并行开发、避免污染当前工作区、保持任务隔离时。

3. **writing-plans**
   - 用途：把已确认的设计拆成可执行的小任务。
   - 适合：设计已经确定，需要明确每一步修改文件、实现内容和验证方式时。

4. **executing-plans**
   - 用途：按计划分批执行任务，并在关键节点请求确认。
   - 适合：希望智能体稳定推进实现，但仍保留人工检查点时。

5. **subagent-driven-development**
   - 用途：为每个任务派发独立子智能体，实现后再进行规格符合性和代码质量审查。
   - 适合：任务较多、希望加快实现并提高审查覆盖率时。

6. **test-driven-development**
   - 用途：强制执行 RED-GREEN-REFACTOR 流程：先写失败测试，再写最小实现，再重构。
   - 适合：修复 bug、添加功能、需要可验证行为变化时。

7. **requesting-code-review**
   - 用途：在任务完成后请求代码审查，按严重程度报告问题。
   - 适合：进入下一步之前，需要确认实现是否符合计划和质量要求时。

8. **receiving-code-review**
   - 用途：处理代码审查反馈，修正问题并重新验证。
   - 适合：已有审查意见，需要系统性解决反馈时。

9. **finishing-a-development-branch**
   - 用途：在开发分支完成后运行验证，并决定合并、创建 PR、保留或丢弃分支。
   - 适合：任务完成，需要收尾、清理 worktree 或准备提交时。

### 调试与验证技能

1. **systematic-debugging**
   - 用途：使用分阶段方法定位根因，而不是凭直觉试错。
   - 适合：问题原因不清楚、修复多次失败、需要追踪根因时。

2. **verification-before-completion**
   - 用途：在声明完成前实际验证结果。
   - 适合：修复 bug、完成实现、准备汇报结果之前。

### 协作与并行技能

1. **dispatching-parallel-agents**
   - 用途：把相互独立的调查或实现任务并行分派给多个子智能体。
   - 适合：需要同时检查多个文件、模块、方案或问题来源时。

### 元技能

1. **using-superpowers**
   - 用途：介绍并启用 Superpowers 技能系统。
   - 适合：会话开始、需要让智能体知道何时自动使用技能时。

2. **writing-skills**
   - 用途：指导如何编写、测试和改进新的技能。
   - 适合：需要为通用工作流创建或修改技能时。

## 使用方法

Superpowers 会在支持的编码智能体中作为插件或扩展安装。安装后，智能体会在合适的任务阶段自动检查并使用相关技能。

### Claude Code

可通过 Claude 官方插件市场安装：

```bash
/plugin install superpowers@claude-plugins-official
```

也可以通过 Superpowers marketplace 安装：

```bash
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

### 其他支持的工具

Superpowers 也支持 Antigravity、Codex、Cursor、Factory Droid、GitHub Copilot CLI、Kimi Code、OpenCode 和 Pi 等工具。不同工具的安装方式不同，但使用方式相同：安装后让智能体在开发任务中自动触发对应技能。

### 日常使用方式

你不需要手动记住每个技能名称。正常描述你的开发目标即可，例如：

```text
我们来做一个 React todo list。
```

智能体应先触发需求澄清和设计流程，而不是直接写代码。

如果你已经知道要使用某个技能，也可以明确要求：

```text
使用 test-driven-development 来修复这个 bug。
```
