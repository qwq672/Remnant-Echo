# 笔记 #2 · 祭祀记录

> 本文件属于 **Remnant Echo 模组资料汇编** 的完整笔记内容章节（`lore-stories/notes/`）。
> 笔记 #2 是模组主世界考古阶段第二份笔记，玩家在沙漠神殿拾取。
>
> **资料优先级**：P1（基于 [`09-village-loot-extension`](../../planning/09-village-loot-extension.md) + [`18-overworld-narrative`](../../planning/18-overworld-narrative.md) 整理）
> **汇编日期**：2026-09-21
> **状态**：🟢 完成 v0.2
> **对应主线节点**：M2 主世界考古

---

## 1. 笔记基本信息

| 属性 | 值 |
|------|-----|
| **笔记编号** | #2 |
| **物品 ID** | `remnant:tattered_note`（同笔记 #1） |
| **来源结构** | 沙漠神殿箱子（`chests/desert_pyramid`，10% 概率） |
| **触发方式** | 玩家拾取笔记后触发 advancement `remnant:lore/note_2` |
| **对应主题** | 祭祀信仰——先民鼎盛期的信仰体系 |

---

## 2. 笔记内容（zh_cn）

### 2.1 完整文本

> 我们在这里埋下了第一份祭品。
>
> 黄金是给太阳的。
> 钻石是给深处的。
> 青金石是给灵魂的。
>
> 但神没有回答。
> 神从来不回答。
>
> —— 沙漠神殿祭祀记录

### 2.2 微动作 tellraw

按 [`12-visual-audio-microaction`](../../17-lore-extensions/12-visual-audio-microaction.md) §3.2 视觉帧设计：

```mcfunction
# data/remnant/functions/lore/on_note2_pickup.mcfunction

# 视觉：沙漠神殿的祭祀氛围粒子
particle minecraft:enchant ~ ~1 ~ 0.5 0.5 0.5 0 10
particle minecraft:smoke ~ ~1 ~ 0.3 0.3 0.3 0 5

# 听觉：mellohi 配乐（祭祀/庆典主题）
playsound minecraft:music_disc_mellohi master @s ~ ~ ~ 0.4 1

# 微动作 tellraw
tellraw @s {"text":"你打开沙漠神殿的箱子，发现一份泛黄的祭祀记录。","color":"gray","italic":true}
tellraw @s {"text":"黄金给太阳，钻石给深处，青金石给灵魂——但神从来不回答。","color":"gray","italic":true}
tellraw @s {"text":"","extra":[{"text":"线索书第 1 章补充：祭祀信仰","color":"gold"}]}

advancement grant @s only remnant:lore/note_2
```

### 2.3 文学化展开

> 沙漠的风吹过神殿的裂隙，将沙粒送入祭祀室。
>
> 祭司站在 4 个彩色陶罐前，手中握着最后一份黄金——这是给太阳的祭品。
>
> 他抬头看向神殿顶部的开口，阳光如金线般洒下。
>
> "神啊，如果你在听，请给我们一个征兆。"
>
> 但风只是吹过，沙只是落下，太阳只是燃烧。
>
> 神没有回答。神从来不回答。
>
> 祭司将黄金放入陶罐，封上盖子，走出神殿。
>
> 他不知道，千年之后，会有一个局外人打开这个陶罐，发现这份记录——以及那份从未被神接受的黄金。

---

## 3. 笔记内容（en_us）

> We buried the first offering here.
>
> Gold for the sun.
> Diamond for the depths.
> Lapis lazuli for the soul.
>
> But the gods did not answer.
> The gods never answer.
>
> — Desert Temple Sacrifice Record

---

## 4. 模组叙事意义

- 揭示先民鼎盛期的"祭祀信仰体系"——黄金（太阳/维度穿行）+钻石（深处/红石机械）+青金石（灵魂/灵魂能量）三色对应模组四色光谱中的三个
- "神没有回答"暗示先民从鼎盛期就对自己的信仰产生怀疑——这是后续灾变的伏笔
- 沙漠神殿的 4 个彩色陶罐+TNT 陷阱被模组解读为"防止外人盗掘祭祀品"的简易红石机械（按 [`18-overworld-narrative`](../../planning/18-overworld-narrative.md) §2.1）

---

## 5. 与已有规划文档的关联

- [`09-village-loot-extension`](../../planning/09-village-loot-extension.md) §3.2 笔记 #2 内容设计——本笔记是其完整实现
- [`18-overworld-narrative`](../../planning/18-overworld-narrative.md) §2.1 沙漠神殿=地方祭祀与仓储——本笔记是其叙事文本
- [`15-netherite-enchantment-essence`](../../planning/15-netherite-enchantment-essence.md) §3 四色光谱——本笔记的三色对应
- [`26-music-scenario-catalog`](../../planning/26-music-scenario-catalog.md) §4.1 沙漠神殿配乐——本笔记是其听觉部分

---

## 6. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-21 | v0.1 | 初稿，按 [`09-village-loot-extension`](../../planning/09-village-loot-extension.md) §3.2 + [`18-overworld-narrative`](../../planning/18-overworld-narrative.md) §2.1 整理笔记 #2 完整内容，含 zh_cn/en_us 文本+微动作 tellraw+文学化展开+模组叙事意义 | 项目方 |
