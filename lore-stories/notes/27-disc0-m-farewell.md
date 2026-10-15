# 0 号唱片 · M. 遗言（9 段完整文本）

> 本文件是 **Remnant Echo 模组真结局的核心文本**——0 号唱片播放时的 M. 遗言 9 段。
>
> **状态**：🟢 完成 v0.6
> **对应主线节点**：M10 真结局
> **关联章节**：[`20-end-narrative`](../../planning/20-end-narrative.md) §14.2 · [`29-story-outline`](../../planning/29-story-outline.md) M10

---

## 1. 基本信息

| 属性 | 值 |
|------|-----|
| **物品** | 0 号唱片（`remnant:music_disc_0`，L3 自定义，按 [`10-custom-items-registry`](../../planning/10-custom-items-registry.md) §2.3） |
| **触发方式** | 玩家将 0 号唱片放入唱片机 |
| **配乐** | L3 自创配乐 `M.'s Farewell`（基于 C418 ambient 风格衍生，按 [`26-music-scenario-catalog`](../../planning/26-music-scenario-catalog.md) §10.2） |
| **粒子** | L3 自定义粒子 `m_farewell`（金蓝色，基于 end_rod+enchant 衍生，按 [`24-design-followups-2`](../../planning/24-design-followups-2.md) §Q18） |
| **文本** | 9 段 tellraw 依次显示（每段间隔 15 秒） |
| **总时长** | 约 2 分 15 秒 |

---

## 2. M. 遗言完整文本（zh_cn）

### 第 1 段（播放后 0 秒）

> 他们不是英雄，不是叛徒，不是怪物。
> 他们只是一群完成任务的士兵，在任务完成后发现……

### 第 2 段（播放后 15 秒）

> 总部已经不在了。

### 第 3 段（播放后 30 秒）

> 你走过的每一座遗迹，都是他们建造的。
> 要塞是他们的军事中心。
> 废弃矿井是他们的运输网。
> 沙漠神殿是他们的祭祀所。
> 试炼密室是他们的考场。

### 第 4 段（播放后 45 秒）

> 你击败的每一个Boss，都是他们留下的。
> 凋灵是他们以为自己能控制的灵魂能量。
> 监守者是他们以为自己能控制的幽匿。
> 末影龙是他们留下的守门人。

### 第 5 段（播放后 60 秒）

> 你遇到的每一个种族，都是他们的后裔。
> 村民接受了失败。
> 猪灵重建了文明。
> 灾厄村民拒绝了失败。
> 末影人——

### 第 6 段（播放后 75 秒）

> 末影人不是怪物。
> 他们是被遗忘的士兵。
> 他们完成了任务——等待接应。
> 但接应从未到来。
> 因为总部已经不在了。

### 第 7 段（播放后 90 秒）

> 我叫 M.。
> 我曾经叫 C.。
> 我在末地等了太久。
> 青金石保住了我的灵魂——
> 但灵魂保不住记忆。
> 我忘记了我是谁。
> 只记得一个词——Memory。
> 所以我叫 M.。

### 第 8 段（播放后 105 秒）

> 但你不一样。
> 你不是他们的后裔。你是局外人。
> 你用局外人的视角，走完了他们走过的路。
> 你看到了他们的成功——三界同源的遗迹。
> 你看到了他们的失败——三大灾变的废墟。
> 你看到了他们的后裔——各自演化的种族。

### 第 9 段（播放后 120 秒）

> 现在你知道了一切。
> 你不再是局外人。
> 你是继承者。
>
> 这个世界，现在交给你了。
>
> —— M.（曾经的 C.）

---

## 3. M. 遗言完整文本（en_us）

### Paragraph 1 (0s)

> They were not heroes, not traitors, not monsters.
> They were just soldiers who completed their mission, and after the mission was done, they discovered...

### Paragraph 2 (15s)

> Headquarters was no longer there.

### Paragraph 3 (30s)

> Every ruin you walked through, they built.
> The stronghold was their military center.
> The mineshaft was their transport network.
> The desert temple was their place of worship.
> The trial chamber was their examination hall.

### Paragraph 4 (45s)

> Every boss you defeated, they left behind.
> The Wither was the soul energy they thought they could control.
> The Warden was the sculk they thought they could control.
> The Ender Dragon was the gatekeeper they left behind.

### Paragraph 5 (60s)

> Every race you encountered, they are their descendants.
> The villagers accepted failure.
> The piglins rebuilt civilization.
> The illagers refused failure.
> The endermen —

### Paragraph 6 (75s)

