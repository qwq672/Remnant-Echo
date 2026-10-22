# 20 · 重大版本开发过程汇编 · Version Development Stories

> 本文件属于 **Remnant Echo 模组资料汇编** 的剧情扩展章节（`17-lore-extensions/`）。
> 收录 Minecraft 1.9-1.20 期间重大版本的开发过程、争议、设计变更、幕后故事。
>
> **资料优先级**：P1（Minecraft 官方+Wiki）+ P2（社区高流传度考据）
> **汇编日期**：2026-10-19
> **状态**：🟢 完成（基于已收集的资料，含 1.9 Combat Update 争议+1.15 Buzzy Bees+1.20 Trails & Tales）

---

## 1. 项目方问题

> "1.9 Combat Update 争议 + 1.15 Buzzy Bees + 1.20 Trails & Tales 开发过程"

本汇编补充 [`00-overview/05-completeness-audit-report.md`](../00-overview/05-completeness-audit-report.md) §7.2 列出的"仍存空白"中关于版本开发过程的部分。

---

## 2. 1.9 Combat Update（2016）——最具争议的更新

### 2.1 基本资料

- **正式名称**：Combat Update
- **发布日期**：2016-02-29（Java Edition 1.9）
- **首个快照**：15w31a（2015-07-29）
- **快照数量**：约 60 个
- **主题**：战斗机制重做 + 末地扩展

### 2.2 核心新内容

**战斗机制**：
- **Shield（盾牌）** 取代剑格挡
- **Attack Cooldown（攻击冷却）**——根据武器速度决定 DPS
- **Off-hand（副手）**——可装备第二件物品
- **Sweeping attack（横扫攻击）**——剑的群体攻击
- **Trident（三叉戟）** 延后到 1.13

**末地完全重做**：
- 5 个群系（详见 [`19-end-biome-history.md`](./19-end-biome-history.md)）
- 末地城+末地船+潜影贝+鞘翅
- 末地折跃门
- 紫颂果+紫珀砖+末地石砖

**其他**：
- **Elytra（鞘翅）** + 烟花火箭飞行
- **Skeleton Trap Horse（骷髅陷阱马）**——雷暴中触发的骷髅骑手
- **Lingering Potion（滞留药水）**
- **End Crystal 重生末影龙**
- **Spectral Arrow（光灵箭）**

### 2.3 争议：Attack Cooldown

**核心争议**：Attack Cooldown（攻击冷却）机制引发了 PvP 社区大规模反对

**反对理由**：
- 1.8 PvP 的"快速点击"机制被破坏——玩家不能再通过快速点击实现高 DPS
- "快攻 vs 重击"的二元化选择降低了 PvP 灵活性
- 大量 PvP 服务器长期停留在 1.8 版本

**Mojang 应对**：
- 推出 **Combat Test 系列**（Combat Test 1/2/3/4/5/6/7/8/8c）
- Combat Test 8c 于 2020-08 发布
- 截至 2026 仍无正式版发布——Mojang 在持续测试中
- 详见 [`17-lore-extensions/15-cut-unused-features.md`](./15-cut-unused-features.md) §6.4 引用 Minecraft Wiki Mentioned features "Combat changes"

### 2.4 模组叙事关联

- 🟡 Attack Cooldown 争议 = 模组"现代纪元玩家分歧"叙事的现实参照
- 🟡 Combat Test 8c 4 年未发布 = 模组"被搁置的内容"叙事的原版官方案例
- 🟢 **末地完全重做** = 模组"末地叙事"（[`planning/20-end-narrative.md`](../planning/20-end-narrative.md)）的原版官方基础——所有末地群系+末地城+末地船+鞘翅+潜影贝均来自 1.9

---

## 3. 1.15 Buzzy Bees（2019）——蜜蜂更新

### 3.1 基本资料

- **正式名称**：Buzzy Bees
- **发布日期**：2019-12-17（Java Edition 1.15）
- **首个快照**：19w34a（2019-08-22）
- **快照数量**：约 17 个
- **主题**：蜜蜂+蜂蜜

### 3.2 核心新内容

**新生物**：
- **Bee（蜜蜂）** —— 被动中立生物，攻击玩家后死亡（类似现实蜜蜂）
- **Baby Bee（幼年蜜蜂）**

**新方块**：
- **Beehive（蜂巢）** —— 自然生成的蜜蜂巢
- **Bee Nest（蜂箱）** —— 玩家制作的蜜蜂箱
- **Honey Block（蜂蜜块）** —— 粘性方块，可减缓下落速度，可粘连实体
- **Honeycomb Block（蜜脾块）** —— 装饰方块
- **Honey Bottle（蜂蜜瓶）** —— 可食用+解毒
- **Honeycomb（蜜脾）** —— 制作蜂箱材料

