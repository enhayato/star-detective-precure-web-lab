# Star Detective Precure Web Lab

《名探偵プリキュア！》2026 年活动回忆档案馆的 GitHub Pages 开发实验仓库。

**项目定位：**面向粉丝，通过日历和地图重温已发生的活动。这不是实时活动公告、报名或导航站，也不承诺收录完整性。

## 当前状态（2026-11-20）

- **稳定上线：**2026年日历原型（PR #4）及独立日本地图原型（PR #5）均已合并到 `main`，GitHub Pages 成功部署，并经用户在 PC / iPhone 上完成基础实测。
- **本轮开发：**`feature/calendar-map-navigation` 增加日历 ↔ 地图双向跳转及年月、单日／整月、地区、活动类型筛选的状态继承。**须经本轮 PR 审查、合并和 Pages 部署后才会上线**，当前不得视为已验收。
- **地区粒度限制：**日历只提供「全部／东京都／其他地区」三种选项；地图可选47府县，并在东京都细选区市町村。地图返回日历时，非东京具体府县统一落到「其他地区」，具体区市町村统一落到「东京都」，页面会主动说明筛选粒度变化。
- **地图范围：**全国47都道府县；二级区划目前仅实现东京都62个真实区市町村。原始行政边界使用2025版数据的简化衍生图形，仍待2026版边界、使用条件等终验。出典和限制见 [地图数据说明](docs/MAP_DATA.md)。
- **演示数据：**只有一条内部史料导航定位的2026-10-15 Staff Talk 示例，**尚未接入完整研究数据库**。不能据此推断活动数量或覆盖范围。
- **尚未实现：**其他46府县二级行政地图、活动详情纪念册、完整档案列表、正式数据导入、离线 ZIP。

## 设计规范

- [UI 设计规范 V1.2](docs/UI_DESIGN_V1.2.md)：**本仓库未来的主要设计维护文件**，记录已经认可的产品定位、视觉语言、日期／地图规则、尚未决定事项、版本历史和实施状态。
- [原始 Google Docs 交接说明 V1.2](https://docs.google.com/document/d/1DKExfW0TC3AzFJtBci9M0NKEHX-VdPbgNt5GLtV0euc/edit)：保留历史交接。
- [原始视觉参考包 V1.2](https://drive.google.com/file/d/1ciQbeNd0XKXE3uQEBINDV-Wt8aWg8mrK/view)：五张视觉稿，含已否决的 V1.0；图中地图几何、活动数量、地名与示意活动不可当作事实。

## 网站访问

已部署网站（`main` 分支）：

- [活动日历](https://enhayato.github.io/star-detective-precure-web-lab/)
- [活动地图](https://enhayato.github.io/star-detective-precure-web-lab/map.html)

**注意：**新分支上的 UI 只有在 PR 经审查合并并且 Pages 工作流部署成功后，才会出现在上述网址。

## 如何维护

1. 从最新 `main` 创建新的功能分支。
2. 修改 `index.html`（日历）、`map.html`（地图）、`docs/UI_DESIGN_V1.2.md`（当前设计与开发状态）等目标文件；不要改无关文件。
3. 提交 Commit，创建 Pull Request，检查 Files changed、交互效果、演示数据来源。
4. 人工批准并合并到 `main`；检查 Actions 的 `pages build and deployment` 是否为 Success。
5. 在电脑和手机分别检查已发布网页。出错时首先检查 PR 变更及 Actions 日志，不要直接覆盖整仓库。

**原型说明：**日历、地图均采用静态 HTML/CSS/JavaScript；地图额外读取仓库内的本地 JSON 边界数据。正式活动数据接入前，应先批准公开字段、去重规则与核查流程。
