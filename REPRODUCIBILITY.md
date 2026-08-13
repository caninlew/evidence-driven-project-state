# Reproducibility · 可复现性记录

## 记录模板

每次实验/回归必须记录以下字段。本仓库的 `evals/` 案例应配套此记录。

```text
- 日期：
- Agent 宿主与版本：
- 模型及版本：
- Skill commit / hash：
- 输入文件 hash：
- 工具权限（允许/禁止）：
- 温度或随机性配置：
- 输出（或输出路径）：
- 人工评审人：
- 是否重跑：是/否（重跑结果一致/不一致）
```

## 已知限制（诚实声明）

- 早期 forward test 的宿主与模型版本细节尚未全部档案化；`v0.1.0-alpha` 发布前将补齐已执行案例的记录，无法补录的标注为"historical, not fully reproducible"；
- LLM 输出存在平台漂移：同一 Skill 在不同模型版本上的输出可能不同。任何关于"方法有效"的表述，均以固定输入 + 固定版本的回放为准；
- 论文实验（held-out 测试集）将严格按本模板执行，并在论文中提供完整记录。

## 固定输入原则

- 回归案例的输入文件已冻结于 `evals/files/`（内容 hash 记录于 `evals/evals.json`）；
- 论文级 held-out 测试集：只公开文件数量、hash 与类别分布，不公开题目与答案（见 `DATA_AVAILABILITY.md`）。
