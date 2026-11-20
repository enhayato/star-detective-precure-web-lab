# Star Detective Precure Web Lab

《名探偵プリキュア！》2026 年活动回忆档案馆的 GitHub Pages 开发实验仓库。

**项目定位：**面向粉丝，通过日历和地图重温已发生的活动。这不是实时活动公告、报名或导航站，也不承诺收录完整性。

## 当前状态

- **已在 main 上线的稳定基线：**最初的 HTML 练习页，GitHub Pages 从 `main/(root)` 自动发布。
- **正在审查的 V1.2 原型：**日历 UI（2026 年月切换、单日／整月、地区与类型筛选、活动预览、响应式布局、URL 状态恢复）。合并对应 PR 之前，它**不在正式 Pages 地址上**。
- 演示数据仅包含一条已在内部史料导航定位的 2026-10-15 Staff Talk，**没有接入完整活动数据库**。演示数量不能用于推断活动总数或地区覆盖情况。
- **地图独立候选原型：**新增 `map.html`，全国47都道府县和东京62区市町村真实行政边界的简化SVG交互、离岛视图、时间筛选、记录高亮及地区下拉选择。原始边界为2025年版；有关精度、授权核查与数据改造说明见 [docs/MAP_DATA.md](docs/MAP_DATA.md)。查看仓库 `map.html`；该文件只有被合并到 `main` 且Pages部署成功后，才能通过 `/map.html` 在公开网站访问。
- 正式活动详情、其他46府县二级地图、完整活动档案、正式数据导入与离线 ZIP 尚未实现。

## 设计规范

- [UI 设计规范 V1.2](docs/UI_DESIGN_V1.2.md)：**本仓库未来的主要设计维护文件**，记录已经认可的产品定位、视觉语言、日期／地图规则、尚未决定事项、版本历史和实施状态。
- [原始 Google Docs 交接说明 V1.2](https://docs.google.com/document/d/1DKExfW0TC3AzFJtBci9M0NKEHX-VdPbgNt5GLtV0euc/edit)：保留历史交接。
- [原始视觉参考包 V1.2](https://drive.google.com/file/d/1ciQbeNd0XKXE3uQEBINDV-Wt8aWg8mrK/view)：五张视觉稿，含已否决的 V1.0；图中地图几何、活动数量、地名与示意活动不可当作事实。

## 网站访问

已部署网站（`main` 分支）：https://enhayato.github.io/star-detective-precure-web-lab/

**注意：**新分支上的 UI 只有在 PR 经审查合并并且 Pages 工作流部署成功后，才会出现在上述网址。

## 如何维护

1. 从最新 `main` 创建新的功能分支。
2. 修改 `index.html`（界面、样式、当前原型数据）或 `docs/UI_DESIGN_V1.2.md`（设计决策），只修改需要修改的文件。
3. 提交 Commit，创建 Pull Request，检查 Files changed、交互效果、演示数据来源。
4. 人工批准并合并到 `main`；检查 Actions 的 `pages build and deployment` 是否为 Success。
5. 在电脑和手机分别检查已发布网页。出错时首先检查 PR 变更及 Actions 日志，不要直接覆盖整仓库。

**原型说明：**当前 `index.html` 是无外部依赖的单文件 HTML/CSS/JavaScript，方便直接查看和维护；后续复杂化再考虑拆成多个文件。正式活动数据接入前，应先批准公开字段、去重规则与核查流程。
