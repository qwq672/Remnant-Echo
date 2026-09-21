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
- 完善 18-testing-matrix / 19-fabric-loader-selection / 20-community-contribution-guide

### 新增（v0.1 之后）
- 新建 `planning/` 目录存放项目设计决策与规划文档
- 新增 `planning/00-planning-index.md` 规划总索引，确立**「补优先于添」**与**「以原版世界观为主」**为最高优先级设计原则
- 新增 `planning/01-spawn-point-design.md` 玩家出生点叙事设计
  - v0.1：初稿，提出方案 B+C 组合
  - v0.2：修订为方案 A（原版 loot 表扩展），完全符合「补不是添」原则
  - v0.3：修订为「补优先于添」三级优先级，方案 A（Level 1）+ 方案 B（Level 2）+ 方案 C（Level 3 彩蛋）组合实施
- 新增 `planning/02-story-timeline-plan.md` 故事时间线规划
  - 六大纪元 + Mermaid 时序图 + 因果链分析
  - 明确所有设定为**对原版留白的解读**，非新创造
  - 列出"原版关联性"判定表，允许材质/行为基于原版衍生的自定义内容
- 新增 `planning/03-player-journey-map.md` 玩家体验路径图
  - 十阶段 + Mermaid 流程图
  - 认知锁机制按三级优先级实现（Level 1: advancement + tellraw / Level 2: particle 视觉反馈 / Level 3: 自定义 frame 变体，暂不实施）
- 新增 `planning/04-auto-sync-strategy.md` 自动同步方案（GitHub Action 定时任务）
- 更新 `README.md` 添加 `planning/` 目录说明

### 关键设计决策（v0.3）
- 修订「补不是添」为「补优先于添」三级优先级原则：
  - Level 1：优先用原版物品/方块/机制承载
  - Level 2：实在没辙用原版变体（如带 NBT 的原版方块）
  - Level 3：必须自定义时，材质/行为必须与原版有关（如先民储藏室用原版石砖工艺、残破石碑材质基于原版石砖衍生、0 号唱片材质基于原版唱片纹理）
- 出生点设计：方案 A（loot 表扩展）作为基础保证，方案 B（村庄图书馆 NBT 增强）作为增强，方案 C（先民储藏室彩蛋）作为深度奖励
- 认知锁机制：Level 1（advancement + tellraw）作为基础，Level 2（particle 视觉反馈）作为备选，Level 3（自定义 frame 变体）暂不实施
- 允许的自定义内容：先民储藏室（材质基于原版石砖）、残破石碑（材质基于原版石砖衍生）、0 号唱片（材质基于原版唱片衍生）、自定义纪元名称（基于原版事件解读）
- 禁止的自定义内容：全新 Boss（如守门人作为新生物）、新种族、新维度、新机制（如灵气值）

### 新增（v0.3 之后）

**新增 5 个规划文档**：
- `planning/05-clue-book-system.md` — 线索书系统设计（Patchouli L3 自定义论证）
- `planning/06-cognitive-lock-mechanism.md` — 认知锁机制（基于原版 advancement + tellraw 详细配置）
- `planning/07-boss-narrative-binding.md` — Boss 叙事绑定（4 个原版 Boss 击杀触发记忆回放文本）
- `planning/08-music-disc-unlock-order.md` — 唱片解锁顺序与剧情对应（22 张原版 + 0 号唱片 L3 自定义）
- `planning/09-village-loot-extension.md` — 5 个原版 loot 表详细配置（5 份笔记内容设计 + Fabric API 注入）
- `planning/10-custom-items-registry.md` — L3 自定义物品登记表（残破笔记 / 线索书 / 0 号唱片 全部已论证）

**新增 L3 自定义物品**（已论证 + 已登记）：
- 残破笔记（`remnant:tattered_note`）— `written_book` + CustomModelData，满足 4 项关联性 + 退化方案
- 线索书（`patchouli:guide_book`）— 满足 5 项关联性 + 退化方案
- 0 号唱片（`remnant:music_disc_0`）— `music_disc_13` + CustomModelData，满足 5 项关联性 + 退化方案

### 关键设计决策（v0.4 · L3 登记制度）
- 所有 L3 自定义必须论证「必要性」（L1/L2 不可行的原因）+「关联性」（至少 2 项关联性标准）
- 所有 L3 自定义必须提供「退化方案」（失去模组时的行为）
- 所有 L3 自定义必须记录到 `planning/10-custom-items-registry.md`
- 永远禁止的 L3：新维度、新生物、新 Boss（作为新实体）、新种族、新数值系统

### 新增（v0.5 资料完善 · 2026-09-18 第二批）

**新增根目录 `BLUEPRINT.md`**：
- 项目蓝图总览（整合版），整合 ancient-echo.md 初版的所有要点
- 含五大核心原则、世界观总览、玩家体验流程、开发路线图、命名计划、发布与开源策略
- 标记当前进度（已完成 ✅ / 进行中 🟡 / 计划中 ⬜）

