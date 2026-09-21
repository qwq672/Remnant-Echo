# Minecraft 1.21.11 · 鹦鹉螺更新

> 本文件属于 **Remnant Echo 模组资料汇编** 的新版本更新章节（`16-version-updates/`）。
> 所有内容均基于真实 web 搜索（2026-09-21 完成），URL 与发布日期经核实。
>
> **资料权威性**：★★★★★（Minecraft 官方/Wiki 叙事，P1 级）
> **版本**：Java Edition 1.21.11
> **名称**：鹦鹉螺更新（项目方命名）

---

## 1. 版本概述

### 1.1 minecraft.wiki 条目

- **来源**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki>（搜索结果 rank 0，"Zombie Nautilus"条目）
- **访问日期**：2026-09-21

**摘要引用**：
> A zombie nautilus is an undead variant of the nautilus that spawns being ridden and controlled by a trident-wielding drowned.

### 1.2 minecraft.fandom.com 条目

- **来源**：minecraft.fandom.com
- **原文链接**：<https://minecraft.fandom.com>（搜索结果 rank 1）
- **访问日期**：2026-09-21

**摘要引用**：
> A zombie nautilus is an undead neutral mob. Are damaged by Instant Health and healed. Camel Husk, Cave Spider, Creaking (requires destroying the creaking heart).

### 1.3 minecraft.net 预览公告

- **来源**：minecraft.net
- **原文链接**：<https://www.minecraft.net>（搜索结果 rank 2，"Minecraft Preview 1.21.130.24"）
- **发布日期**：2025-10-29
- **访问日期**：2026-09-21

**摘要引用**：
> Meet the camel husk for the first time, an undead passive mob that thrives in the desert. Camels no longer sink. Nautilus now has the correct...

### 1.4 关键特性速查

| 特性 | 类型 | 描述 |
|------|------|------|
| **鹦鹉螺（Nautilus）** | 生物 | 原版生物，1.21.11 修复/优化 |
| **僵尸鹦鹉螺（Zombie Nautilus）** | 不死生物 | 鹦鹉螺的不死变体，由三叉戟溺尸骑乘 |
| **骆驼尸壳（Camel Husk）** | 不死被动生物 | 骆驼的不死变体，沙漠群系生成 |
| **焦骸（Charred）** | — | 项目方提及，待补充具体信息 |
| **僵尸马（Zombie Horse）** | 不死生物 | 原版生物，1.21.11 可能优化 |

---

## 2. 详细内容

### 2.1 僵尸鹦鹉螺（Zombie Nautilus）

按 minecraft.wiki + minecraft.fandom.com：

- 鹦鹉螺的不死变体
- 由三叉戟溺尸骑乘控制（类似僵尸骑鸡）
- 不死生物，受到瞬间治疗伤害，瞬间伤害治疗
- 中立生物（除非被攻击）

### 2.2 骆驼尸壳（Camel Husk）

按 minecraft.net 预览公告：

- 骆驼的不死变体
- 被动生物（不主动攻击）
- 在沙漠群系生成
- 骆驼不再沉入水中（1.21.11 修复）

### 2.3 焦骸（Charred）

项目方提及但未在 2026-09-21 搜索中获取到具体信息，待补充调研。

---

## 3. 与 Remnant Echo 模组叙事的关联

### 3.1 模组叙事关联度：⭐⭐ 低关联

### 3.2 模组解读

按 [`02-story-timeline-plan`](../planning/02-story-timeline-plan.md) §5.5 大分裂设定：僵尸猪灵=猪灵进入主世界后的退化形态（维度能量冲突）。

**模组叙事采纳**：

1.21.11 不死变体（僵尸鹦鹉螺+骆驼尸壳）**可强化模组"维度诅咒"叙事**：

> 「大分裂后，原版世界中出现了大量"不死变体"——僵尸猪灵、僵尸鹦鹉螺、骆驼尸壳等。这些都是维度能量冲突的产物——原版生物在跨维度移动时，被维度能量扭曲为不死形态。
>
> 这不是单一现象，而是模组"维度诅咒"叙事的多次印证——先民维度穿行技术的失败，导致后世所有跨维度移动的生物都面临"不死化"风险。」

### 3.3 模组采纳建议

| 候选 | 采纳方式 | L 等级 | 优先级 |
|------|----------|--------|--------|
| 僵尸鹦鹉螺作为"维度诅咒"叙事的补充证据 | L1 tellraw 文本（玩家首次遭遇时触发） | L1 | ★ v0.4 |
| 骆驼尸壳作为"沙漠群系不死变体"叙事载体 | L1 原版生物解读 | L1 | ★ v0.4 |
| 焦骸（待补充信息后评估） | — | — | v0.5 后评估 |

### 3.4 与已有规划文档的关联

- [`02-story-timeline-plan`](../planning/02-story-timeline-plan.md) §5.5 大分裂——不死变体作为维度诅咒叙事
- [`19-nether-narrative`](../planning/19-nether-narrative.md) 僵尸猪灵叙事——僵尸鹦鹉螺+骆驼尸壳是同类"维度诅咒"

---

## 4. 待补充调研

- [ ] 焦骸（Charred）的具体信息（项目方提及，搜索未获取到——可能是中文译名差异，尝试搜索"charred mob minecraft"或"焦骸 minecraft"）
- [ ] 僵尸马（Zombie Horse）在 1.21.11 的具体变化
- [ ] 鹦鹉螺原版生物的具体修复内容

---

## 5. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-21 | v0.1 | 初稿，基于真实 web 搜索汇编 Minecraft 1.21.11 鹦鹉螺更新内容，含僵尸鹦鹉螺/骆驼尸壳/焦骸（待补）/僵尸马等特性 + 模组叙事关联分析（低关联，可作"维度诅咒"叙事补充证据） | 项目方 |
