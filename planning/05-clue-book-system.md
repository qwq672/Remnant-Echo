# 05 · 线索书系统设计

> **状态**：🟡 设计讨论中
> **对应模组版本**：v0.1（概念验证）
> **创建日期**：2026-09-18
> **最后更新**：2026-09-18
> **设计原则**：[原则 0 · L1/L2/L3 判定](./00-planning-index.md#原则-0优先原版实在没辙才自定义且必须与原版有关)

---

## 1. 目的

设计承载叙事内容的"线索书"系统，让玩家通过阅读线索拼凑远古先民文明的真相。

**核心约束**：线索书必须是玩家**可主动阅读**的载体，**不可强制弹窗**、**不可阻止游戏**。

---

## 2. 实现方案：Patchouli + advancement 触发

### 2.1 方案选择

| 方案 | 描述 | L 等级 | 是否采用 |
|------|------|--------|----------|
| A. 纯原版 `written_book` | 用 NBT 写入多页文本，玩家右键阅读 | L1 | ❌ 单本 `written_book` 难承载章节解锁机制 |
| B. `written_book` + advancement 树 | 每个章节是一本独立 `written_book`，通过 advancement 解锁 | L2 | ⚠️ 可行，但玩家背包会有 22+ 本书，体验差 |
| C. **Patchouli 模组集成**（推荐 ✅） | 用 Patchouli 提供的"持续存在的书"，章节通过 advancement 解锁 | L3 | ✅ 采用 |

### 2.2 为何 Patchouli 是 L3 自定义（合规）

Patchouli 是 Vazkii 开发的开源模组，被大量模组采用（如 Botania、Create 等），已成为"事实标准"。

**关联性论证**：
| 关联维度 | 满足情况 |
|----------|----------|
| 视觉关联 | ✅ Patchouli 的书外观基于原版 `written_book` 纹理 |
| 行为关联 | ✅ 行为与 `written_book` 一致（右键打开、可放入讲台） |
| 来源关联 | ✅ 通过原版 advancement 触发解锁 |
| 数据关联 | ✅ 章节内容存储在 JSON 文件中，结构参考原版 `advancement` JSON |
| 退化关联 | ✅ 失去 Patchouli 时，玩家无法打开书但物品仍在背包，可通过 JEI 查看章节 |

**必要性论证**：
- L1（纯 `written_book`）：无法实现"章节解锁"机制，玩家无法知道哪些章节已读
- L2（`written_book` + advancement 树）：每个章节一本独立书，背包会有 22+ 本书，体验极差
- L3（Patchouli）：单一物品承载所有章节，按 advancement 解锁，体验最佳

**结论**：Patchouli 满足 L3 标准，允许作为软依赖引入。

### 2.3 软依赖策略

- 模组**不强制依赖** Patchouli
- 若玩家未安装 Patchouli：模组仍能运行，叙事文本通过 `tellraw` 显示（降级体验）
- 若玩家安装 Patchouli：完整线索书体验

---

## 3. 线索书结构设计

### 3.1 章节划分

按 [03-player-journey-map.md](./03-player-journey-map.md) 的十阶段路径划分：

| 章节 | 标题 | 解锁触发 | 内容主题 |
|------|------|----------|----------|
| 第 0 章 | 残破笔记 | 拾取第一份 `written_book` | 寻找那座塔 |
| 第 1 章 | 先民存在 | 收集全部 5 份笔记 | 三界同源伏笔 |
| 第 2 章 | 主世界考古 | 探索沙漠神殿、丛林神庙、地牢、废弃矿井 | 先民鼎盛纪元 |
| 第 3 章 | 下界初探 | 进入下界 | 凋灵之灾伏笔 |
| 第 4 章 | 下界深处 | 进入猪灵堡垒 | 灾变与分裂 |
| 第 5 章 | 远古城市 | 进入远古城市 | 幽匿之厄 |
| 第 6 章 | 苍白花园 | 进入苍白花园 | 苍白之悔 |
| 第 7 章 | 进入末地 | 击败末影龙 | 守门人真相 |
| 第 8 章 | 末地城探索 | 进入末地城 | 末地殖民军 |
| 第 9 章 | 末影人的记忆 | 找到远古日记 | 被遗忘的士兵 |
| 终章 | M. 的遗言 | 合成 0 号唱片 | 先民领袖遗言 |

### 3.2 章节解锁的 advancement 配置

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
    "function": "remnant:lore/unlock_chapter_0"
  }
}
```

### 3.3 章节内容（Patchouli JSON 格式）

每个章节对应一个 Patchouli JSON 文件，存放在 `data/remnant/patchouli_books/remnant/en_us/entries/` 目录。

**示例：第 0 章内容**

```json
// data/remnant/patchouli_books/remnant/en_us/entries/chapter_0.json
{
  "name": "残破笔记",
  "icon": "minecraft:writable_book",
  "category": "remnant:lore",
  "advancement": "remnant:lore/chapter_0",
  "pages": [
    {
      "type": "text",
      "text": "寻找那座塔。它会告诉你我们是谁。$(br2)不要相信猪灵。也不要相信我们。$(br2)—— M."
    },
    {
      "type": "text",
      "text": "笔记的纸张泛黄，墨迹模糊。$(br)字迹似乎在颤抖——是写的人害怕，还是阅读的人？$(br2)最后一行有一个符号，像是字母 M。"
    }
  ]
}
```

---

## 4. 线索书的物理载体

### 4.1 物品选择

| 选项 | 描述 | L 等级 | 是否采用 |
|------|------|--------|----------|
| A. 用原版 `written_book` 作为线索书 | 玩家通过合成获得 | L1 | ❌ 玩家无法区分普通 `written_book` 与线索书 |
| B. 用原版 `knowledge_book` | 已弃用的原版物品 | L1 | ❌ 已弃用，玩家陌生 |
| C. **Patchouli 的 `patchouli:guide_book`**（推荐 ✅） | Patchouli 提供的书物品 | L3 | ✅ 采用 |

### 4.2 玩家如何获得线索书

**两种获取方式并存**：

**方式 1：合成（推荐）**
- 配方：`book` + `ender_eye` + `paper` × 3
- 合成后获得 `patchouli:guide_book`，NBT 指向 `remnant:remnant` 这本书
- 用原版 `crafting_shaped` 配方，符合 L1/L2

**方式 2：拾取第一份残破笔记后自动获得**
- 触发 `remnant:lore/chapter_0` advancement
- advancement reward 调用 function `remnant:lore/give_guide_book`
- function 内容：`give @s patchouli:guide_book{patchouli:book:"remnant:remnant"}`
- 玩家上线后第一次拾取笔记即获得

### 4.3 与原版物品的兼容性

- 线索书是 `patchouli:guide_book` 物品，**不替换**原版 `written_book`
- 残破笔记是 `written_book` + NBT，**不替换**原版 `written_book`
- 玩家可同时拥有原版 `written_book` 与线索书，互不干扰

---

## 5. 叙事文本的本地化

### 5.1 多语言支持

通过原版 `lang/` JSON 文件实现，**不新增自定义本地化机制**。

**文件结构**：
```
assets/remnant/lang/
├── en_us.json
├── zh_cn.json
├── ja_jp.json
└── ...
```

**示例（en_us.json）**：
```json
{
  "remnant.lore.chapter_0.title": "Tattered Note",
  "remnant.lore.chapter_0.page_1": "Seek the tower. It will tell you who we are.\n\nDo not trust the piglins. Do not trust us either.\n\n— M.",
  "remnant.lore.chapter_0.page_2": "The pages are yellowed, the ink faded.\nThe handwriting seems to tremble—was the writer afraid, or the reader?\n\nThe last line bears a symbol, resembling the letter M."
}
```

### 5.2 Patchouli 章节文本的本地化

Patchouli 支持 `$(l)` 等格式化标签，文本内容直接从 JSON 文件读取。

通过 `assets/remnant/lang/zh_cn.json` 等文件覆盖，实现多语言。

---

## 6. 与原版 advancement 系统的集成

### 6.1 advancement 树结构

```
remnant:lore/root
├── remnant:lore/chapter_0  (find_first_note)
├── remnant:lore/chapter_1  (collect_all_5_notes)
├── remnant:lore/chapter_2  (explore_desert_temple + jungle_temple + dungeon + mineshaft)
├── remnant:lore/chapter_3  (enter_nether)
├── remnant:lore/chapter_4  (enter_bastion)
├── remnant:lore/chapter_5  (enter_ancient_city)
├── remnant:lore/chapter_6  (enter_pale_garden)
├── remnant:lore/chapter_7  (kill_ender_dragon)
├── remnant:lore/chapter_8  (enter_end_city)
├── remnant:lore/chapter_9  (find_ancient_journal)
└── remnant:lore/chapter_final  (craft_disc_0)
```

### 6.2 触发器配置

每个 advancement 使用原版触发器：

| 章节 | 触发器 | 原版触发器名 |
|------|--------|-------------|
| 第 0 章 | 拾取残破笔记 | `minecraft:inventory_changed` |
| 第 1 章 | 收集全部 5 份笔记 | `minecraft:inventory_changed` + 计数 |
| 第 2 章 | 探索遗迹 | `minecraft:location`（特定 biome/structure） |
| 第 3 章 | 进入下界 | `minecraft:location`（nether biome） |
| 第 4 章 | 进入堡垒遗迹 | `minecraft:location`（bastion_remnant） |
| 第 5 章 | 进入远古城市 | `minecraft:location`（ancient_city） |
| 第 6 章 | 进入苍白花园 | `minecraft:location`（pale_garden） |
| 第 7 章 | 击败末影龙 | `minecraft:player_killed_entity` |
| 第 8 章 | 进入末地城 | `minecraft:location`（end_city） |
| 第 9 章 | 找到远古日记 | `minecraft:inventory_changed` |
| 终章 | 合成 0 号唱片 | `minecraft:recipe_crafted` |

所有触发器均为原版机制，符合 L1/L2 标准。

---

## 7. v0.1 实现验收标准

- [ ] 集成 Patchouli 作为软依赖
- [ ] 实现线索书物品（`patchouli:guide_book` 指向 `remnant:remnant`）
- [ ] 实现第 0 章的 advancement 触发器
- [ ] 实现第 0 章的 Patchouli JSON 内容
- [ ] 玩家可通过合成获得线索书
- [ ] 玩家可通过拾取残破笔记自动获得线索书
- [ ] 线索书打开后显示第 0 章内容
- [ ] 未解锁章节在书中显示为"???"
- [ ] 多语言支持（en_us + zh_cn）

---

## 8. 风险与讨论点

### 8.1 风险

1. **Patchouli 兼容性**
   - 缓解：作为软依赖，未安装时降级为 `tellraw` 显示
2. **背包占用**
   - 缓解：线索书是单一物品，所有章节在书内切换，不占额外背包格
3. **多人服务器中 advancement 同步**
   - 缓解：每个玩家独立判定 advancement，符合原版多人逻辑

### 8.2 待讨论的设计问题

- [ ] 线索书是否可丢弃？建议可丢弃但可通过合成重新获得
- [ ] 线索书是否灵魂绑定？建议否，违反"不魔改原版交互"
- [ ] 章节内容是否包含图片/插图？建议 v0.5 后考虑（需 L3 自定义纹理）
- [ ] 是否提供"已读章节"标记？建议是，通过 advancement 内部状态实现

---

## 9. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-18 | v0.1 | 初稿，提出 Patchouli 集成方案，符合 L3 标准 | 项目方 |
