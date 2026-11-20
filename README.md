# Star Detective Precure Web Lab

《名探偵プリキュア！》2026 年活动回忆档案馆的 GitHub Pages 开发实验仓库。

**项目定位：**面向粉丝，通过日历和地图重温已发生的活动。这不是实时活动公告、报名或导航站，也不承诺收录完整性。

## 当前状态（2026-11-20）

- **稳定上线：**2026年日历原型（PR #4）及独立日本地图原型（PR #5）均已合并到 `main`，GitHub Pages 成功部署，并经用户在 PC / iPhone 上完成基础实测。
- **已上线并验收：**PR #6 于2026-11-20合并到 `main`（`7ddc843`），Pages 部署成功，用户报告 PC/iPhone 双向联动测试正常；时间、类别及粗粒度地区条件可跨页继承。
- **纪念册原型：**本阶段通过 PR #7 开发 `event.html` 与共享 `data/events-demo.json`。活动资料仍处于演示与待核验状态；PR 合并与设备验收以 GitHub、用户后续记录为准。
- **地区粒度限制：**日历只提供「全部／东京都／其他地区」三种选项；地图可选47府县，并在东京都细选区市町村。地图返回日历时，非东京具体府县统一落到「其他地区」，具体区市町村统一落到「东京都」，页面会主动说明筛选粒度变化。
- **地图范围：**全国47都道府县；二级区划目前仅实现东京都62个真实区市町村。原始行政边界使用2025版数据的简化衍生图形，仍待2026版边界、使用条件等终验。出典和限制见 [地图数据说明](docs/MAP_DATA.md)。
- **演示数据：**只有一条内部史料导航定位的2026-10-15 Staff Talk 示例，**尚未接入完整研究数据库**。不能据此推断活动数量或覆盖范围。
- **尚未实现：**其他46府县二级行政地图、经正式核验和图片授权的纪念册内容、完整档案列表、正式数据导入、离线 ZIP。

## 设计规范

- [UI 设计规范 V1.2](docs/UI_DESIGN_V1.2.md)：**本仓库未来的主要设计维护文件**，记录已经认可的产品定位、视觉语言、日期／地图规则、尚未决定事项、版本历史和实施状态。
- [原始 Google Docs 交接说明 V1.2](https://docs.google.com/document/d/1DKExfW0TC3AzFJtBci9M0NKEHX-VdPbgNt5GLtV0euc/edit)：保留历史交接。
- [原始视觉参考包 V1.2](https://drive.google.com/file/d/1ciQbeNd0XKXE3uQEBINDV-Wt8aWg8mrK/view)：五张视觉稿，含已否决的 V1.0；图中地图几何、活动数量、地名与示意活动不可当作事实。

## 网站访问

已部署网站（`main` 分支）：

- [活动日历](https://enhayato.github.io/star-detective-precure-web-lab/)
- [活动地图](https://enhayato.github.io/star-detective-precure-web-lab/map.html)
- [活动纪念册原型](event.html)：需经 PR 合并并成功部署后方可在线访问

**注意：**新分支上的 UI 只有在 PR 经审查合并并且 Pages 工作流部署成功后，才会出现在上述网址。

## 如何维护

1. 从最新 `main` 创建新的功能分支。
2. 按功能范围修改 `index.html`（日历）、`map.html`（地图）、`event.html`（纪念册）、`data/events-demo.json`（共用演示资料）及有关文档；不要修改无关文件。
3. 提交 Commit，创建 Pull Request，检查 Files changed、交互效果、演示数据来源。
4. 人工批准并合并到 `main`；检查 Actions 的 `pages build and deployment` 是否为 Success。
5. 在电脑和手机分别检查已发布网页。出错时首先检查 PR 变更及 Actions 日志，不要直接覆盖整仓库。

**原型说明：**日历、地图均采用静态 HTML/CSS/JavaScript；地图额外读取仓库内的本地 JSON 边界数据。正式活动数据接入前，应先批准公开字段、去重规则与核查流程。

## 演示活动数据的维护

唯一演示活动数据保存在 [data/events-demo.json](data/events-demo.json)，日历、地图和纪念册共用这一份文件。字段说明见 [docs/EVENT_DATA.md](docs/EVENT_DATA.md)。不要直接把独立研究数据库的内部审计字段发布到网站，也不能以本条演示记录推断全国活动数量。
