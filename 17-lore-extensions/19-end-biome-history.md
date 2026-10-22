# 19 · 末地群系开发史 · End Biome History

> 本文件属于 **Remnant Echo 模组资料汇编** 的剧情扩展章节（`17-lore-extensions/`）。
> 完整收录 The End 维度所有群系的开发历史、加入版本、设计演变、与模组叙事的关联。
>
> **资料优先级**：P1（minecraft.wiki 官方）+ P1（Mojang 开发历史）
> **汇编日期**：2026-10-19
> **状态**：🟢 完成（基于已收集的资料，含 Sky Dimension 转化史 + 1.9 End Update + 1.13 群系重命名）

---

## 1. 项目方问题

> "末地群系开发史"

本汇编系统整理末地所有群系的开发历史，作为模组"末地叙事"（[`planning/20-end-narrative.md`](../planning/20-end-narrative.md)）的群系层背景。

---

## 2. 末地群系完整列表

### 2.1 当前末地群系（Java Edition 1.21+）

| 群系 ID | 中文名 | 加入版本 | 特征 |
|---------|--------|----------|------|
| `minecraft:end_barrens` | 末地荒原 | 1.9 (15w31a) | 虚空岛屿之间的空白区域，无方块生成 |
| `minecraft:end_highlands` | 末地高地 | 1.9 (15w31a) | 含末地城（End City）+紫颂果森林的高地岛屿 |
| `minecraft:end_midlands` | 末地中部 | 1.9 (15w31a) | 中等高度岛屿，过渡区域 |
| `minecraft:small_end_islands` | 小末地岛屿 | 1.9 (15w31a) | 小型岛屿之间的过渡群系 |
| `minecraft:end_spike` / `minecraft:ender_giant_spikes` | 末地尖刺 | 1.9 (15w31a) → 1.13 重命名 | 中央岛屿周围的 obsidian pillars 区域 |

### 2.2 已废弃/历史群系 ID

| 旧群系 ID | 时间范围 | 当前状态 |
|-----------|----------|----------|
| `minecraft:sky` | 1.0 ~ 1.13 (18w06a 前) | 1.13 后改为 `minecraft:end_*` 系列——**Sky Dimension 的最后遗产** |
| `minecraft:sky_islands_high` | 18w06a 开发期 | 1.13.1 (18w06a 后) 改为 `minecraft:end_highlands` |
| `minecraft:sky_islands_medium` | 18w06a 开发期 | 改为 `minecraft:end_midlands` |
| `minecraft:sky_islands_low` | 18w06a 开发期 | 改为 `minecraft:end_barrens` |
| `minecraft:small_end_islands` | 18w06a 开发期 | 保留 |

---

## 3. 末地开发完整时间线

### 3.1 Sky Dimension 时期（2011）

> 详见 [`15-cut-unused-features.md`](./15-cut-unused-features.md) §5

- **2011-05-19**：Notch 在 Twitter 正式确认 Sky Dimension
- **2011-10-12**：Jeb 确认 Sky Dimension 改造成 The End
- **2011-11-18**：Minecraft 1.0 发布，**末地首次实装**——只有中央岛屿 + 末影龙 + 末影人

### 3.2 早期末地（1.0 ~ 1.8，2011-2014）

**1.0 末地特征**：
- 单一群系 `minecraft:sky`（Sky Dimension 的最后遗产）
- 只有中央岛屿
- obsidian pillars（黑曜石柱）+ End Crystals（末影水晶）
- 末影龙 + 末影人
- 无外岛——只有击败末影龙后通过末影珍珠传送才能到达
- **黑暗虚空**——无太阳/月亮/云

### 3.3 末地扩展（1.9 Combat Update，2016）

**1.9 (15w31a) 重大更新**：
- **末地完全重做**
- 添加 5 个群系：
  1. `minecraft:end_barrens`
  2. `minecraft:end_highlands`
  3. `minecraft:end_midlands`
  4. `minecraft:small_end_islands`
  5. `minecraft:end_spike`（中央岛屿周围）