**新增 7 份规划文档**（planning/11 ~ 17）：
- `planning/11-localization-strategy.md` — 多语言支持策略（533 行）
  - L1 主导（原版 lang/ JSON 体系）
  - 首发语言：zh_cn + en_us；v0.5 引入 ja_jp；v1.0 前扩展至 8 语言
  - 字符串 key 命名规范、Patchouli 多语言策略、字体兼容性、退化方案
- `planning/12-release-roadmap.md` — 发布路线图（770 行）
  - v0.1 ~ v1.0 全里程碑 + Mermaid Gantt 图
  - L3 自定义累计仅 5 项（残破笔记 / 线索书 / 先民储藏室 / 残破石碑 / 0 号唱片），严格遵守 L1/L2/L3 占比 ~80%/~15%/~5%
  - 发布渠道策略（内部测试 → 封闭 Beta → 公开 Beta → 正式发布）
- `planning/13-save-compatibility.md` — 存档兼容性策略（290 行）
  - 三种风险场景：升级（向后兼容）/ 卸载（向后退化）/ 替换/重装（数据保留）
  - L3 自定义物品退化矩阵 + 数据持久化层级
  - NBT 版本号机制（remnant_version 字段）+ 版本迁移 function
  - Mermaid 状态转换图
- `planning/14-trial-chamber-narrative.md` — 试炼密室叙事（476 行）
  - 100% L1/L2 实现，无 L3 自定义（最佳实践案例）
  - 解读试炼密室为"先民挑战与继承测试设施"
  - 四份笔记（#7 试炼者铭言 / #8 挑战的起源 / #9 供给哲学 / #10 创造者留言）
  - 不祥试炼叙事 + Breeze/Bogged 与其他种族串联
  - 视觉叙事对照（试炼密室受控 vs 远古城市失控）
- `planning/15-netherite-enchantment-essence.md` — 下界合金/附魔本质叙事（578 行）
  - 100% L1/L2 实现，无 L3 自定义
  - 直接采纳原版 Trivia：远古残骸=猪灵挖掘残留、附魔台=先民标准银河字母
  - 四份笔记（#11 矿工的记录 / #12 提炼者笔记 / #13 附魔台匠人日记 / #14 灵魂能量研究员手记）
  - 视觉叙事：四色光谱体系（暗红=维度穿行 / 紫=维度异化 / 白=生命本源 / 蓝=灵魂能量）
  - 各类附魔的叙事解读（时运 / 精准采集 / 经验修补 / 灵魂疾行 / 火焰附加 / 绑定诅咒 / 消亡诅咒）
- `planning/16-worldview-overview.md` — 面向读者的世界观总纲（739 行）
  - 三界同源视觉与工艺证据
  - 远古先民文明四大研究领域（维度穿行 / 红石机械 / 灵魂能量 / 生命本源）
  - 六大纪元与因果链（Mermaid 流程图）
  - 关键种族演化矩阵与遗迹叙事定位
  - 玩家角色定位（局外人）+ 多角色叙事网络（M./H./K./T./E.）
  - 真结局"被遗忘的士兵"——对原版末影人留白的最深刻解读
- `planning/17-mod-introduction-copy.md` — 对外模组介绍文案（493 行）
  - 6 种文案形态：一句话简介 / 段落式简介 / 完整介绍 / 特性清单 / FAQ / 媒体宣传
  - 多语言版本：zh_cn + en_us + ja_jp
  - 用于 CurseForge / Modrinth / MC百科 / Twitter / Discord / 视频简介

### 关键设计决策（v0.5 资料完善 · 2026-09-18）
- 资料阶段基本完成，规划文档从 11 份扩展至 18 份
- 试炼密室与下界合金/附魔均实现 100% L1/L2 实现，是 L1/L2/L3 原则的最佳实践案例
- 多角色叙事网络（M./H./K./T./E.）建立，多视角拼图叙事成型
- 四色光谱体系（暗红/紫/白/蓝）作为视觉叙事主线
- "被遗忘的士兵"作为模组真结局的核心叙事，对原版末影人留白作最深刻解读

### 新增（v0.6 三界叙事 + 社区传说 + 思维导图 · 2026-09-18 第三批）

**新增 4 份三界叙事规划文档**：
- `planning/18-overworld-narrative.md` — 主世界叙事细化（842 行）
  - 遗迹/种族/事件三大矩阵按时序串联
  - 13 个社区理论汇编（MatPat/Reddit/MCBBS/YouTuber）
  - 4 份新笔记（#15 R. 撤退者 / #16 S. 航海者 / #17 E. 匠人 / #18 M. 生命树脂实验最后记录）
- `planning/19-nether-narrative.md` — 下界叙事细化（621 行）
  - 遗迹/种族/事件三大矩阵
  - 12 个社区理论汇编（10 采纳 / 1 不采纳 / 1 待评估）
  - 4 份新笔记（#19 B. 工程师日志 / #20 N. 自然学者 / #21 G. 埋葬者 / #22 L. 猪灵领袖宣言）
  - 暗红光谱视觉叙事主线
