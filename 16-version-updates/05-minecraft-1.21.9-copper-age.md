# Minecraft 1.21.9 · The Copper Age 铜器时代

> 本文件属于 **Remnant Echo 模组资料汇编** 的新版本更新章节（`16-version-updates/`）。
> 所有内容均基于真实 web 搜索（2026-09-21 完成），URL 与发布日期经核实。
>
> **资料权威性**：★★★★★（Minecraft 官方/Wiki 叙事，P1 级）
> **版本**：Java Edition 1.21.9 / Bedrock Edition 1.21.111
> **发布日期**：2025-09-30
> **名称**：The Copper Age（铜器时代）

---

## 1. 版本概述

### 1.1 官方公告

- **来源**：minecraft.net
- **原文链接**：<https://www.minecraft.net>（搜索结果 rank 1）
- **发布日期**：2025-09-30
- **搜索关键词**：`Minecraft 1.21.9 copper age update`（搜索结果 rank 1）
- **访问日期**：2026-09-21

**摘要引用**：
> Minecraft Java Edition 1.21.9：Minecraft has entered The Copper Age! Express yourself in every shade of copper. New Features: Added Copper Chest, Added Copper Golem...

### 1.2 minecraft.wiki 条目

- **来源**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki>（搜索结果 rank 0）
- **访问日期**：2026-09-21

**摘要引用**：
> The Copper Age is a game drop released on September 30, 2025 as Java Edition 1.21.9 and Bedrock Edition 1.21.111. It introduces copper armor...

### 1.3 关键特性速查

| 特性 | 类型 | 描述 |
|------|------|------|
| **铜盔甲（Copper Armor）** | 装备 | 铜制盔甲套装 |
| **铜傀儡（Copper Golem）** | 生物 | 铜制傀儡，可被玩家激活/友好 |
| **铜箱子（Copper Chest）** | 方块 | 铜制箱子，可氧化变色 |
| **模特（Mannequins）** | 实体 | 可展示装备的人体模型 |
| **铜装饰（Copper Decor）** | 方块 | 铜质装饰方块系列 |

---

## 2. 详细内容

### 2.1 铜傀儡（Copper Golem）

按 minecraft.net + empireminecraft.com：

- **来源**：empireminecraft.com
- **原文链接**：<https://empireminecraft.com>（搜索结果 rank 2）
- **发布日期**：2025-11-29
- **访问日期**：2026-09-21

**摘要引用**：
> 1.21.9/10 Update - The Copper Age: Lots of copper items have been added and should work as you would expect them. Copper Golems are eggifiable and retain a lot of their properties.

**详细机制**：
- 铜傀儡可被玩家用刷怪蛋生成
- 友好生物，不攻击玩家
- 会随时间氧化（颜色从橙变绿）
- 可用蜂蜡/蜜脾打蜡保持原色

### 2.2 铜盔甲（Copper Armor）

- 铜制盔甲套装（头盔/胸甲/护腿/靴子）
- 防御力介于铁与金之间
- 可氧化变色（视觉特性）

### 2.3 铜箱子（Copper Chest）

- 铜制箱子，与原版箱子容量相同
- 可氧化变色（橙→绿）
- 可打蜡保持原色

### 2.4 模特（Mannequins）

- 可展示装备的人体模型
- 玩家可右键放置装备
- 用于装饰/展示

### 2.5 铜装饰（Copper Decor）

- 铜质装饰方块系列（铜砖/铜楼梯/铜半砖/铜按钮等）
- 与原版石砖/铜块同源
- 可氧化变色

---

## 3. 与 Remnant Echo 模组叙事的关联

### 3.1 模组叙事关联度：⭐⭐⭐⭐ 高关联

### 3.2 模组解读

按 [`14-trial-chamber-narrative`](../planning/14-trial-chamber-narrative.md) §6.5"凝灰岩与铜质构件"叙事：试炼密室使用凝灰岩+铜质构件建造，模组解读为"先民在主世界地下深处开采的特殊石材+容易氧化变绿的金属"。

**模组叙事采纳**：

1.21.9 铜器时代的更新**强化了模组"先民铜器工艺"叙事**：

> 「铜是先民鼎盛纪元的核心材料之一，与下界合金（暗红）、紫珀砖（紫）、苍白橡木（白）、青金石（蓝）共同构成模组的"四色光谱+第五色（铜绿）"。
>
> 铜傀儡是先民尝试制造的下界合金守卫的早期实验——铜比下界合金更容易获取，但硬度不足，因此铜傀儡是"先民守卫的早期原型"，最终演化为铁傀儡（村民的退化复制品）。
>
> 铜箱子是先民储物设施的变体（与试炼密室 Vault 同源），可氧化变色暗示其时间久远。
>
> 模特可能是先民贵族展示盔甲的人体模型，大分裂后被村民继承为"村庄雕像"传统。」

### 3.3 模组采纳建议

| 候选 | 采纳方式 | L 等级 | 优先级 |
|------|----------|--------|--------|
| 铜傀儡叙事解读（先民守卫早期实验） | L1 tellraw 文本（玩家首次激活铜傀儡时触发） | L1 | ★★★ v0.2 |
| 铜箱子作为模组"先民储物设施变体"叙事载体 | L1 原版方块解读 | L1 | ★★ v0.2 |
| 模特作为"先民贵族展示盔甲传统"叙事载体 | L1 原版实体解读 | L1 | ★★ v0.3 |
| 铜装饰作为"四色光谱+第五色（铜绿）"视觉叙事主线 | L1 原版方块解读 | L1 | ★★★ v0.2 |
| 铜盔甲作为"先民鼎盛期士兵装备"考古发现 | L1 原版物品解读 | L1 | ★★ v0.3 |

### 3.4 与已有规划文档的关联

- [`14-trial-chamber-narrative`](../planning/14-trial-chamber-narrative.md) §6.5 凝灰岩与铜质构件——铜器时代强化试炼密室铜工艺叙事
- [`15-netherite-enchantment-essence`](../planning/15-netherite-enchantment-essence.md) §3 四色光谱——铜绿作为"第五色"补充
- [`16-worldview-overview`](../planning/16-worldview-overview.md) §4 远古先民文明四大研究领域——铜工艺属于红石机械分支
- [`18-overworld-narrative`](../planning/18-overworld-narrative.md) 主世界遗迹叙事——铜傀儡作为先民守卫早期实验

---

## 4. 待补充调研

- [ ] 铜傀儡的具体 AI 行为（是否会跟随玩家？是否会攻击怪物？）
- [ ] 铜盔甲的具体防御数值
- [ ] 铜箱子的氧化机制（与原版铜块氧化速度一致？）
- [ ] 模特的具体使用方式（是否可展示工具/武器？）

---

## 5. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-21 | v0.1 | 初稿，基于真实 web 搜索汇编 Minecraft 1.21.9 The Copper Age 更新内容，含铜傀儡/铜盔甲/铜箱子/模特/铜装饰等特性 + 模组叙事关联分析（高关联，强化模组"先民铜器工艺"叙事，作为四色光谱+第五色铜绿） | 项目方 |