**新机制**：
- **蜜蜂授粉**——传播作物生长
- **蜂蜜瓶解毒**——可解除中毒效果
- **蜂蜜块机制**——可拖动实体，被红石利用

### 3.3 开发过程

**预告**：
- 2019-09-28 MINECON Live 2019 公布——但只展示蜜蜂+蜂蜜，未公布 1.15 名称
- 2019-10 公布名称 "Buzzy Bees"

**快照**：
- 19w34a（2019-08-22）：首个快照，添加蜜蜂和蜂巢
- 19w35a ~ 19w44a：持续完善
- 1.15-pre1 ~ pre7（2019-11）：pre-release
- 1.15 RC1 ~ RC2（2019-12）：release candidate
- 1.15 正式版：2019-12-17

### 3.4 模组叙事关联

- 🟡 蜜蜂 = 模组"鼎盛纪元先民畜牧繁荣"叙事的视觉资源
- 🟡 蜂蜜块 = 模组"先民冶金技术"叙事的"粘合材料"
- 🟡 蜜蜂授粉机制 = 模组"先民农业技术"叙事的背景

### 3.5 与 1.16 的关系

- 1.15 是 1.16 Nether Update 之前的小版本
- 1.15 主要是社区期待已久的蜜蜂更新
- 1.15 之后 1.16 重新进入重大更新节奏

---

## 4. 1.20 Trails & Tales（2023）——考古与叙事

### 4.1 基本资料

- **正式名称**：Trails & Tales
- **发布日期**：2023-06-07（Java Edition 1.20）
- **首个快照**：23w03a（2023-01-18）
- **快照数量**：约 18 个
- **主题**：考古+叙事+探险

### 4.2 核心新内容

**新生物**：
- **Sniffer（嗅探兽）** —— Mob Vote 2022 胜者（详见 [`00-overview/06-mob-menagerie-modern-mobs.md`](../00-overview/06-mob-menagerie-modern-mobs.md) §2.1）
- **Camel（骆驼）** —— 沙漠村庄骑乘生物

**新方块**：
- **Suspicious Sand（可疑沙子）** —— 考古刷子挖掘点
- **Suspicious Gravel（可疑砾石）** —— 考古刷子挖掘点（1.20 后加入）
- **Brush（刷子）** —— 考古工具
- **Decorated Pot（装饰罐）** —— 4 个陶片合成的装饰容器
- **Torchflower（火炬花）** —— Sniffer 挖出的远古植物
- **Pitcher Plant（投手植物）** —— Sniffer 挖出的远古植物

**新群系**：
- **Cherry Grove（樱花林）** —— 粉色樱花树林

**新结构**：
- **Trail Ruins（遗迹路径）** —— 埋在地下的考古结构，含 4 种陶片

**新物品**：
- 4 种 Pottery Shards（陶片）：archer、prize、arms_up、skull
- **Name Tag（名签）** —— 玩家可制作（之前只能从宝箱获取）
- **Hanging Sign（悬挂告示牌）**

**新机制**：
- **Archeology（考古）** —— 用刷子挖掘可疑沙子，获取陶片
- **Camel 双骑乘** —— 2 名玩家骑乘同一只骆驼
- **Sniffer 蛋孵化** —— 从海底废墟的可疑沙子中获取

### 4.3 开发过程

**预告**：
- 2022-10-15 Minecraft Live 2022 公布——含 Sniffer（投票胜者）+ Camel + 樱花林 + 考古
- 但 1.20 名称未公布

**快照**：
- 23w03a（2023-01-18）：首个快照
- 23w04a ~ 23w18a：持续完善
- 1.20-pre1 ~ pre7（2023-05）：pre-release
- 1.20 RC1（2023-06）：release candidate
- 1.20 正式版：2023-06-07

**与 Minecraft Live 2022 的关系**：
- Sniffer 是 Mob Vote 2022 胜者
- 樱花林是 Biome Chooser 2018 投票败给 Taiga 后的承诺实现
- 考古是从 1.14 Village & Pillage 推迟的内容

### 4.4 模组叙事关联

- 🟢 **核心叙事资源**——Sniffer 作为"远古生物"+考古机制 = 模组"先民文明考古"叙事的原版官方机制
- 🟢 **Trail Ruins（遗迹路径）** = 模组"先民遗迹"叙事的原版结构资源——可作为模组笔记触发的物理载体
- 🟡 樱花林 = 模组"鼎盛纪元自然繁荣"叙事的视觉资源
- 🟢 **考古机制** = 模组 v0.5+ 玩家"探索先民遗迹"叙事的原版官方机制——用原版刷子挖掘可疑沙子获取笔记是模组 L1 实现
- 🟢 **装饰罐** = 模组笔记触发的物理载体——4 个陶片合成装饰罐，可作为笔记触发器