- `planning/20-end-narrative.md` — 末地叙事 + 真结局核心（1032 行）
  - 子代理调用 `web_search` 真实搜索 12 次，覆盖末影人/末影龙/末地城/End Poem 等关键词
  - 13 个社区理论汇编（基于真实搜索）
  - 4 份新笔记（#23 C. 殖民军日志 / #24 C. 等待接应 / #25 E. 维度穿行技术报告晚期 / #26 M.=曾经的 C. 告别书）
  - End Poem 重新解读（"宇宙由两个灵魂对话创造"=M. 与另一领袖对话）
  - C.=M. 同人揭晓作为真结局叙事核心
  - 紫光谱视觉叙事主线
- `planning/21-narrative-causality-map.md` — 模组叙事因果链总图
  - 完整 Mermaid flowchart（覆盖鼎盛→凋灵之灾→幽匿之厄→苍白之悔→大分裂→现代纪元→真结局）
  - 四大规律（灾难链/悲剧/视觉光谱/角色贯穿/留白）
  - 思维导图建议（指向 MINDMAP.md）

**新增社区传说汇编章节**：
- `15-community-lore/` 目录（5 份文档，基于 8 次真实 `z-ai function web_search` 调用）
  - `00-index.md` — 章节索引 + 资料权威性分级 + 模组采纳状态总表（11 完全采纳 + 11 部分采纳 + 5 不采纳 + 3 待评估）
  - `01-syntaxmine-ancient-builders.md` — SyntaxMine 三篇核心文章汇编
  - `02-matpat-game-theory.md` — MatPat Game Theory 系列理论汇编
  - `03-reddit-forum-theories.md` — Reddit / Forum 9 个社区讨论来源汇编
  - `04-end-poem-interpretations.md` — End Poem 社区解读汇编（Julian Gough 自述 + 单义哲学 + 进化复杂性 + 5 大解读维度对照表）

**新增项目思维导图**：
- 根目录 `MINDMAP.md` — 6 张 Mermaid mindmap（叙事因果链 / 玩家路径 / 资料结构 / 设计原则 / 真结局 / 多角色网络）
- `download/mindmap/` 目录 — 6 张对应 PNG 渲染（由 mermaid-cli 渲染）

### 关键设计决策（v0.6 三界叙事 + 社区传说 · 2026-09-18）
- 三界叙事（18/19/20）按因果链串联，"事得顺起来"——鼎盛→凋灵之灾→幽匿之厄→苍白之悔→大分裂→现代纪元→真结局
- 社区理论汇编严格基于真实 web 搜索（主代理 8 次 + 子代理 20 章节子代理 12 次 = 20 次），URL 与创作者署名经核实
- 真结局核心揭晓：C.=M. 同人——M. 即为先民领袖 C.，在末地等待接应，通过青金石保住灵魂
- 22 张笔记形成完整网络：#1-#6 主世界考古 / #7-#10 试炼密室 / #11-#14 下界合金+附魔 / #15-#18 主世界补充 / #19-#22 下界 / #23-#26 末地+真结局
- 12 位落款角色（M./H./K./T./E./B./N./G./L./C./R./S.）形成多视角拼图叙事
- 资料阶段基本完成，规划文档总数从 18 增至 22，加上社区传说章节共 27 份核心文档

### 新增（v0.7 设计问答 · 2026-09-21）

**新增设计问答文档**：
- `planning/22-design-questions-answers.md` — 项目方 9-20 夜间提出的 11 个核心设计问题的讨论与建议
  - Q1 玩家进入世界：不展示剧情前戏，不强制出生在村庄附近
  - Q2 第一个任务：模组不布置任务，玩家自由探索触发叙事种子
  - Q3 末地顺序：保持原版"先打龙"默认路径，认知锁不强制阻止
  - Q4 主线收尾：0 号唱片+M. 遗言；游戏开放式结尾
  - Q5 探险顺序：修订版基于 03 玩家路径，移除"猪灵入侵村庄"+补充"苍白花园"
  - Q6 古城/试炼进主线：远古城市+苍白花园必进主线；试炼密室+古迹废墟可选支线
  - Q7 工作占比：文学 50% / 代码 30% / 美术 15% / 音乐 5%
  - Q8 模组命名：推荐 Echo（待项目方审核），备选 Remnant
  - Q9 配乐场景：不新增音乐文件，通过 /playsound 配置 18+ 场景原版曲目
  - Q10 整体封装：单一模组封装；不内置光影；不改生物 AI
  - Q11 参考衍生作：参考 Legends 设定灾厄村民起源+天启骑士；Dungeons 仅作彩蛋

### 关键设计决策（v0.7 设计问答 · 2026-09-21）
- 严格遵循 L1/L2/L3 原则——所有建议均基于已有规划文档的逻辑自洽性
- 项目方需审核 4 个关键决策：Q5 探险顺序、Q8 模组命名、Q10-c 规则树放弃、Q11 衍生作采纳范围
- 审核通过后，建议将进入 01/02/03/17 等已存在规划文档的修订版本

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
