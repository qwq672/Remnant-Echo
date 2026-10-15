# 笔记 #1 · 残破笔记（寻找那座塔）

> 本文件属于 **Remnant Echo 模组资料汇编** 的完整笔记内容章节（`lore-stories/notes/`）。
> 笔记 #1 是模组叙事的第一份笔记，玩家在 M1 种子埋下阶段拾取。
>
> **资料优先级**：P1（基于 [`09-village-loot-extension`](../../planning/09-village-loot-extension.md) §3.1 整理）
> **汇编日期**：2026-09-21
> **状态**：🟢 完成 v0.1
> **对应主线节点**：M1 种子埋下（按 [`28-main-side-quest-design`](../../planning/28-main-side-quest-design.md)）

---

## 1. 笔记基本信息

| 属性 | 值 |
|------|-----|
| **笔记编号** | #1 |
| **物品 ID** | `remnant:tattered_note`（按 [`10-custom-items-registry`](../../planning/10-custom-items-registry.md) §2.1 L3 自定义） |
| **基础物品** | `minecraft:written_book` + CustomModelData |
| **L 等级** | L3 |
| **落款角色** | M.（先民领袖，曾经的 C.） |
| **来源结构** | 村庄图书馆箱子（`chests/village/village_library`，15% 概率）+沙漠神殿箱子+丛林神庙箱子+废弃矿井矿车+地牢箱子（按 [`09-village-loot-extension`](../../planning/09-village-loot-extension.md) 方案 A 多 loot 表追加） |
| **触发概率** | 15%（村庄图书馆）/10%（沙漠神殿+丛林神庙）/8%（废弃矿井）/12%（地牢） |
| **触发方式** | 玩家拾取笔记后触发 advancement `remnant:lore/chapter_0` |

---

## 2. 笔记内容（zh_cn）

### 2.1 完整文本

> 寻找那座塔。它会告诉你我们是谁。
>
> 不要相信猪灵。也不要相信我们。
>
> —— M.

### 2.2 微动作 tellraw（玩家拾取时触发）

按 [`12-visual-audio-microaction`](../../17-lore-extensions/12-visual-audio-microaction.md) §6.1：

```mcfunction
# data/remnant/functions/lore/on_note1_pickup.mcfunction

# 视觉：粒子环绕笔记位置
particle minecraft:enchant ~ ~1 ~ 0.5 0.5 0.5 0 10
particle minecraft:note ~ ~1 ~ 0.3 0.3 0.3 0 5

# 听觉：轻柔 cat 配乐+ book_open 音效
playsound minecraft:music_disc_cat master @s ~ ~ ~ 0.3 1
playsound minecraft:block.chest.open master @s ~ ~ ~ 0.5 1

# 微动作 tellraw（M. 视角）
tellraw @s {"text":"你拾起笔记，纸张泛黄，墨迹模糊。","color":"gray","italic":true}
tellraw @s {"text":"字迹似乎在颤抖——是写的人害怕，还是阅读的人？","color":"gray","italic":true}
tellraw @s {"text":"最后一行有一个符号，像是字母 M。","color":"gray","italic":true}
tellraw @s {"text":"","extra":[{"text":"M. 写下这行字时，手指在颤抖。","color":"aqua","italic":true}]}
tellraw @s {"text":"","extra":[{"text":"线索书第 0 章已解锁。","color":"gold"}]}

# advancement 触发
advancement grant @s only remnant:lore/chapter_0
```

### 2.3 文学化展开（M. 视角，作为预写剧情参考）

按 [`12-visual-audio-microaction`](../../17-lore-extensions/12-visual-audio-microaction.md) §5.2.1：

> M. 写下这行字时，手指在颤抖。
>
> 他听到下界要塞的轰鸣声从远处传来——那是凋灵实验失控的前兆。
>
> 他抬头看向窗外，紫珀砖的塔楼在末地的紫雾中若隐若现。
>
> 他知道，这是他最后一次以"C."的身份写信。
>
> 他蘸了蘸墨，写下了最后的落款——M.。
>
> "M"是"Memory"（记忆）的第一个字母。他选择这个化名，是因为他知道，自己即将失去的，正是记忆。

---

## 3. 笔记内容（en_us）

### 3.1 完整文本

> Seek the tower. It will tell you who we are.
>
> Do not trust the piglins. Do not trust us either.
>
> — M.

### 3.2 lang key

```json
// assets/remnant/lang/en_us.json
{
  "item.remnant.tattered_note": "Tattered Note",
  "remnant.lore.note_1.title": "Tattered Note",
  "remnant.lore.note_1.page_1": "Seek the tower. It will tell you who we are.\n\nDo not trust the piglins. Do not trust us either.\n\n— M.",
  "remnant.lore.note_1.microaction_1": "You pick up the note. The pages are yellowed, the ink faded.",
  "remnant.lore.note_1.microaction_2": "The handwriting seems to tremble — was the writer afraid, or the reader?",
  "remnant.lore.note_1.microaction_3": "The last line bears a symbol, resembling the letter M.",
  "remnant.lore.note_1.microaction_4": "M.'s fingers trembled as he wrote this line.",
  "remnant.message.chapter_0_unlocked": "Clue Book Chapter 0 unlocked."
}
```

---

