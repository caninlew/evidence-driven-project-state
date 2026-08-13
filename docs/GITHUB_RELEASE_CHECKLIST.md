# GitHub Release Checklist

## 1. 必做项

- [x] 统一项目名称为 `Evidence-Driven Project State`
- [x] 删除或隔离所有带有“同事测试”“Hermes 专用”等内部语义的文件
- [x] README 改为公开仓库口径，而非交接包口径
- [x] 明确项目定位：core framework + architecture domain pack
- [x] 补充至少 1 个非建筑领域样例
- [x] 增加 `LICENSE`
- [x] 增加 `CONTRIBUTING.md`
- [x] 增加 `SECURITY.md`
- [x] 检查是否存在不应公开的内部路径、姓名、组织名、产品名

## 2. 强烈建议项

- [x] 增加英文版或双语 README
- [x] 增加仓库 topics
- [x] 增加架构图或最小流程图
- [x] 增加“适用边界 / 不适用边界”章节
- [x] 增加 examples 目录
- [x] 增加版本号和 changelog 规则

## 3. 技术清理项

- [x] 检查 skill 内部是否仍有不可公开的路径引用
- [x] 检查相对路径是否在新目录结构中保持有效
- [x] 检查是否存在需要替换的内部术语
- [x] 检查可选依赖的默认地址和说明是否准确

## 4. 叙事清理项

发布前应避免：

- “给同事试用”
- “内部测试版”
- “Hermes 工作流实验”
- “直接丢文件进去自动全做完”

发布时应突出：

- evidence-driven
- state-based
- multi-source
- architecture-first
- domain-extensible
- explicit approval boundaries

## 5. 开源姿态建议

建议采用的开源姿态是：

1. 先把方法和结构讲清楚
2. 再把 skill 作为可执行实现附上
3. 最后逐步扩展更多 domain pack

不要一开始就把项目包装成“大而全 AI 项目管理平台”。

## 6. 发布时的最小完成标准

满足以下条件即可发布 v0：

- [x] README 能独立解释项目价值
- [x] 至少 1 个真实 domain pack 可用
- [x] 至少 1 个 example 可帮助理解
- [x] 有贡献说明和许可证
- [x] 没有明显内部痕迹

## 7. 最佳首发策略

建议首发为：

**方法框架 + 建筑领域包 + 公开 examples**

先建立可信度，再逐步引入更多领域扩展。
