# 06 · 认知锁机制详解

> **状态**：🟡 设计讨论中
> **对应模组版本**：v0.5（末地线）
> **创建日期**：2026-09-18
> **最后更新**：2026-09-18
> **设计原则**：[原则 0 · L1/L2/L3 判定](./00-planning-index.md#原则-0优先原版实在没辙才自定义且必须与原版有关)

---

## 1. 目的

通过**软引导**让玩家在挑战末影龙前先体验叙事内容。

**核心约束**：**不强制阻止**玩家进入末地。仅通过原版 `advancement` + `tellraw` 提示，引导玩家回头补叙事。

---

## 2. 实现方案

### 2.1 方案选择

| 方案 | 描述 | L 等级 | 是否采用 |
|------|------|--------|----------|
| A. 自定义"认知锁"机制 | 拦截末地传送门交互 | L3 | ❌ 新机制，违反原则 0 |
| B. 修改末地传送门方块行为 | 改变原版 `end_portal` 方块逻辑 | ❌ | 严重违反"不魔改原版交互" |
| C. **基于原版 `advancement` 触发 `tellraw`**（推荐 ✅） | 玩家进入末地传送门时通过 `location` 触发器检测认知达标，根据状态显示不同文本 | L2 | ✅ 采用 |

### 2.2 方案 C 的工作原理

```
玩家进入末地传送门
    ↓
原版 location advancement 触发器检测玩家位置（end_portal 框内）
    ↓
模组的 advancement 判定：
    玩家是否已解锁 remnant:lore/chapter_0 ~ chapter_6？
    ├─ 全部解锁 → 触发 function A：tellraw 显示「认知已达边界。你将看到他们留下的最后一道门。」
    └─ 未全部解锁 → 触发 function B：tellraw 显示「你还没有准备好。回去看看那些遗迹。」
    ↓
玩家正常进入末地（不被阻止）
```

**关键点**：
- ✅ 不阻止玩家进入末地
- ✅ 不伤害玩家
- ✅ 不改变原版末地传送门机制
- ✅ 仅通过 `advancement` + `tellraw` 显示提示

---

## 3. 详细配置

### 3.1 检测玩家进入末地传送门

```json
// data/remnant/advancement/lore/enter_end_portal.json
{
  "display": {
    "icon": { "item": "minecraft:end_portal_frame" },
    "title": "认知的边界",
    "description": "你已站在他们留下的最后一道门前",
    "show_toast": true,
    "announce_to_chat": false,
    "hidden": true
  },
  "criteria": {
    "in_end_portal": {
      "trigger": "minecraft:location",
      "conditions": {
        "player": {
          "location": {
            "block": {
              "block": "minecraft:end_portal"
            }
          }
        }
      }
    }
  },
  "rewards": {
    "function": "remnant:lore/check_cognitive_lock"
  }
}
```

### 3.2 认知锁判定 function

```mcfunction
# data/remnant/functions/lore/check_cognitive_lock.mcfunction

# 检查玩家是否已解锁所有关键章节
# 通过 scoreboard 跟踪已解锁章节数

# 重置计数
scoreboard players set @s remnant_chapters_read 0

# 检查每个章节的 advancement 状态
advancement test @s remnant:lore/chapter_0
execute if entity @s[advancements={remnant:lore/chapter_0=true}] run scoreboard players add @s remnant_chapters_read 1

advancement test @s remnant:lore/chapter_1
execute if entity @s[advancements={remnant:lore/chapter_1=true}] run scoreboard players add @s remnant_chapters_read 1

advancement test @s remnant:lore/chapter_2
execute if entity @s[advancements={remnant:lore/chapter_2=true}] run scoreboard players add @s remnant_chapters_read 1

advancement test @s remnant:lore/chapter_3
execute if entity @s[advancements={remnant:lore/chapter_3=true}] run scoreboard players add @s remnant_chapters_read 1

advancement test @s remnant:lore/chapter_4
execute if entity @s[advancements={remnant:lore/chapter_4=true}] run scoreboard players add @s remnant_chapters_read 1

advancement test @s remnant:lore/chapter_5
execute if entity @s[advancements={remnant:lore/chapter_5=true}] run scoreboard players add @s remnant_chapters_read 1

advancement test @s remnant:lore/chapter_6
execute if entity @s[advancements={remnant:lore/chapter_6=true}] run scoreboard players add @s remnant_chapters_read 1

# 根据计数显示不同文本
# 7 个章节全部解锁（计数 = 7）→ 认知达标
execute if score @s remnant_chapters_read = 7 run tellraw @s {"text":"认知已达边界。你将看到他们留下的最后一道门。","color":"gold","italic":true}

# 部分章节解锁（0 < 计数 < 7）→ 提示补全
execute if score @s remnant_chapters_read matches 1..6 run tellraw @s [{"text":"你还没有准备好。","color":"yellow"},{"text":"回去看看那些遗迹，他们会告诉你剩下的故事。","color":"gray","italic":true}]

# 完全未解锁（计数 = 0）→ 强烈提示
execute if score @s remnant_chapters_read = 0 run tellraw @s [{"text":"你冲得太快了。","color":"red"},{"text":"这片土地上有许多遗迹，每个都藏着故事。回去看看吧。","color":"gray","italic":true}]
```

### 3.3 与原版 advancement 系统的集成

**关键设计**：
- 检测逻辑基于原版 `minecraft:location` 触发器
- 判定逻辑使用原版 `advancement` + `scoreboard` + `tellraw` 命令
- **不引入任何新机制**

---

## 4. 认知达标的判定标准

### 4.1 必须解锁的章节

玩家进入末地传送门前，需要解锁以下 7 个章节：

| 章节 | 解锁触发 | 叙事意义 |
|------|----------|----------|
| 第 0 章 | 拾取第一份残破笔记 | 接触叙事 |
| 第 1 章 | 收集全部 5 份笔记 | 确认先民存在 |
| 第 2 章 | 探索主世界遗迹 | 鼎盛纪元 |
| 第 3 章 | 进入下界 | 凋灵之灾 |
| 第 4 章 | 进入堡垒遗迹 | 灾变与分裂 |
| 第 5 章 | 进入远古城市 | 幽匿之厄 |
| 第 6 章 | 进入苍白花园 | 苍白之悔 |

### 4.2 未列出的章节

| 章节 | 为何不列入认知锁判定 |
|------|----------------------|
| 第 7 章（进入末地） | 这就是认知锁保护的目标，逻辑循环 |
| 第 8 章（末地城探索） | 进入末地后才可触发，逻辑上不可能先解锁 |
| 第 9 章（末影人记忆） | 同上 |
| 终章 | 同上 |

### 4.3 可选的 Boss 击杀要求

**待讨论**：是否将击败凋灵、监守者纳入认知锁判定？

| 选项 | 设定 | 推荐度 |
|------|------|--------|
| A. 不纳入 | 仅要求章节阅读 | ★★★★ 推荐 |
| B. 纳入 | 要求击败凋灵 + 监守者 | ★★★ 增加挑战，但可能过度强制 |
| C. 部分纳入 | 仅要求击败监守者（与远古城市关联） | ★★★★ 备选 |

**推荐 A**：仅要求章节阅读，避免过度强制。Boss 击杀可作为彩蛋触发额外叙事，但不作为认知锁门槛。

---

## 5. 兼容性分析

| 检查项 | 状态 |
|--------|------|
| 是否阻止玩家进入末地？ | ❌ 不阻止 |
| 是否伤害玩家？ | ❌ 不伤害 |
| 是否改变原版末地传送门机制？ | ❌ 不改变 |
| 是否新增自定义机制？ | ❌ 仅用原版 advancement + tellraw |
| 玩家可绕过吗？ | ✅ 可（通过直接进入末地传送门） |
| 多人服务器是否兼容？ | ✅ 每个玩家独立判定 |
| 是否符合"补不是添"原则？ | ✅ L2（原版组合） |

---

## 6. 待讨论的设计问题

- [ ] 认知锁提示是显示一次还是每次进入末地都显示？建议首次 + 玩家主动查询时显示
- [ ] 是否提供"查看认知进度"的命令？建议是，通过 `/trigger remnant_progress` 实现
- [ ] 多人服务器中，是否需要团队认知共享？建议否，每个玩家独立
- [ ] 是否需要视觉提示（如未达标玩家传送门呈灰色）？建议否，违反"不魔改原版交互"

---

## 7. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-18 | v0.1 | 初稿，提出基于 advancement + tellraw 的认知锁方案 | 项目方 |
