# Minecraft Live 2026 9月场 · 原版游戏更新资讯

> 本文件属于 **Remnant Echo 模组资料汇编** 的新版本更新章节（`16-version-updates/`）。
> 所有内容均基于真实 web 搜索（2026-09-21 尝试，API 故障，待重试）。
>
> **资料优先级**：P1（minecraft.net 官方）
> **汇编日期**：2026-09-21
> **状态**：🟡 待补充调研（搜索 API 故障，基于项目方提供的信息整理）

---

## 1. 项目方信息

项目方 2026-09-21 提供：

> "几十天前 Minecraft LIVE 2026 9月场已经结束，主要是有关地下城 2 游戏、现实场景及原版游戏更新等，原版游戏的更新包括新的群系冰什么群系来着、the sift（应该是叫筛界）、新的僵尸变种等，建议继续收集新版本相关资讯及资料以同步世界观"

---

## 2. Minecraft Live 2026 9月场概览

### 2.1 已知信息

| 内容 | 状态 | 备注 |
|------|------|------|
| **Minecraft Dungeons 2** | 🟡 待补充调研 | 地下城续作，项目方提及 |
| **现实场景** | 🟡 待补充调研 | 可能是 AR/真人快闪类内容 |
| **冰系群系** | 🟡 待补充调研 | 项目方提及"冰什么群系来着"——可能是冰原扩展或新冰系群系 |
| **The Sift（筛界）** | 🟡 待补充调研 | 项目方提及——可能是新维度/新结构/新群系 |
| **新僵尸变种** | 🟡 待补充调研 | 项目方提及——可能是焦骸之后的下一个僵尸变体 |

### 2.2 待搜索补充

- [ ] Minecraft Live 2026 9月场完整公告
- [ ] 冰系群系的具体名称与特性
- [ ] The Sift（筛界）的官方资料（维度？结构？群系？）
- [ ] 新僵尸变种的具体名称与特性
- [ ] Minecraft Dungeons 2 的官方公告
- [ ] 现实场景的具体内容

---

## 3. 模组叙事预解读（基于项目方信息）

### 3.1 冰系群系

按 [`02-story-timeline-plan`](../planning/02-story-timeline-plan.md) §5.5 大分裂+ [`18-overworld-narrative`](../planning/18-overworld-narrative.md) §3 主世界种族：

> 「冰系群系（待确认名称）可能是先民"维度能量残留"在寒冷环境的具象化区域——与流髑（雪原骷髅变种）+冰元素叙事一致。
>
> 模组预解读：冰系群系是先民维度能量在极寒环境下的"稳定结晶区"——这里的维度能量被低温稳定，形成独特的冰系生物群系。」

### 3.2 The Sift（筛界）

按 [`02-story-timeline-plan`](../planning/02-story-timeline-plan.md) §5.1 鼎盛纪元+ [`17-lore-extensions/05-dimension-origins`](../17-lore-extensions/05-dimension-origins.md)：

> 「The Sift（筛界）——按名称推测可能是"维度筛子"或"维度过滤区"。
>
> 模组预解读：The Sift 是先民维度穿行技术的"过滤层"——在主世界/下界/末地之间的"过渡维度"，用于过滤维度能量。这与模组"先民曾尝试开拓第四维度（Sky Dimension）但失败"叙事呼应。
>
> The Sift 可能是 Sky Dimension 失败后的"残片"——一个未完成的过渡维度。」

### 3.3 新僵尸变种

按 [`17-lore-extensions/01-mob-evolution-history`](../17-lore-extensions/01-mob-evolution-history.md) §6 骷髅家族演变+ [`17-lore-extensions/06-mob-behaviors-explained`](../17-lore-extensions/06-mob-behaviors-explained.md) §3.15 僵尸：

> 「新僵尸变种可能是僵尸在特定群系（如冰系群系）的演化形态——与焦骸（沙漠骷髅变种）/流髑（雪原骷髅变种）的"群系+元素"演化路径一致。
>
> 模组预解读：新僵尸变种是僵尸在冰系群系的"冰化"演化——附加冰元素，与流髑同源但属于僵尸家族而非骷髅家族。」

### 3.4 Minecraft Dungeons 2

按 [`14-official-derivatives`](../14-official-derivatives/) 官方衍生作品汇编：

> 「Minecraft Dungeons 2 是 Minecraft Dungeons 的续作——按模组原则 5"基于官方衍生作品可参考，但以原版为准"，可作为模组叙事的辅助参考。
>
> 待官方公告后，按 [`14-official-derivatives/02-minecraft-dungeons.md`](../14-official-derivatives/02-minecraft-dungeons.md) 整理为新的衍生作资料。」

---

## 4. 模组采纳建议（待官方资料确认后实施）

| 候选 | 采纳方式 | L 等级 | 优先级 |
|------|----------|--------|--------|
| 冰系群系=维度能量在寒冷环境的稳定结晶区 | L1 tellraw 文本（玩家进入冰系群系时触发） | L1 | ★★ v0.5+ 后 |
| The Sift=Sky Dimension 失败后的过渡维度 | L1 tellraw 文本（玩家首次接触 The Sift 时触发） | L1 | ★★ v0.5+ 后 |
| 新僵尸变种=僵尸在冰系群系的冰化演化 | L1 tellraw 文本（玩家首次遭遇时触发） | L1 | ★★ v0.5+ 后 |
| Minecraft Dungeons 2 设定参考 | L1 文档整理（按 [`14-official-derivatives`](../14-official-derivatives/)） | L1 | ★ v1.0 后 |

---

## 5. 待补充调研（API 故障后重试）

- [ ] 搜索 "Minecraft Live 2026 September ice biome frozen update announcement"
- [ ] 搜索 "Minecraft The Sift 筛界 new dimension 2026"
- [ ] 搜索 "Minecraft Live 2026 September new zombie variant"
- [ ] 搜索 "Minecraft Dungeons 2 announcement 2026"
- [ ] 搜索 "Minecraft Live 2026 September vanilla update announcements"

---

## 6. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-21 | v0.1 | 初稿，基于项目方 2026-09-21 提供的 Minecraft Live 2026 9月场信息整理（冰系群系+The Sift 筛界+新僵尸变种+Minecraft Dungeons 2+现实场景），含模组叙事预解读+模组采纳建议；搜索 API 故障，标注待补充调研 | 项目方 |