- 添加 **末地城（End City）**——位于 `end_highlands` 群系
- 添加 **末地船（End Ship）**——末地城的附属结构
- 添加 **潜影贝（Shulker）**——末地城守卫
- 添加 **鞘翅（Elytra）**——末地船战利品
- 添加 **紫颂果（Chorus Fruit）** + **紫珀砖（Purpur Block）** + **末地石砖（End Stone Bricks）**
- 添加 **末影珍珠传送**——外岛与中央岛屿间的传送机制
- 添加 **末地重生**——通过 4 个末影水晶复活末影龙

### 3.4 群系 ID 重命名（1.13，2018）

**1.13 (18w06a) The Update Aquatic**：
- 末地群系 ID 全部重命名：
  - `minecraft:sky` → `minecraft:end_*` 系列
  - `minecraft:sky_islands_high` → `minecraft:end_highlands`
  - `minecraft:sky_islands_medium` → `minecraft:end_midlands`
  - `minecraft:sky_islands_low` → `minecraft:end_barrens`
- **Sky Dimension 的最后遗产被彻底清除**——`minecraft:sky` 不再存在
- 但仍可通过 1.16.2 的 `minecraft:floating_islands` 噪声预设恢复 Sky Dimension 概念

### 3.5 现代末地（1.13+）

末地群系结构自 1.13 后基本无变化。后续版本仅添加少量内容：

- **1.13 (18w06a)**：群系 ID 重命名
- **1.14 (2019)**：无末地更新
- **1.16 (2020) Nether Update**：无末地更新
- **1.18 (2021) Caves & Cliffs**：无末地更新（但末地高度限制随主世界增加）
- **1.19 (2022) Wild Update**：无末地更新
- **1.21 (2024) Tricky Trials**：无末地更新
- **1.21.4 (2024-12) Garden Awakens**：无末地更新
- **26.x (2026)**：无末地更新

**模组关联**：模组"末地叙事"基于 1.9 后的末地结构，但保留 `minecraft:sky` 的历史命名作为模组"末地=Sky Dimension 失败版"叙事的原版官方证据。

---

## 4. 末地群系详细解析

### 4.1 End Highlands（末地高地）

**特征**：
- 大型岛屿
- **生成末地城（End City）**——含潜影贝和战利品
- 紫颂果森林常见
- 模组叙事核心——模组"末地殖民军据点"叙事的原版结构资源

### 4.2 End Midlands（末地中部）

**特征**：
- 中等高度岛屿
- 过渡区域——连接高地和小岛屿
- 紫颂果少量生成
- 模组叙事——可作为模组"末地殖民军迁徙路径"叙事

### 4.3 End Barrens（末地荒原）

**特征**：
- 虚空岛屿之间的空白区域
- **无方块生成**——只有虚空
- 玩家需要搭桥或使用末影珍珠穿越
- 模组叙事——可作为模组"末地殖民军迷失的探索者"叙事

### 4.4 Small End Islands（小末地岛屿）

**特征**：
- 小型岛屿之间的过渡群系
- 生成零星小岛
- 玩家需要搭桥穿越
- 模组叙事——模组"末地殖民军散落据点"叙事

### 4.5 End Spike（末地尖刺）

**特征**：
- 中央岛屿周围的区域
- 含 obsidian pillars（黑曜石柱）+ End Crystals（末影水晶）
- 末影龙的栖息地
- 模组叙事——模组"末影龙=守门人"叙事的核心战斗区域

---

## 5. 末地结构完整列表

| 结构 | 加入版本 | 群系 | 备注 |
|------|----------|------|------|
| **Obsidian Pillar（黑曜石柱）** | 1.0 | `end_spike` | 中央岛屿周围 |
| **End Crystal（末影水晶）** | 1.0 | `end_spike` | 在黑曜石柱顶 |
| **Exit Portal（出口传送门）** | 1.0 | 中央岛屿 | 击败末影龙后激活 |
| **End Podium（末影龙栖息基座）** | 1.0 | 中央岛屿 | 末影龙停留点 |
| **End Gateway Portal（末地折跃门）** | 1.9 | 中央岛屿+外岛 | 击败末影龙后生成，传送到外岛 |
| **End City（末地城）** | 1.9 (15w31a) | `end_highlands` | 含潜影贝+战利品 |
| **End Ship（末地船）** | 1.9 (15w31a) | `end_highlands` | 末地城附属，含鞘翅 |
| **Chorus Tree（紫颂果树）** | 1.9 (15w31a) | `end_highlands` + `end_midlands` | 紫颂果来源 |
| **End Portal Frame（末地传送门框架）** | 1.0 → 1.9 完善 | 主世界要塞 | 模组"先民建造"叙事核心 |
| **Exit Portal（出口传送门）** | 1.0 | 末地中央 | 含龙蛋 |

