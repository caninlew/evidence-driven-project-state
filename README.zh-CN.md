# Evidence-Driven Project State

一个把复杂、多来源材料转成可追溯项目状态、有边界任务与可校审交接的证据驱动框架。

当前是 **architecture-first**：建筑实践已积累真实迭代，方法目标可扩展到咨询、产品、研究等知识密集型场景，但跨领域等效性仍需公开评测，而不是只靠宣称。

> 本仓库由一位隶属于 TJAD AI专班 / 量子城市专班的个人独立开源发布。隶属关系仅作个人背景说明，不代表 TJAD、专班或任何单位的官方发布、审定、授权或背书。详见 [AUTHORS.md](AUTHORS.md)。

## 它解决什么问题

普通项目系统擅长跟踪任务，却常常丢失任务背后的证据。本框架在原始材料与后续执行之间增加一个受控状态层：

- 说法来自哪里、由谁提出；
- 属于法规、合同、客户、专业、运营还是 Agent 哪个效力域；
- 是已发布、已确认、暂定、冲突还是 Agent 生成；
- 指标口径能否比较；
- 哪些问题仍未关闭；
- 哪些建议没有得到批准；
- 下一轮什么工作可以安全推进。

## 四个 Skill

- `architect-project-state`：来源、效力、指标、变更与有界任务；
- `architect-method-lens`：从证据与反例提炼方法假设，不做人格或风格模拟；
- `design-test-framework-rounds`：把方法转成可比较、可证伪的测试，而不是过早出方案；
- `architect-wiki-builder`：可选的 LLM Wiki 检索适配层，任何候选结论都必须回到 canonical Raw 核验。

```text
项目循环：原始资料 -> 项目状态 -> 方法镜头 -> 测试框架 -> 人工决策
学习循环：失败暴露 -> 人工纠正 -> Skill 更新 -> 固定输入回归 -> 下一版本
```

真正可复用的不是某次回答，而是经过纠正与回归验证的工作规程。

## 兼容性

Skill 使用开放的 Agent Skills 文件夹结构，并把 frontmatter 收敛为通用的 `name + description`。

| 宿主 | 当前定位 |
|---|---|
| Hermes Agent | 原始工作流的主要实测环境 |
| OpenClaw | 重点适配目标；运行时等效验证仍在继续 |
| 其他 Agent Skills 宿主 | 目前只声明格式目标，不声明完整兼容 |

详见 [安装说明](docs/INSTALLATION.md)。格式可加载不等于工具、权限、刷新方式和行为输出完全一致。

## 八条纪律

1. 先登记，再解释。
2. 用“效力域＋来源状态＋归因”判断来源，不用文件名或一条总排名。
3. 不同指标口径默认分开。
4. 冲突并存，不静默抹平。
5. Agent 提案不得自动进入项目事实。
6. 具名方法必须有证据与反例，不模拟人格。
7. 失败基线要保留，Skill 更新要用固定案例回归。
8. 专业判断、法规结论、客户承诺和署名责任留给明确的人。

## 开始使用

- [安装说明](docs/INSTALLATION.md)
- [快速开始](docs/QUICKSTART.md)
- [流程结构](docs/ARCHITECTURE_FLOW.md)
- [贡献指南](CONTRIBUTING.md)
- [作者与隶属声明](AUTHORS.md)
- [安全说明](SECURITY.md)
- [评测案例](evals/README.md)
- [研究状态](RESEARCH_STATUS.md)
- [可复现性](REPRODUCIBILITY.md)
- [数据可用性](DATA_AVAILABILITY.md)
- [来源与演变](PROVENANCE.md)
- [学术发布边界](ACADEMIC_RELEASE_POLICY.md)
- [公开发布门](docs/PUBLIC_RELEASE_GATE.md)

## 当前状态

**公开 alpha / architecture-first。** 方法来自 Hermes Agent 中的多轮真实任务纠正与 forward test；当前仓库已加入去标识化 Skill、宿主安装说明、CI 检查与机器可读 smoke cases。尚不宣称其他宿主或非建筑领域已经达到等效质量。

本仓库是研究软件产物，不是同行评议结论或论文预印本；现有案例用于开发回归，不是独立 held-out benchmark。详见 [研究状态](RESEARCH_STATUS.md)。

## 引用

研究或衍生工作应引用实际使用的版本化 Release。仓库提供 `CITATION.cff.template`，但在发布者姓名、ORCID（如使用）和最终仓库 URL 确认前，不应生成生效的 `CITATION.cff`。详见[公开发布门](docs/PUBLIC_RELEASE_GATE.md)。

## License

MIT，见 [LICENSE](LICENSE)。