> The endermen are not monsters.
> They are forgotten soldiers.
> They completed their mission — wait for relief.
> But relief never came.
> Because headquarters was no longer there.

### Paragraph 7 (90s)

> My name is M.
> I was once called C.
> I waited too long in the End.
> Lapis lazuli preserved my soul —
> but it couldn't preserve memory.
> I forgot who I was.
> I only remembered one word — Memory.
> So I am M.

### Paragraph 8 (105s)

> But you are different.
> You are not their descendant. You are an outsider.
> You walked the path they walked, with an outsider's eyes.
> You saw their successes — the ruins of a shared origin across three dimensions.
> You saw their failures — the wastelands of three cataclysms.
> You saw their descendants — races evolved in their own ways.

### Paragraph 9 (120s)

> Now you know everything.
> You are no longer an outsider.
> You are the successor.
>
> This world is now yours.
>
> — M. (formerly C.)

---

## 4. 触发机制

```mcfunction
# data/remnant/functions/lore/on_disc0_play.mcfunction

# 视觉：金蓝色粒子从唱片机扩散（L3 自定义 m_farewell 粒子）
particle remnant:m_farewell ~ ~1 ~ 1 1 1 0 30

# 听觉：L3 自创配乐 m_farewell（基于 C418 ambient 风格）
playsound remnant:music.m_farewell master @s ~ ~ ~ 0.8 1

# 微动作 tellraw（M. 遗言 9 段，按 15 秒间隔）
tellraw @s {"text":"他们不是英雄，不是叛徒，不是怪物。","color":"gray","italic":true}
tellraw @s {"text":"他们只是一群完成任务的士兵，在任务完成后发现……","color":"gray","italic":true}
schedule function remnant:lore/disc0_paragraph_2 300t
schedule function remnant:lore/disc0_paragraph_3 600t
schedule function remnant:lore/disc0_paragraph_4 900t
schedule function remnant:lore/disc0_paragraph_5 1200t
schedule function remnant:lore/disc0_paragraph_6 1500t
schedule function remnant:lore/disc0_paragraph_7 1800t
schedule function remnant:lore/disc0_paragraph_8 2100t
schedule function remnant:lore/disc0_paragraph_9 2400t

# 第 9 段后触发真结局 advancement
schedule function remnant:lore/disc0_finale 2700t
```

```mcfunction
# data/remnant/functions/lore/disc0_finale.mcfunction
# 触发 End Poem 重新解读+真结局 advancement
advancement grant @s only remnant:lore/true_ending
tellraw @s {"text":"","extra":[{"text":"真结局已达成。","color":"gold","bold":true}]}
tellraw @s {"text":"","extra":[{"text":"你不再是局外人。你是继承者。","color":"aqua","italic":true}]}
```

---

## 5. 模组叙事意义

- **模组叙事的最高潮**——M. 遗言 9 段涵盖了模组全部叙事内容（遗迹/Boss/种族/灾变/真相/玩家角色）
- "他们不是英雄，不是叛徒，不是怪物。他们只是一群完成任务的士兵"——模组对先民文明的核心评价
- "末影人不是怪物。他们是被遗忘的士兵"——模组对原版末影人留白的最深刻解读（按 [`20-end-narrative`](../../planning/20-end-narrative.md) §10）
- "你不再是局外人。你是继承者"——玩家角色从"局外人"觉醒为"继承者"的转折点
- "这个世界，现在交给你了"——开放式结尾，玩家完成真结局后继续探索

---

## 6. 与已有规划文档的关联

- [`20-end-narrative`](../../planning/20-end-narrative.md) §14.2 M. 遗言——本笔记是其完整文本
- [`10-custom-items-registry`](../../planning/10-custom-items-registry.md) §2.3 0 号唱片 L3 自定义——本笔记是其触发内容
- [`26-music-scenario-catalog`](../../planning/26-music-scenario-catalog.md) §10.2 0 号唱片播放——本笔记是其听觉+文本部分
- [`12-visual-audio-microaction`](../../17-lore-extensions/12-visual-audio-microaction.md) §6.3 三位一体设计——本笔记是其 M10 真结局实现
- [`29-story-outline`](../../planning/29-story-outline.md) M10 真结局——本笔记是其核心交付

---

## 7. 修订历史

| 日期 | 版本 | 修订内容 |
|------|------|----------|
| 2026-09-21 | v0.1 | 初稿，按 [`20-end-narrative`](../../planning/20-end-narrative.md) §14.2 扩展为完整 9 段 M. 遗言，含 zh_cn/en_us 双语文本+触发机制+模组叙事意义 | 项目方 |
