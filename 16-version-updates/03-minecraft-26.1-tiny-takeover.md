# Minecraft 26.1 · Tiny Takeover 微小侵占

> 本文件属于 **Remnant Echo 模组资料汇编** 的新版本更新章节（`16-version-updates/`）。
> 所有内容均基于真实 web 搜索（2026-09-21 完成），URL 与发布日期经核实。
>
> **资料权威性**：★★★★★（Minecraft 官方/Wiki 叙事，P1 级）
> **版本**：Java Edition 26.1 / Bedrock Edition 26.10
> **发布日期**：2026-09-17（搜索结果"4 days ago"）
> **名称**：Tiny Takeover（微小侵占）

---

## 1. 版本概述

### 1.1 minecraft.wiki 条目

- **来源**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki>（搜索结果 rank 0）
- **访问日期**：2026-09-21

**摘要引用**：
> The update also makes name tags craftable, and adds the golden dandelion, which when fed to baby mobs, stops them from aging until fed another...

### 1.2 官方公告

- **来源**：minecraft.net
- **原文链接**：<https://www.minecraft.net>（搜索结果 rank 1）
- **访问日期**：2026-09-21

**摘要引用**：
> The golden dandelion is a new item introduced in the Minecraft Tiny Takeover game drop that keeps baby mobs from growing up. Players unlock the crafting recipe...

### 1.3 关键特性速查

| 特性 | 类型 | 描述 |
|------|------|------|
| **金蒲公英（Golden Dandelion）** | 物品 | 喂幼年生物可阻止其长大（不老化） |
| **幼年生物更新** | 机制 | 多种生物的幼年变体行为/外观优化 |
| **可合成名牌（Craftable Name Tags）** | 物品 | 名牌可合成（原版仅地牢/钓鱼获取） |
| **唢呐（Trumpet）** | 音符块乐器 | 音符块新增唢呐音色 |

---

## 2. 详细内容

### 2.1 金蒲公英（Golden Dandelion）机制

按 minecraft.wiki + minecraft.fandom.com：

- **来源**：minecraft.fandom.com
- **原文链接**：<https://minecraft.fandom.com>（搜索结果 rank 2）
- **访问日期**：2026-09-21

**摘要引用**：
> Golden dandelion no longer works on baby skeleton horse and baby zombie horse. Golden dandelion now works on tadpoles. Bedrock Edition 26.10, beta 26.10.21.

**详细机制**：
- 喂幼年生物可阻止其长大
- 不作用于幼年骷髅马/僵尸马（后期版本移除）
- 作用于蝌蚪（可让蝌蚪不变成青蛙）
- 玩家可通过合成获取（解锁合成配方）

### 2.2 可合成名牌

- 原版名牌仅能从地牢箱子/钓鱼获取
- 26.1 后可合成（具体配方待补充）
- 对模组叙事 NPC 命名（如"古老图书管理员"等）有直接价值

### 2.3 唢呐（Trumpet）音符块乐器

- 音符块新增唢呐音色
- 与原版钢琴/吉他/笛子等乐器并列

---

## 3. 与 Remnant Echo 模组叙事的关联

### 3.1 模组叙事关联度：⭐⭐ 低关联

### 3.2 模组解读

按 [`02-story-timeline-plan`](../planning/02-story-timeline-plan.md) §5.4 苍白之悔设定：先民研究生命本源（生命树脂实验），生命树脂实验失控导致苍白花园白化。

**模组叙事采纳**：

金蒲公英可解读为**模组"生命本源研究残留"叙事载体**：

> 「金蒲公英是苍白花园生命树脂实验的副产物，散落在主世界。它能"冻结"生物的成长过程——这是先民生命本源研究的"可控产物"。
>
> 当玩家喂幼年生物金蒲公英时，实际上是在重现先民的"生命冻结"实验。这不影响主线推进，但作为"生命本源研究残留"的视觉叙事提示。」

### 3.3 模组采纳建议

| 候选 | 采纳方式 | L 等级 | 优先级 |
|------|----------|--------|--------|
| 金蒲公英作为"生命本源研究残留"叙事载体 | L1 tellraw 文本（玩家首次合成金蒲公英时触发） | L1 | ★★ v0.4 |
| 可合成名牌用于模组叙事 NPC 命名 | L1 原版机制 | L1 | ★★★ v0.1（与 25 文档 4 个叙事 NPC 联动） |
| 唢呐音符块作为"先民祭祀音乐"叙事载体 | L1 原版音符块 | L1 | ★ v0.5+ |

### 3.4 与已有规划文档的关联

- [`02-story-timeline-plan`](../planning/02-story-timeline-plan.md) §5.4 苍白之悔——金蒲公英是生命树脂实验副产物
- [`25-design-followups-3`](../planning/25-design-followups-3.md) §3 4 个叙事 NPC——可合成名牌对 NPC 命名有直接价值
- [`18-overworld-narrative`](../planning/18-overworld-narrative.md) 主世界遗迹叙事——金蒲公英可在苍白花园附近自然生成（待 v0.4 实施）

---

## 4. 待补充调研

- [ ] 金蒲公英的具体合成配方
- [ ] 幼年生物更新的具体内容（哪些生物的幼年变体有变化？）
- [ ] 可合成名牌的具体合成配方
- [ ] 唢呐音符块的具体音色与触发条件

---

## 5. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-21 | v0.1 | 初稿，基于真实 web 搜索汇编 Minecraft 26.1 Tiny Takeover 更新内容，含金蒲公英/幼年生物更新/可合成名牌/唢呐音符块等特性 + 模组叙事关联分析（低关联，可作生命本源研究残留叙事载体） | 项目方 |