### 4.5 与模组 L1/L2/L3 原则的契合度

1.20 Trails & Tales 是模组 L1/L2/L3 原则的**最佳原版官方背书**：
- **L1 原版物品优先**：考古刷子+装饰罐+陶片+Sniffer 都是原版物品，模组直接使用
- **L2 原版组合优先**：装饰罐由 4 个陶片合成 = 模组"原版组合"的最佳案例
- **L3 必要自定义**：模组仅需自定义"残破笔记"等少量新物品

模组 v0.5+ 笔记触发机制可完全采用 1.20 考古机制：
- 玩家用原版刷子挖掘可疑沙子
- 获取"残破笔记"（L3 自定义）
- 装饰罐合成（4 个陶片+1 张残破笔记？）

---

## 5. 重大版本开发过程总表

| 版本 | 名称 | 发布日期 | 首个快照 | 快照数 | 主题 |
|------|------|----------|----------|--------|------|
| 1.9 | Combat Update | 2016-02-29 | 15w31a | ~60 | 战斗机制+末地扩展 |
| 1.10 | Frostburn Update | 2016-06-08 | 16w20a | ~8 | 结构生成+骸骨马 |
| 1.11 | Exploration Update | 2016-11-14 | 16w32a | ~20 | 林地府邸+灾厄村民 |
| 1.12 | World of Color | 2017-06-07 | 17w06a | ~15 | 彩色陶瓦+混凝土 |
| 1.13 | Update Aquatic | 2018-07-18 | 17w43a | ~40 | 海洋重做 |
| 1.14 | Village & Pillage | 2019-04-23 | 18w43a | ~50 | 村庄+灾厄村民 |
| 1.15 | Buzzy Bees | 2019-12-17 | 19w34a | ~17 | 蜜蜂 |
| 1.16 | Nether Update | 2020-06-23 | 20w06a | ~30 | 下界重做 |
| 1.17 | Caves & Cliffs Part I | 2021-06-08 | 20w45a | ~25 | 紫晶洞+滴水石 |
| 1.18 | Caves & Cliffs Part II | 2021-11-30 | 1.18 exp1 | ~10 | 世界生成重做 |
| 1.19 | Wild Update | 2022-06-07 | 22w03a | ~15 | 深暗之域+监守者 |
| 1.20 | Trails & Tales | 2023-06-07 | 23w03a | ~18 | 考古+Sniffer |
| 1.21 | Tricky Trials | 2024-06-13 | 23w41a | ~20 | 试炼密室 |

---

## 6. 模组采纳状态总表

### 6.1 完全采纳（作为核心叙事资源）

| 编号 | 版本开发过程 | 模组采纳形式 |
|------|--------------|--------------|
| V1 | **1.9 Combat Update 末地完全重做** | 模组"末地叙事"原版官方基础——所有末地群系+末地城+末地船+鞘翅+潜影贝均来自 1.9 |
| V2 | **1.15 Buzzy Bees 蜜蜂+蜂蜜块** | 模组"鼎盛纪元先民畜牧繁荣"叙事的视觉资源 |
| V3 | **1.20 Trails & Tales 考古机制** | 模组 v0.5+ 笔记触发机制的原版官方背书——用原版刷子挖掘可疑沙子获取残破笔记 |
| V4 | **1.20 装饰罐** | 模组笔记触发的物理载体——4 个陶片合成 |
| V5 | **1.20 Trail Ruins** | 模组"先民遗迹"叙事的原版结构资源 |
| V6 | **1.20 Sniffer** | 模组"远古生物"叙事的原版官方实装 |
| V7 | **1.20 樱花林** | 模组"鼎盛纪元自然繁荣"叙事的视觉资源 |
| V8 | **1.13 Update Aquatic 沉船+海底废墟** | 模组"沉没的文明"叙事的原版结构资源 |
| V9 | **1.14 Village & Pillage 灾厄村民** | 模组"灾厄村民"支线的原版起点 |
| V10 | **1.16 Nether Update 下界重做** | 模组"凋灵之灾"叙事的原版基础——玄武岩三角洲+绯红森林+诡异森林+灵魂沙峡谷 |
| V11 | **1.17/1.18 Caves & Cliffs 拆分** | 模组"重大版本拆分"叙事案例——Mojang 把 Caves & Cliffs 拆成两部分 |
| V12 | **1.19 Wild Update 深暗之域+监守者** | 模组"幽匿之厄"纪元核心叙事——监守者=sculk 守护者 |
| V13 | **1.21 Tricky Trials 试炼密室** | 模组"试炼密室"叙事（[`planning/14-trial-chamber-narrative.md`](../planning/14-trial-chamber-narrative.md)）原版基础 |

