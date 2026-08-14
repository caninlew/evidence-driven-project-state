# GitHub Release Checklist

本清单检查仓库是否达到工程公开标准。涉及署名、知识产权和论文时点的硬门槛，另见 [PUBLIC_RELEASE_GATE.md](PUBLIC_RELEASE_GATE.md)。

## 1. 仓库内容

- [x] 项目名称统一为 `Evidence-Driven Project State`
- [x] README 能独立解释项目价值、边界与 architecture-first 状态
- [x] 包含 MIT License、贡献指南、安全说明与行为准则
- [x] 包含至少一个非建筑领域开发样例
- [x] 四个 Skill 使用可移植的 `name` + `description` frontmatter
- [x] 去除具名建筑师、事务所、客户、项目与本地路径残留
- [x] 开发 fixtures 与 held-out benchmark 明确区分

## 2. 研究与权利边界

- [x] 声明 public alpha、未同行评议和未验证范围
- [x] 声明公开数据与不可公开数据的边界
- [x] 声明第三方材料不受本仓库 MIT License 自动覆盖
- [x] 声明个人贡献与机构隶属、机构作者身份相互独立
- [x] 提供非生效的 `CITATION.cff.template`
- [x] 发布者姓名、ORCID（如使用）与最终仓库 URL 已确认
- [x] 单位知识产权与隶属措辞已完成书面确认
- [x] 已生成无占位符的正式 `CITATION.cff`

## 3. 自动检查

- [x] GitHub Actions `Repo Health` 通过
- [x] Skill frontmatter、相对链接与 eval JSON 通过
- [x] 绝对本地路径、敏感案例名与私有研究目录扫描为零
- [x] 密钥和认证文件扫描为零
- [x] `.zenodo.json` 不存在，当前无引用元数据优先级冲突

## 4. GitHub 首发顺序

1. 先创建 private repository，完成一次远端渲染与 Actions 检查。
2. 完成 [PUBLIC_RELEASE_GATE.md](PUBLIC_RELEASE_GATE.md) 的全部 P0 项。
3. 转为 public，并在创建首个 Release 前连接 Zenodo GitHub 集成。
4. 创建 `v0.1.0-alpha` Release，而不是只打 tag。
5. 核对 Zenodo 归档与 DOI；随后将 DOI 写入下一次引用元数据版本。
6. 请求或核对 Software Heritage 归档并记录 SWHID。

## 5. 不进入本仓库

- 论文手稿与审稿通信
- 未公开的完整研究协议与假设
- held-out 案例、答案与调参历史
- 客户、参与者、机密或受版权限制的原始材料
- 凭据、私有配置、终端日志与本机绝对路径

满足工程检查不等于可以公开；任何 P0 发布阻断项未完成，都应停在 private repository。
