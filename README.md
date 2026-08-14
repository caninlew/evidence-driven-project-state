# Evidence-Driven Project State

[中文](#中文) · [English](#english)

> 把复杂、多来源工作转成可追溯项目状态、有边界行动与可校审交接。
>
> Turn complex, multi-source work into traceable project state, bounded action, and reviewable handoffs.

---

<a id="中文"></a>

## 中文

当前是 **architecture-first**：建筑实践已经历多轮真实任务纠正与回归测试；治理方法以咨询、产品、研究等知识密集型工作为扩展目标，但在公开评测完成前，不宣称跨领域等效。

> 本仓库由隶属于 TJAD AI专班 / 量子城市专班的个人独立开发与发布。单位信息仅作作者背景说明，不代表 TJAD、专班或任何单位的官方发布、审定、授权或背书。详见 [AUTHORS.md](AUTHORS.md)。

### 为什么需要它

普通项目系统擅长跟踪任务，却常常丢失任务背后的证据。本框架在原始材料和执行之间增加一个受控状态层，用来回答：

- 每项关键说法来自哪里、由谁提出；
- 它属于法规、合同、客户、专业、运营还是 Agent 的效力域；
- 它是已发布、已确认、暂定、冲突还是 Agent 生成；
- 不同指标口径能否比较；
- 哪些问题仍未关闭，哪些建议从未获批；
- 下一轮哪些工作可以在明确边界内安全推进。

### 核心命题

复杂项目中最困难的常常不是生成内容，而是治理上下文。先把来源观察、当前事实、相关方陈述、正式决定、Agent 推导、工作假设、未批准提案、开放问题和任务彼此分开，再让 Agent 推进工作。

### 包含的四个 Skill

- `architect-project-state`：来源、效力、指标、变更与有界任务；
- `architect-method-lens`：从证据与反例提炼方法假设，不做人格或风格模拟；
- `design-test-framework-rounds`：把方法转成可比较、可证伪的测试，而不是过早出方案；
- `architect-wiki-builder`：可选的 LLM Wiki 检索适配层，候选结论必须回到 canonical Raw 核验。

```text
项目循环：原始资料 -> 项目状态 -> 方法镜头 -> 测试框架 -> 人工决策
学习循环：失败暴露 -> 人工纠正 -> Skill 更新 -> 固定输入回归 -> 下一版本
```

真正可复用的不是某次回答，而是经过纠正与回归验证的工作规程。

### 兼容性

这些 Skill 使用开放的 Agent Skills 文件夹结构，并将 frontmatter 收敛为通用的 `name + description`。

| 宿主 | 当前定位 |
|---|---|
| Hermes Agent | 原始工作流的主要实测环境 |
| OpenClaw | 重点适配目标；运行时等效验证仍在继续 |
| 其他 Agent Skills 宿主 | 目前只声明格式目标，不声明完整兼容 |

详见[安装说明](docs/INSTALLATION.md)。格式可加载不等于工具、权限、刷新方式和行为输出完全一致。

### 适用边界

适合：建筑与城市设计团队、证据密集型咨询、模糊产品探索、研究计划，以及来源频繁变化的多方协作项目。

不适合：简单一次性任务、只需要看板的团队，或期待 Agent 自行裁决尚未解决的权责与效力冲突的工作流。

### 八条证据纪律

1. 先登记，再解释。
2. 用“效力域＋来源状态＋归因”判断来源，不用文件名或单一总排名。
3. 不同指标口径默认分开。
4. 冲突并存，不静默抹平。
5. Agent 提案不得自动进入项目事实。
6. 具名方法必须有证据与反例，不模拟人格。
7. 保留失败基线，Skill 更新后用固定案例回归。
8. 专业判断、法规结论、客户承诺和署名责任留给明确的人。

### 开始使用

- [安装说明](docs/INSTALLATION.md) · [快速开始](docs/QUICKSTART.md)
- [流程结构](docs/ARCHITECTURE_FLOW.md) · [采用模型](docs/ADOPTION_MODEL.md)
- [贡献指南](CONTRIBUTING.md) · [作者与隶属声明](AUTHORS.md) · [安全说明](SECURITY.md)
- [评测案例](evals/README.md) · [研究状态](RESEARCH_STATUS.md) · [可复现性](REPRODUCIBILITY.md)
- [数据可用性](DATA_AVAILABILITY.md) · [来源与演变](PROVENANCE.md)
- [学术发布边界](ACADEMIC_RELEASE_POLICY.md) · [公开发布门](docs/PUBLIC_RELEASE_GATE.md)

### 当前状态与引用

**v0.1.0-alpha / architecture-first。** 现有案例用于开发回归，不是独立 held-out benchmark；本仓库是研究软件产物，不是同行评议结论或论文预印本。详见[研究状态](RESEARCH_STATUS.md)。

研究或衍生工作应引用实际使用的版本化 Release。机器可读的引用元数据见 [`CITATION.cff`](CITATION.cff)；作者 ORCID 为 [0009-0004-0228-4526](https://orcid.org/0009-0004-0228-4526)。

---

<a id="english"></a>

## English

This project is **architecture-first** today. It has grown through repeated real-task corrections and regression tests in architectural practice. The governance method is intended to generalize to consulting, product, research, and other knowledge-intensive work, but it does not claim cross-domain parity before published evaluation.

> This repository is independently developed and released by an individual affiliated with the TJAD AI and Quantum City working groups. The affiliation is biographical only; this is not an official TJAD or working-group publication, approval, authorization, or endorsement. See [AUTHORS.md](AUTHORS.md).

### Why this exists

Most project systems track tasks but lose the evidence behind them. This framework adds a controlled state layer between raw material and execution to record:

- where each consequential claim came from and who made it;
- which authority domain it belongs to;
- whether it is issued, confirmed, provisional, contested, or Agent-generated;
- which metric definitions are compatible;
- which conflicts and questions remain open;
- which recommendations were never approved;
- what bounded work may safely proceed next.

### Core thesis

The hard part of ambiguous project work is often context governance, not content generation. Separate source observations, current facts, stakeholder statements, decisions, derivations, assumptions, proposals, open questions, and tasks before asking an Agent to advance the work.

### Included Skills

- `architect-project-state` — evidence, authority, metrics, change, and bounded tasks;
- `architect-method-lens` — evidence-backed method hypotheses and counterexamples, without persona or style imitation;
- `design-test-framework-rounds` — comparable, falsifiable design tests rather than premature schemes;
- `architect-wiki-builder` — an optional LLM Wiki retrieval adapter with canonical-Raw verification.

```text
project loop: raw sources -> controlled state -> method lens -> test frameworks -> human decision
learning loop: failure -> human correction -> Skill revision -> fixed-input regression -> next release
```

The second loop turns one-off conversations into reusable, reviewable experience.

### Compatibility

These Skills follow the open Agent Skills folder pattern and use portable `name` + `description` frontmatter.

| Host | Current position |
|---|---|
| Hermes Agent | Primary tested environment for the originating workflow |
| OpenClaw | Primary compatibility target; runtime parity validation is ongoing |
| Other Agent Skills hosts | Format target only until host-specific smoke tests pass |

See [Installation](docs/INSTALLATION.md). Compatibility does not imply identical tools, permissions, refresh behavior, or outputs.

### Intended use

Best fit: architecture and urban design teams, evidence-heavy consulting, ambiguous product discovery, research programs, and multi-stakeholder projects with frequent revisions.

Not a fit: trivial tasks, teams needing only a Kanban board, or workflows that expect an Agent to decide unresolved authority conflicts autonomously.

### Evidence discipline

1. Register before interpreting.
2. Judge authority by domain, source status, and attribution—not filename or a single global rank.
3. Keep incompatible metric definitions separate.
4. Preserve conflict instead of flattening it.
5. Do not inherit Agent proposals as project facts.
6. Keep named-person methods evidence-backed and never simulate a personality.
7. Preserve failed baselines and test Skill changes against fixed cases.
8. Keep professional judgment, statutory conclusions, client commitments, and authorship with identified humans.

### Start here

- [Installation](docs/INSTALLATION.md) · [Quickstart](docs/QUICKSTART.md)
- [Architecture flow](docs/ARCHITECTURE_FLOW.md) · [Adoption model](docs/ADOPTION_MODEL.md)
- [Contributing](CONTRIBUTING.md) · [Authors and affiliation](AUTHORS.md) · [Security](SECURITY.md)
- [Evaluation cases](evals/README.md) · [Research status](RESEARCH_STATUS.md) · [Reproducibility](REPRODUCIBILITY.md)
- [Data availability](DATA_AVAILABILITY.md) · [Provenance](PROVENANCE.md)
- [Academic release policy](ACADEMIC_RELEASE_POLICY.md) · [Public release gate](docs/PUBLIC_RELEASE_GATE.md)

### Status and citation

**v0.1.0-alpha / architecture-first.** The included cases are development regressions, not a held-out benchmark. This repository is a research software artifact, not a peer-reviewed result or preprint. See [RESEARCH_STATUS.md](RESEARCH_STATUS.md).

Use the exact versioned release in research or derivative work. Machine-readable citation metadata is available in [`CITATION.cff`](CITATION.cff); the author ORCID is [0009-0004-0228-4526](https://orcid.org/0009-0004-0228-4526).

## Repository structure / 仓库结构

```text
.
├── docs/
├── evals/
├── examples/
└── skills/
    ├── architect-project-state/
    ├── architect-method-lens/
    ├── design-test-framework-rounds/
    └── architect-wiki-builder/
```

Directory names inside a user's project are recommendations, not protocol requirements. The real boundary is one explicit project root, task-relevant sources, traceable state, and clear write authority.

用户项目中的目录名称只是建议，不是协议要求。真正的边界是：一个明确的项目根目录、与任务相关的来源、可追溯状态，以及清晰的写入权限。

## License / 许可证

MIT. See [LICENSE](LICENSE)。
