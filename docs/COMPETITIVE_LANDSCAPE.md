# Competitive Landscape

## 1. 结论先行

公开检索后，能找到若干“相邻项目”，但没有看到一个与本项目完全重合的开源仓库。

最接近的公开方向主要有三类：

1. markdown-native 项目管理
2. ADR / 决策记录
3. agent workflow / documentation automation

本项目的机会点，正是在这三类之间建立一个新的中间层：

**项目状态层（Project State Layer）**

## 2. 相近项目与参考意义

### 2.1 Markplane

仓库：

- https://github.com/relsas/markplane

观察：

- 强调把任务、计划、项目信息保存在 markdown 中
- 强调 local-first 与 AI 可读性
- 更接近“repo 内 markdown 原生任务系统”

对我们的启发：

- Git 仓库内 markdown 原生管理是被市场接受的表达方式
- “AI-ready project artifacts” 是一个可被理解的价值点

与本项目的差异：

- Markplane 的重点仍是任务、计划与 repo 内协作
- 本项目更关注来源登记、事实分层、冲突保留、开放问题治理

### 2.2 Backlog.md

项目入口：

- https://www.npmjs.com/package/backlog.md

观察：

- 把任务管理、验收标准、审查节点做成 markdown-native 工作流
- 明确强调 AI 时代的人机分工与任务审查

对我们的启发：

- “AI 写代码，人审任务” 这类 framing 很容易被开发者理解
- 任务文件、验收标准、阶段审查的表达值得参考

与本项目的差异：

- Backlog.md 更接近任务与执行控制
- 本项目更靠前，先处理原始资料、状态、冲突和证据治理

### 2.3 git-adr / ADR 类仓库

仓库：

- https://github.com/zircote/git-adr
- https://github.com/aufstandeq/architecture_decision_records
- https://github.com/commonality/architecture-decision-records

观察：

- ADR 生态已经证明“把决策理由写进仓库”是成熟实践
- 强调不可变历史、状态流转、可追溯性

对我们的启发：

- “记录 why，不只记录 what” 这个价值已经被开发社区教育过
- 状态流转、superseded、decision log 等概念可以借力

与本项目的差异：

- ADR 通常记录的是“已经形成的关键决策”
- 本项目治理的是“在决策形成之前，原始资料如何被清洗、分类、比对、保留冲突并转化为项目状态”

换句话说：

**ADR 更像决策层，本项目更像决策前的状态治理层。**

### 2.4 GitHub Agentic Workflows

参考：

- https://github.blog/ai-and-ml/automate-repository-tasks-with-github-agentic-workflows/
- https://github.blog/ai-and-ml/github-copilot/automating-cross-repo-documentation-with-github-agentic-workflows/

观察：

- GitHub 正在推动“markdown + agent + guardrails”的工作流表达
- 核心思想是让 agent 在受限工具和显式边界内工作

对我们的启发：

- “不是放任 agent 自由发挥，而是让 agent 在治理边界内工作”是成熟方向
- 工作流文档本身作为自动化入口，是一个有公信力的趋势

与本项目的差异：

- GitHub Agentic Workflows 更偏仓库自动化与流水线
- 本项目更偏知识密集型项目的上下文治理和状态管理

## 3. 本项目的独特定位

综合来看，本项目并不适合宣称自己是：

- 新的 Kanban 工具
- 新的 ADR 工具
- 新的通用 agent 编排器

更适合的定位是：

**an evidence-driven project-state framework for complex, multi-source workflows**

中文可表达为：

**一个面向复杂多来源项目的、基于证据与状态分层的项目整理框架。**

## 4. 建议的对外比较口径

### 与任务管理工具比较

它不替代任务看板，而是为任务看板提供更可靠的上下文基座。

### 与 ADR 比较

它不是只记录最后的决策，而是治理决策前的资料、冲突、来源和开放问题。

### 与通用 AI 提示词比较

它不是“一次性提示词”，而是一套具备边界、分类、版本和交接纪律的项目工作协议。

## 5. GitHub 首页建议避免的表述

不建议写：

- architecture-only
- for Hermes users
- for colleagues
- internal test package
- just drop files and it will do everything automatically

这些表达会让项目显得：

- 边界太窄
- 工程成熟度不足
- 过度承诺自动化能力

## 6. GitHub 首页建议保留的表述

建议保留：

- evidence-driven
- state-based
- local-first / markdown-friendly
- multi-source / multi-stakeholder
- architecture-first domain pack
- explicit boundaries and human approval

## 7. 最终判断

从公开项目对标结果看，这个项目是有独立叙事空间的。

真正需要做的不是证明“世界上完全没人做过类似的事”，而是把它讲清楚：

- 不是任务板
- 不是纯 ADR
- 不是黑盒 agent
- 而是一个把原始资料治理、项目状态层和后续研究/执行链路连起来的框架