## 4. 笔记内容（ja_jp，v0.5 后）

### 4.1 完整文本

> あの塔を探せ。それが我々が何者かを教える。
>
> ピグリンを信じるな。我々も信じるな。
>
> —— M.

### 4.2 lang key

```json
// assets/remnant/lang/ja_jp.json
{
  "item.remnant.tattered_note": "破れたノート",
  "remnant.lore.note_1.title": "破れたノート",
  "remnant.lore.note_1.page_1": "あの塔を探せ。それが我々が何者かを教える。\n\nピグリンを信じるな。我々も信じるな。\n\n—— M.",
  "remnant.message.chapter_0_unlocked": "手がかり本 第0章 がアンロックされました。"
}
```

---

## 5. 笔记触发机制

### 5.1 advancement 配置

```json
// data/remnant/advancement/lore/chapter_0.json
{
  "display": {
    "icon": { "item": "minecraft:writable_book" },
    "title": "线索书第 0 章已解锁",
    "description": "残破笔记",
    "show_toast": true,
    "announce_to_chat": false,
    "hidden": false
  },
  "criteria": {
    "find_first_note": {
      "trigger": "minecraft:inventory_changed",
      "conditions": {
        "items": [
          {
            "items": ["minecraft:written_book"],
            "nbt": "{display:{Title:\"残破的笔记\"}}"
          }
        ]
      }
    }
  },
  "rewards": {
    "function": "remnant:lore/on_note1_pickup"
  }
}
```

### 5.2 loot 表追加（5 个原版 loot 表）

按 [`09-village-loot-extension`](../../planning/09-village-loot-extension.md) §2：

| 原版 loot 表 | 触发概率 | 笔记编号 |
|--------------|----------|----------|
| `chests/village/village_library` | 15% | #1 |
| `chests/desert_pyramid` | 10% | #1 |
| `chests/jungle_temple` | 10% | #1 |
| `chests/abandoned_mineshaft` | 8% | #1 |
| `chests/simple_dungeon` | 12% | #1 |

### 5.3 NBT 结构

按 [`10-custom-items-registry`](../../planning/10-custom-items-registry.md) §2.1：

```nbt
{
  display: {
    Title: "残破的笔记",
    Lore: ["纸张泛黄，墨迹模糊"]
  },
  CustomModelData: 1,
  pages: [
    '{"text":"寻找那座塔。它会告诉你我们是谁。\\n\\n不要相信猪灵。也不要相信我们。\\n\\n—— M."}'
  ],
  author: "M.",
  title: "残破的笔记",
  resolved: 1b
}
```

---

## 6. 模组叙事意义

按 [`01-spawn-point-design`](../../planning/01-spawn-point-design.md) §4.2：

- 第 1 句"寻找那座塔"指引玩家寻找要塞（要塞有塔楼结构）→ 软引导玩家探索主线
- 第 2 句"不要相信猪灵，也不要相信我们"埋下种族不信任伏笔→呼应"灾变与分裂"设定
- 落款 "M." 是神秘符号，后续在末地城日记中揭晓身份（先民领袖？末地殖民军指挥官？）

**与模组叙事的关联**：
- M. 是模组核心角色（按 [`09-mob-relationships`](../../17-lore-extensions/09-mob-relationships.md) + [`20-end-narrative`](../../planning/20-end-narrative.md) §14）
- 笔记 #1 是 M. 在主世界的留言，与笔记 #10（试炼密室）/笔记 #14（远古城市）/笔记 #17（要塞图书馆同人）/笔记 #18（苍白花园同人）/笔记 #26（真结局告别书）同人
- 笔记 #1 的"M."落款是模组叙事的"种子"——玩家通过收集 26 张笔记逐步拼凑 M. 的身份

---

## 7. 与已有规划文档的关联

- [`09-village-loot-extension`](../../planning/09-village-loot-extension.md) §3.1 笔记 #1 内容设计——本笔记是其完整实现
- [`10-custom-items-registry`](../../planning/10-custom-items-registry.md) §2.1 残破笔记 L3 自定义——本笔记是其 NBT 结构示例
- [`01-spawn-point-design`](../../planning/01-spawn-point-design.md) §4.2 推荐组合——本笔记是其开场白
- [`12-visual-audio-microaction`](../../17-lore-extensions/12-visual-audio-microaction.md) §5.2.1 M. 微动作——本笔记是其触发场景
- [`26-music-scenario-catalog`](../../planning/26-music-scenario-catalog.md) §9.1 拾取残破笔记配乐——本笔记是其听觉部分
- [`28-main-side-quest-design`](../../planning/28-main-side-quest-design.md) M1 种子埋下——本笔记是其核心交付
- [`29-story-outline`](../../planning/29-story-outline.md) M1 剧情大纲——本笔记是其剧情展开

---

## 8. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-21 | v0.1 | 初稿，按 [`09-village-loot-extension`](../../planning/09-village-loot-extension.md) §3.1 + [`12-visual-audio-microaction`](../../17-lore-extensions/12-visual-audio-microaction.md) §5.2.1 整理笔记 #1 完整内容，含 zh_cn/en_us/ja_jp 三语文本+微动作 tellraw+文学化展开+触发机制+NBT 结构+模组叙事意义 | 项目方 |
