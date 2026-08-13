# Academic Release Policy · 学术发布政策

本政策定义"开源仓库"与"学术论文"的关系，防止仓库提前变成一篇未经同行评审的论文。

## 基本原则

1. **仓库发布 ≠ 论文发表**：GitHub 上的内容是可复现工件；论文结论以同行评审出版物为准；
2. **论文稿不放入主仓库**：手稿、统计结果、专家评审保留在私有研究区；
3. **本仓库当前不包含**：完整论文叙事、具体项目与人物案例、未经文献综述核实的创新主张（如"首个/通用"类表述）。

## 时间线规则

| 阶段 | 仓库动作 | 论文动作 |
|---|---|---|
| 现在 | `v0.1.0-alpha` Release + Zenodo DOI + Software Heritage 归档 | 私有区：研究方案冻结、held-out 测试集封存（OSF embargo） |
| 投稿前 | 仓库保持稳定；必要时创建匿名镜像供双盲引用 | 完成双盲匿名稿；自引仓库写匿名占位 |
| 双盲评审期间 | 不更新预印本；不公开新增实验内容 | 向编辑披露 repo、DOI、预印本与 AI 使用（cover letter） |
| 接受后 | 公开允许公开的测试集部分、统计与分析脚本；仓库链接论文 DOI | 正式发表；公开 held-out 测试集允许公开部分 |

## 双盲细则

- 主稿不出现作者 GitHub 用户名与可识别身份信息；
- 自引仓库用匿名占位（`[Author's repository, anonymized for review]`）；
- 补充材料用 OSF 匿名 view-only link；
- 检查文件名、PDF metadata、Git 历史与图片 EXIF 中的身份痕迹；
- 投稿时向编辑说明仓库与 DOI 的存在及其与手稿的关系。

## 预印本策略

- 初始阶段不发布预印本（避免双盲身份暴露与原创性争议）；
- 若后续需要抢优先权，优先使用 OSF Embargoed Registration（内容不可见、时间戳保留）而非公开预印本；
- 论文接受后可将最终版存入机构库/arXiv（遵循 Sage 版权政策）。

## 优先权防护（不依赖单一手段）

1. GitHub Release（含 commit hash 与发布说明）；
2. **Zenodo DOI**（每个正式 Release 一个版本 DOI + 项目 Concept DOI）；
3. **Software Heritage**（SWHID 持久标识）；
4. **OSF Embargoed Registration**（研究方案、主指标、held-out 测试集 hash 的不可修改时间戳，最长 4 年 embargo）。