---

## 6. 末地群系与模组叙事关联

### 6.1 模组"末地=Sky Dimension 失败版"叙事

**原版官方证据**：
- `minecraft:sky` 群系 ID 在 1.13 前一直存在——Sky Dimension 的最后遗产
- 末地"虚空岛屿"概念源自 Sky Dimension 的"漂浮岛屿"设计
- Notch 2011-07-30 Twitter 戏谑："How about we just rename the 'far lands' to 'the end' instead? ;D"
- 末影人原名"Farlanders"——边境之地的居民

**模组叙事采纳**：
- 模组"末地=Sky Dimension 失败版"叙事（[`planning/20-end-narrative.md`](../planning/20-end-narrative.md) §5.2）已采纳
- 模组笔记 #25 维度穿行技术报告（晚期版）中 E. 明确"我们曾自称 Farlanders"——基于 Sky Dimension 历史命名

### 6.2 模组"末地城=殖民军据点"叙事

**原版官方证据**：
- 末地城使用紫珀砖（Purpur Block）建造——与主世界石砖工艺同源（社区共识）
- 末地城含潜影贝（Shulker）——形似机械守卫
- 末地船含鞘翅（Elytra）——飞行装备，殖民军的"等待接应的飞船"
- SyntaxMine 理论：末地城=古代建造者殖民地

**模组叙事采纳**：
- 模组"末地殖民军"叙事（[`planning/20-end-narrative.md`](../planning/20-end-narrative.md)）已采纳
- 模组笔记 #23/#24 落款 C.，分别在末地城和末地船触发

### 6.3 模组"末影龙=守门人"叙事

**原版官方证据**：
- 末影龙在中央岛屿栖息——obsidian pillars + End Crystals 治疗
- 击败末影龙后通过末地折跃门传送外岛
- 龙蛋作为唯一战利品——"先民设计的重启种子"
- MatPat 理论：末影龙=先民制造的最终守门人

**模组叙事采纳**：
- 模组"末影龙=守门人"叙事（[`planning/07-boss-narrative-binding.md`](../planning/07-boss-narrative-binding.md) §3.3 + [`planning/20-end-narrative.md`](../planning/20-end-narrative.md)）已采纳

### 6.4 模组"末地孤城"叙事

**模组叙事**：
- 大分裂晚期，末地殖民军被困末地，等待接应无果
- 末地城逐渐荒废，殖民军异化为末影人
- 玩家在末地探索时发现的"末地孤城"——模组笔记 #23/#24 的载体

### 6.5 模组 v0.6+ 真结局——The Sift

**与末地的关系**：
- 末地是 Sky Dimension 的失败版
- The Sift 是 Sky Dimension 的成功版（Mojang 终于完成 14 年前的设想）
- 模组真结局：玩家从末地通过远古城市的 Singer's Portal 进入 The Sift
- 详见 [`17-lore-extensions/18-the-sift-deepdive.md`](./18-the-sift-deepdive.md)

---

## 7. 末地开发关键 Mojang 引用

### 7.1 Notch 关于 Sky Dimension 改名

> "/v/ is petitioning me to change the name from 'Endermen' to 'Farlanders'.
> How about we just rename the 'far lands' to 'the end' instead? ;D"
> – @notch (Markus Persson), July 30, 2011

### 7.2 Jeb 关于 Sky Dimension 转化为末地

> "@JPwanabe It has been rebranded to be The End realm."
> – Jeb, October 12, 2011

### 7.3 Jeb/Dinnerbone 关于 Sky Dimension 不复活

> "@Sims_Doc @Dinnerbone No we don't plan to return the Sky Dimension."
> – Jeb, July 2, 2012

> "@Tyren9 We have no plans to revisit the skylands."
> – Dinnerbone, July 3, 2012

### 7.4 1.13 群系 ID 重命名

- 18w06a 快照：末地群系 ID 从 `minecraft:sky` 和 `minecraft:sky_islands_*` 全部改为 `minecraft:end_*`
- 1.13 正式版：Sky Dimension 的最后遗产被清除

