# Minecraft 26.3 · Wilderness Bound 荒野之缚

> 本文件属于 **Remnant Echo 模组资料汇编** 的新版本更新章节（`16-version-updates/`）。
> 所有内容均基于真实 web 搜索（2026-09-21 完成），URL 与发布日期经核实。
>
> **资料权威性**：★★★★★（Minecraft 官方/Wiki 叙事，P1 级）
> **版本**：Java Edition 26.3 / Bedrock Edition 26.30
> **发布日期**：2026-09-15
> **名称**：Wilderness Bound（荒野之缚）

---

## 1. 版本概述

### 1.1 官方公告

- **来源**：minecraft.net
- **原文链接**：<https://www.minecraft.net/en-us/article/minecraft-java-edition-26-3>
- **发布日期**：2026-09-15
- **搜索关键词**：`Minecraft 1.26.3 update tent hay bed patch notes`（搜索结果 rank 1）
- **访问日期**：2026-09-21

**摘要引用**：
> Minecraft Java Edition 26.3：Seek out abandoned camps, build outposts among the poplar trees, sleep under the stars on straw beds, and share campfire stories atop cushions.

### 1.2 minecraft.wiki 条目

- **来源**：minecraft.wiki
- **原文链接**：<https://minecraft.wiki/w/Wilderness_Bound>
- **访问日期**：2026-09-21

**摘要引用**：
> Wilderness Bound 是 Minecraft 26.3 的 game drop，主要新增：
> - 干草床（Straw Bed）：一种新型床，可用于不改变出生点睡觉；4 个干草床可用 3 个干草块合成；可堆叠
> - 废弃营地（Abandoned Camp）：可在主世界任意群系生成的结构，包含帐篷+干草床+箱/桶+营火+铜灯笼

### 1.3 关键特性速查

| 特性 | 类型 | 描述 |
|------|------|------|
| **帐篷（Tent）** | 结构 | 由羊毛楼梯构成的帐篷形状，含营火+干草床+箱/桶+铜灯笼 |
| **干草床（Straw Bed）** | 物品 | 不改变出生点的临时床，可堆叠，3 干草块合成 |
| **坐垫（Cushion）** | 方块 | 可坐下的方块，多人可坐 |
| **废弃营地（Abandoned Camp）** | 结构 | 主世界任意群系生成的新结构 |
| **斑点群系（Dappled）** | 群系 | 新生物群系 |
| **杨树（Poplar）** | 植物 | 新树种 |

---

## 2. 详细内容

### 2.1 废弃营地（Abandoned Camp）结构

按 thebiglead.com 与 bisecthosting.com 的解析：

- **来源**：thebiglead.com + bisecthosting.com
- **原文链接**：<https://www.thebiglead.com/minecraft-26-3-wilderness-bound-patch-notes> + <https://www.bisecthosting.com/blog/minecraft-26-3-release-date-patch-notes-more>
- **访问日期**：2026-09-21

**摘要引用**：
> This structure can spawn in just about any overworld biome, spawning a tent with a straw bed and a few barrels/chests in it.
> It always contains a tent made of wool stairs, barrels or chests for loot, a copper lantern, and a campfire. The straw bed is not placed immediately after...

### 2.2 干草床（Straw Bed）机制

按 minecraft.wiki：

- 4 个干草床可用 3 个干草块合成
- 可用于睡觉，**不改变出生点**
- 可堆叠（不像普通床不能堆叠）
- 可在废弃营地中自然生成

### 2.3 坐垫（Cushion）

按 youtube.com 视频解析：

- 可坐下的方块
- 多人可同时坐下（适合多人服务器营火场景）
- 可与营火搭配形成"营火故事"场景

---

## 3. 与 Remnant Echo 模组叙事的关联

### 3.1 模组叙事关联度：⭐⭐⭐ 中关联

### 3.2 模组解读

按 [`02-story-timeline-plan`](../planning/02-story-timeline-plan.md) §5.5 大分裂设定："三界据点荒废，族群各自演化"——村民、流浪商人、灾厄村民在大分裂后散布于主世界。

**模组叙事采纳**：

废弃营地可解读为**模组"大分裂后流浪者遗迹"叙事载体**：

> 「大分裂后，先民后裔在荒野中建立的临时营地。村民迁徙时会搭帐篷过夜，流浪商人羊驼队伍会在营地补给，灾厄村民分支也会在黑森林边缘扎营。
>
> 随着时间流逝，许多营地被废弃，干草床、营火、铜灯笼成为今日玩家发现的"废弃营地"结构。
>
> 这些营地的箱子中残留着流浪者的物资——可能是先民笔记的副本，或是大分裂期撤离主世界时携带的少量物资。」

### 3.3 模组采纳建议

| 候选 | 采纳方式 | L 等级 | 优先级 |
|------|----------|--------|--------|
| 在废弃营地 loot 表追加笔记 #16（航海者清单） | L1 原版 loot 表追加 written_book | L1 | ★★★ v0.2 |
| 在废弃营地触发 advancement，tellraw 显示流浪者叙事 | L1 advancement + tellraw | L1 | ★★★ v0.2 |
| 干草床作为模组"不固定出生点睡觉"叙事的视觉提示 | L1 原版机制 | L1 | ★★ v0.3 |
| 坐垫+营火场景触发"流浪者围坐叙事"tellraw | L2 多人场景触发 | L2 | ★★ v0.5+ |

### 3.4 与已有规划文档的关联

- [`02-story-timeline-plan`](../planning/02-story-timeline-plan.md) §5.5 大分裂——废弃营地是大分裂后流浪者遗迹
- [`18-overworld-narrative`](../planning/18-overworld-narrative.md) 主世界遗迹叙事矩阵——废弃营地作为新遗迹类型补充
- [`09-village-loot-extension`](../planning/09-village-loot-extension.md) loot 表扩展模式——废弃营地 loot 表采用相同 L1 模式

---

## 4. 待补充调研

- [ ] 官方 patch notes 完整 URL（已找到 minecraft.net 文章，待整理完整特性清单）
- [ ] 帐篷的具体构成（羊毛颜色变体？是否含特殊方块？）
- [ ] 斑点群系（Dappled）的具体内容（含哪些植物/动物？）
- [ ] 杨树（Poplar）的木材属性（与原版橡树/白桦的差异）

---

## 5. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-21 | v0.1 | 初稿，基于真实 web 搜索汇编 Minecraft 26.3 Wilderness Bound 更新内容，含废弃营地/干草床/坐垫/斑点群系/杨树等特性 + 模组叙事关联分析（中关联，可作大分裂后流浪者遗迹叙事载体） | 项目方 |