### 6.2 部分采纳（参考但不实装）

- 1.9 Combat Update Attack Cooldown 争议——仅作为模组"现代纪元玩家分歧"叙事的现实参照
- 1.15 蜂蜜块机制——仅作为模组"先民冶金技术"叙事的"粘合材料"
- 1.20 Camel 双骑乘——仅作为模组"鼎盛纪元先民迁徙"叙事的视觉资源

### 6.3 不采纳（仅记录）

- 1.10 Frostburn Update / 1.11 Exploration Update / 1.12 World of Color——仅记录

---

## 7. 与其他规划文档的引用关系

| 引用文档 | 关联章节 |
|----------|----------|
| [`planning/02-story-timeline-plan.md`](../planning/02-story-timeline-plan.md) | §5.5 大分裂 → §5.6 现代纪元——1.9 Combat Update 末地重做 = 模组"大分裂末地分支"的原版基础 |
| [`planning/14-trial-chamber-narrative.md`](../planning/14-trial-chamber-narrative.md) | §3 试炼密室叙事——1.21 Tricky Trials 原版基础 |
| [`planning/18-overworld-narrative.md`](../planning/18-overworld-narrative.md) | §6 灾厄村民支线——1.14 Village & Pillage 原版起点 |
| [`planning/19-nether-narrative.md`](../planning/19-nether-narrative.md) | §3.3.4 暗红光谱——1.16 Nether Update 群系 |
| [`planning/20-end-narrative.md`](../planning/20-end-narrative.md) | §5 末地群系——1.9 末地完全重做 |
| [`00-overview/05-completeness-audit-report.md`](../00-overview/05-completeness-audit-report.md) | §7.2 仍存空白——本文档补充 |
| [`17-lore-extensions/19-end-biome-history.md`](./19-end-biome-history.md) | 末地群系开发史 |

---

## 8. 参考资料

### 8.1 官方资料（P1）

- minecraft.wiki Java Edition 1.9：<https://minecraft.wiki/w/Java_Edition_1.9>
- minecraft.wiki Java Edition 1.15：<https://minecraft.wiki/w/Java_Edition_1.15>
- minecraft.wiki Java Edition 1.20：<https://minecraft.wiki/w/Java_Edition_1.20>
- minecraft.wiki Java Edition Combat Tests：<https://minecraft.wiki/w/Java_Edition_Combat_Tests>
- minecraft.wiki Buzzy Bees：<https://minecraft.wiki/w/Buzzy_Bees>
- minecraft.wiki Trails & Tales：<https://minecraft.wiki/w/Trails_%26_Tales>
- minecraft.net Village & Pillage out today on Java：<https://www.minecraft.net/en-us/article/village---pillage-out-java->
- minecraft.net Update Aquatic is out on Java：<https://www.minecraft.net/en-us/article/update-aquatic-out-java>
- minecraft.net Nether Update out today on Java：<https://www.minecraft.net/en-us/article/nether-update-java>
- minecraft.net Caves & Cliffs Part II The Features：<https://www.minecraft.net/en-us/article/caves---cliffs-part-ii-the-features>

### 8.2 社区资料（P2）

- minecraft.fandom.com Village & Pillage：<https://minecraft.fandom.com/wiki/Village_%26_Pillage>
- minecraft.fandom.com Caves & Cliffs：<https://minecraft.fandom.com/wiki/Caves_%26_Cliffs>
- minecraft-archive.fandom.com 1.13 The Update Aquatic：<https://minecraft-archive.fandom.com/wiki/1.13_-_The_Update_Aquatic>
- reddit.com/r/xboxone Minecraft Caves & Cliffs update Splitting into 2 updates：<https://www.reddit.com/r/xboxone/comments/mqsuz5/minecraft_caves_cliffs_update_splitting_into_2>
- planetminecraft.com Let's share the Minecraft 1.14 Village & Pillage update：<https://www.planetminecraft.com/forums/minecraft/discussion/minecraft-1.14-release-586336>

### 8.3 搜索关键词与调用次数

无新增搜索——本文档基于已收集的资料整理。

---

## 9. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-10-19 | v1.0 | 初次创建——基于已收集资料，收录 1.9 Combat Update 争议+1.15 Buzzy Bees+1.20 Trails & Tales 三个重大版本的开发过程，补充 1.10-1.21 完整版本时间线 | 项目方 |