---

## 8. 模组采纳状态总表

### 8.1 完全采纳（作为核心叙事资源）

| 编号 | 末地群系/历史 | 模组采纳形式 |
|------|---------------|--------------|
| E1 | **末地 5 个群系**（highlands/midlands/barrens/small_islands/spike） | 模组笔记 #23/#24/#25/#26 的物理载体——分别在 highlands 末地城+highlands 末地船+中央岛屿+回归传送门旁 |
| E2 | **`minecraft:sky` 历史群系 ID** | 模组"末地=Sky Dimension 失败版"叙事的原版官方证据 |
| E3 | **末地=Notch 戏谑"边境之地改名"** | 模组"末影人=Farlanders"叙事的原版官方命名层背书 |
| E4 | **末地城（End City）** | 模组"末地殖民军据点"叙事的核心结构 |
| E5 | **末地船（End Ship）** | 模组"等待接应的飞船"叙事的核心结构 |
| E6 | **Obsidian Pillar + End Crystal** | 模组"末影龙=守门人"叙事的核心战斗区域 |
| E7 | **End Gateway Portal（末地折跃门）** | 模组"末地探索路径"叙事的传送机制 |
| E8 | **1.13 群系 ID 重命名** | 模组"Sky Dimension 遗产被清除"叙事的原版官方证据 |

### 8.2 部分采纳（参考但不实装）

- 紫颂果森林——仅作为模组"末地殖民军粮食"叙事的视觉资源
- 紫珀砖——仅作为模组"先民石砖工艺同源"叙事的视觉证据

### 8.3 不采纳（仅记录）

- 末地重生机制——仅记录原版机制
- 鞘翅+潜影贝掉落——仅记录原版机制

---

## 9. 与其他规划文档的引用关系

| 引用文档 | 关联章节 |
|----------|----------|
| [`planning/20-end-narrative.md`](../planning/20-end-narrative.md) | §5 末地群系+§13 End Poem 重新解读 |
| [`planning/05-clue-book-system.md`](../planning/05-clue-book-system.md) | 笔记 #23-#26 触发位置——末地各群系 |
| [`planning/07-boss-narrative-binding.md`](../planning/07-boss-narrative-binding.md) | §3.3 末影龙击杀叙事——obsidian pillar 区域 |
| [`17-lore-extensions/15-cut-unused-features.md`](./15-cut-unused-features.md) | §5.2 Sky Dimension + §7.5 Enderman=Farlanders |
| [`17-lore-extensions/18-the-sift-deepdive.md`](./18-the-sift-deepdive.md) | §10 The Sift 进入方式——通过远古城市的 Singer's Portal |

---

## 10. 参考资料

### 10.1 官方资料（P1）

- minecraft.wiki The End：<https://minecraft.wiki/w/The_End>
- minecraft.wiki End City：<https://minecraft.wiki/w/End_City>
- minecraft.wiki End Ship：<https://minecraft.wiki/w/End_Ship>
- minecraft.wiki End Dimension：<https://minecraft.wiki/w/Dimension#End>
- minecraft.wiki Ender Dragon：<https://minecraft.wiki/w/Ender_Dragon>
- minecraft.wiki End Spike：<https://minecraft.wiki/w/End_spike>
- minecraft.wiki Sky dimension：<https://minecraft.wiki/w/Sky_dimension>
- minecraft.wiki Java Edition 1.9：<https://minecraft.wiki/w/Java_Edition_1.9>
- minecraft.wiki Java Edition 18w06a：<https://minecraft.wiki/w/Java_Edition_18w06a>

### 10.2 社区资料（P2）

- SyntaxMine Complete Minecraft Lore Timeline：<https://syntaxmine.com/articles/complete-minecraft-lore-timeline>
- lore.astroworldmc.com The Ancient Builders Theory：<https://lore.astroworldmc.com/ancient-builders-theory>

### 10.3 搜索关键词与调用次数

无新增搜索——本文档基于已收集的资料整理。

---

## 11. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-10-19 | v1.0 | 初次创建——基于已收集资料，完整收录末地 5 个群系+Sky Dimension 转化史+1.9 末地扩展+1.13 群系 ID 重命名+模组叙事关联 | 项目方 |
