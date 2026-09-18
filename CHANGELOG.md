# Changelog

本文件记录资料汇编的所有重要变更。

格式参考 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)。

---

## [Unreleased]

### 计划中
- 补充 Minecraft 1.21.5+ 的 Happy Ghast 后续更新公告
- 抓取 SyntaxMine 社区理论文章（需手动定位 URL）
- 补充社区公认的 C418 唱片解读理论
- 添加 MC百科（中文 Wiki）的中文原文对照
- 完善试炼密室叙事章节（试炼钥匙、不祥试炼、劫掠兽关联）

### 新增（v0.1 之后）
- 新建 `planning/` 目录存放项目设计决策与规划文档
- 新增 `planning/00-planning-index.md` 规划总索引，确立**「补不是添」**与**「以原版世界观为主」**为最高优先级设计原则
- 新增 `planning/01-spawn-point-design.md` 玩家出生点叙事设计
  - v0.1：初稿，提出方案 B+C 组合
  - v0.2：修订为方案 A（原版 loot 表扩展），完全符合「补不是添」原则
  - 不新增自定义结构、不新增自定义物品，仅向原版 loot 表追加 `written_book` 条目
- 新增 `planning/02-story-timeline-plan.md` 故事时间线规划
  - 六大纪元 + Mermaid 时序图 + 因果链分析
  - 明确所有设定为**对原版留白的解读**，非新创造
  - 列出严格禁止的「添」项（新种族、新文明、新维度等）
- 新增 `planning/03-player-journey-map.md` 玩家体验路径图
  - 十阶段 + Mermaid 流程图
  - 认知锁机制修订为基于原版 `advancement` 触发器实现，不新增自定义机制
- 新增 `planning/04-auto-sync-strategy.md` 自动同步方案（GitHub Action 定时任务）
- 更新 `README.md` 添加 `planning/` 目录说明

### 关键设计决策
- 确立「补不是添」原则：所有设计必须能用原版物品/方块/机制承载，禁止新增自定义结构、物品、方块、Boss、机制
- 确立「以原版世界观为主」原则：所有叙事设定必须基于原版已有线索，不引入官方未提及的新种族/文明/纪元
- 出生点设计放弃强制生成村庄方案，改为向原版 loot 表追加 `written_book` 条目
- 认知锁机制放弃自定义机制，改为基于原版 `advancement` + `tellraw` 实现

---

## [0.1.0] - 2026-09-18

### 新增
- 初始化仓库结构，15 个章节目录
- 抓取并整理 133 个来源页面
  - minecraft.net 官方文章 ~60 篇
  - minecraft.wiki 条目 ~65 条
  - en.wikipedia.org / en.wikisource.org 3 条
  - matpat.fandom.com 1 条
- 生成 35 个 Markdown 文件，约 1,400+ 条原文引用段落
- 添加 README.md 主索引
- 添加 99-source-index.md 完整来源索引
- 添加 CONTRIBUTING.md 贡献指南
- 添加 PUSH_TO_GITHUB.md 推送指南
- 添加 .gitignore

### 章节覆盖
- 00-overview: End Poem 全文（公共领域）、Music of Minecraft、MatPat Game Theory
- 01-pale-garden: 苍白花园、嘎枝、嘎枝之心
- 02-happy-ghast: 快乐恶魂、恶魂、恶魂之泪
- 03-ancient-city-warden: 远古城市、监守者、幽匿、深暗
- 04-trial-chambers: 试炼密室、1.21 Tricky Trials 更新
- 05-villager-family: 村民、流浪商人、铁傀儡、傻瓜村民
- 06-piglin-family: 猪灵、僵尸猪灵、堡垒遗迹
- 07-ender-family: 末影人、末影龙、末地城、末地船、紫珀块、紫颂果、末影珍珠、末影之眼、潜影贝
- 08-illagers: 掠夺者、卫道士、唤魔者、劫掠兽、恼鬼、林地府邸、掠夺者前哨站
- 09-wither-and-nether-fortress: 凋灵、凋灵骷髅、下界要塞
- 10-other-hostile-mobs: 苦力怕、流髑、尸壳、烈焰人、幻翼、蝙蝠、炽足兽、疣猪兽、守卫者、远古守卫者、女巫、银鱼、幻术师
- 11-overworld-structures: 要塞、末地传送门、废弃传送门、沙漠神殿、丛林神庙、废弃矿井、遗迹废墟、可疑沙子/沙砾、陶片、考古、哭泣黑曜石、重生锚
- 12-key-items: 下界合金、远古残骸、附魔台、紫颂果
- 13-music-discs: 全部 22 张唱片（13/cat/blocks/chirp/far/mall/mellohi/stal/strad/ward/11/wait/Pigstep/otherside/5/Relic/Creator/Creator (Music Box)/Precipice）
- 14-official-derivatives: Minecraft Legends、Minecraft Dungeons
