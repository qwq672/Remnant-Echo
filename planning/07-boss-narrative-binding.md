# 07 · Boss 叙事绑定

> **状态**：🟡 设计讨论中
> **对应模组版本**：v0.5+
> **创建日期**：2026-09-18
> **最后更新**：2026-09-18
> **设计原则**：[原则 0 · L1/L2/L3 判定](./00-planning-index.md#原则-0优先原版实在没辙才自定义且必须与原版有关)

---

## 1. 目的

将原版 Boss（凋灵、末影龙、监守者）的击杀事件与叙事文本绑定，让 Boss 战成为叙事高潮。

**核心约束**：
- **不新增自定义 Boss**（违反原则 0）
- **不修改原版 Boss 的 AI/属性**
- 仅通过原版 `advancement` 触发器在 Boss 击杀后显示叙事文本

---

## 2. Boss 体系设计

### 2.1 参与叙事的原版 Boss

| Boss | 击杀触发 | 叙事章节 | 叙事主题 |
|------|----------|----------|----------|
| 凋灵 | `minecraft:player_killed_entity` | 第 3 章补充 | 凋灵之灾的复现 |
| 监守者 | `minecraft:player_killed_entity` | 第 5 章补充 | 幽匿之厄的悲剧 |
| 末影龙 | `minecraft:player_killed_entity`（原版 `end/kill_dragon`） | 第 7 章 | 守门人真相 |
| 凋灵骷髅（非 Boss，但相关） | `minecraft:player_killed_entity` | 第 3 章补充 | 凋灵实验残留 |

### 2.2 不参与叙事的原版 Boss

| Boss | 为何不参与 |
|------|------------|
| 远古守卫者 | 与主线叙事关联较弱，可选作彩蛋 |
| 劫掠兽 | 灾厄村民分支叙事，v0.3 后考虑 |
| 凋灵（再次召唤） | 玩家可多次召唤，仅首次击杀触发叙事 |

---

## 3. 详细设计

### 3.1 凋灵击杀触发

**叙事主题**：玩家重现了先民的凋灵召唤，目睹了灾变的余响。

**advancement 配置**：
```json
// data/remnant/advancement/lore/kill_wither.json
{
  "display": {
    "icon": { "item": "minecraft:nether_star" },
    "title": "灾变的余响",
    "description": "你重现了他们的实验，并活了下来",
    "show_toast": true,
    "announce_to_chat": false,
    "hidden": true,
    "frame": "goal"
  },
  "criteria": {
    "kill_wither": {
      "trigger": "minecraft:player_killed_entity",
      "conditions": {
        "entity": {
          "type": "minecraft:wither"
        }
      }
    }
  },
  "rewards": {
    "function": "remnant:lore/on_wither_killed"
  }
}
```

**触发 function**：
```mcfunction
# data/remnant/functions/lore/on_wither_killed.mcfunction

tellraw @s [{"text":"凋灵倒下了。","color":"dark_red","bold":true},{"text":"它的灵魂消散，但那扭曲的能量仍在下界回响。","color":"gray","italic":true}]

tellraw @s [{"text":"他们也曾这样召唤过——","color":"yellow","italic":true},{"text":"在下界要塞的中心，用同样的灵魂沙与凋灵骷髅头颅。","color":"gray","italic":true}]

tellraw @s [{"text":"只是那一次，他们没能控制住。","color":"red","italic":true}]

# 解锁线索书第 3 章补充内容
advancement grant @s only remnant:lore/chapter_3_supplement
```

### 3.2 监守者击杀触发

**叙事主题**：玩家终结了远古城市的悲剧，但监守者的灵魂仍未安息。

**advancement 配置**：
```json
// data/remnant/advancement/lore/kill_warden.json
{
  "display": {
    "icon": { "item": "minecraft:sculk_catalyst" },
    "title": "监守者的安息",
    "description": "远古城市的悲剧终于落幕",
    "show_toast": true,
    "announce_to_chat": false,
    "hidden": true,
    "frame": "goal"
  },
  "criteria": {
    "kill_warden": {
      "trigger": "minecraft:player_killed_entity",
      "conditions": {
        "entity": {
          "type": "minecraft:warden"
        }
      }
    }
  },
  "rewards": {
    "function": "remnant:lore/on_warden_killed"
  }
}
```

**触发 function**：
```mcfunction
# data/remnant/functions/lore/on_warden_killed.mcfunction

tellraw @s [{"text":"监守者倒下了。","color":"dark_blue","bold":true},{"text":"它没有眼睛——因为它不需要看。","color":"gray","italic":true}]

tellraw @s [{"text":"它曾是科研贵族的灵魂聚合体，","color":"aqua","italic":true},{"text":"被幽匿吞噬后，只剩下守护远古城市的本能。","color":"gray","italic":true}]

tellraw @s [{"text":"现在，它终于可以安息了。","color":"dark_purple","italic":true}]

# 解锁线索书第 5 章补充内容
advancement grant @s only remnant:lore/chapter_5_supplement
```

### 3.3 末影龙击杀触发

**叙事主题**：玩家击败末影龙后，"守门人真相"浮现。

**advancement 配置**：
```json
// data/remnant/advancement/lore/kill_ender_dragon.json
{
  "display": {
    "icon": { "item": "minecraft:dragon_head" },
    "title": "守门人",
    "description": "它不是敌人——它是被遗忘的守卫",
    "show_toast": true,
    "announce_to_chat": false,
    "hidden": true,
    "frame": "challenge"
  },
  "criteria": {
    "kill_dragon": {
      "trigger": "minecraft:player_killed_entity",
      "conditions": {
        "entity": {
          "type": "minecraft:ender_dragon"
        }
      }
    }
  },
  "rewards": {
    "function": "remnant:lore/on_dragon_killed"
  }
}
```

**触发 function**：
```mcfunction
# data/remnant/functions/lore/on_dragon_killed.mcfunction

# 等待原版 End Poem 播放完毕（约 9 分钟）
# 玩家进入末地返回传送门时会自动触发

# 在原版 End Poem 结束后追加额外叙事
tellraw @s [{"text":"《诗》说完了。","color":"gold","bold":true}]

tellraw @s [{"text":"但故事还没结束。","color":"yellow","italic":true}]

tellraw @s [{"text":"末影龙不是末地的统治者——","color":"aqua","italic":true},{"text":"它是守门人，","color":"aqua","italic":true},{"text":"被先民留下的指令守护着这座空城。","color":"gray","italic":true}]

tellraw @s [{"text":"现在它倒下了，门打开了。","color":"dark_purple","italic":true},{"text":"去末地城看看吧——他们在那里等你。","color":"gray","italic":true}]

# 解锁线索书第 7 章
advancement grant @s only remnant:lore/chapter_7
```

### 3.4 凋灵骷髅击杀触发（补充叙事）

**叙事主题**：玩家击败凋灵骷髅，理解其身份——先民射手的转化体。

**advancement 配置**：
```json
// data/remnant/advancement/lore/kill_wither_skeleton.json
{
  "display": {
    "icon": { "item": "minecraft:wither_skeleton_skull" },
    "title": "执行最后命令的射手",
    "description": "他们的灵魂被困，仍在守卫下界要塞",
    "show_toast": false,
    "announce_to_chat": false,
    "hidden": true
  },
  "criteria": {
    "kill_wither_skeleton": {
      "trigger": "minecraft:player_killed_entity",
      "conditions": {
        "entity": {
          "type": "minecraft:wither_skeleton"
        }
      }
    }
  },
  "rewards": {
    "function": "remnant:lore/on_wither_skeleton_killed"
  }
}
```

**触发 function**（仅首次触发）：
```mcfunction
# data/remnant/functions/lore/on_wither_skeleton_killed.mcfunction

# 仅在玩家首次击杀凋灵骷髅时显示
execute unless entity @s[advancements={remnant:lore/kill_wither_skeleton=true}] run tellraw @s [{"text":"凋灵骷髅倒下了。","color":"gray","italic":true},{"text":"它的骨头是黑色的，仿佛被烧焦过。","color":"gray","italic":true}]

execute unless entity @s[advancements={remnant:lore/kill_wither_skeleton=true}] run tellraw @s [{"text":"他们曾是先民的射手阶层，","color":"yellow","italic":true},{"text":"在凋灵之灾中被扭曲波及，灵魂被困在骨头里，","color":"gray","italic":true},{"text":"执行着最后的命令——守卫下界要塞。","color":"gray","italic":true}]
```

---

## 4. 叙事触发的去重机制

为避免玩家多次击杀同一 Boss 时反复触发同一叙事，使用 advancement 内置的"一次性触发"机制。

**实现**：
- 每个 Boss 击杀触发的 advancement 配置为 `hidden: true`，玩家不会看到重复的 toast
- function 内部使用 `execute unless entity @s[advancements={...}]` 判定是否首次触发
- 首次触发后 advancement 自动标记为已获得，不再重复触发

---

## 5. 与原版 Boss 战的兼容性

| 检查项 | 状态 |
|--------|------|
| 是否新增自定义 Boss？ | ❌ 不新增 |
| 是否修改原版 Boss 的 AI/属性？ | ❌ 不修改 |
| 是否改变原版 Boss 战流程？ | ❌ 不改变 |
| 是否阻止玩家击杀 Boss？ | ❌ 不阻止 |
| 是否阻止玩家重复击杀？ | ❌ 不阻止 |
| 仅通过 advancement 触发叙事？ | ✅ 是 |
| 多人服务器中谁获得叙事？ | 仅击杀者 |

---

## 6. v0.5 实现验收标准

- [ ] 实现 4 个 Boss 击杀触发的 advancement（凋灵、监守者、末影龙、凋灵骷髅）
- [ ] 实现对应的 4 个触发 function
- [ ] 实现去重机制（仅首次触发显示完整叙事）
- [ ] 实现线索书对应章节补充内容的解锁
- [ ] 多语言支持（en_us + zh_cn）
- [ ] 多人服务器测试（仅击杀者获得叙事）

---

## 7. 待讨论的设计问题

- [ ] 凋灵骷髅击杀是否每次都触发？建议仅首次（避免刷怪时被刷屏）
- [ ] 末影龙击杀叙事是否与原版 End Poem 冲突？建议否，原版 End Poem 结束后才追加
- [ ] 是否需要给监守者击杀额外的视觉提示（如粒子效果）？建议否，违反"不魔改原版"
- [ ] 是否需要 Boss 击杀后掉落额外叙事物品（如"凋灵记忆碎片"）？建议否，避免新增物品

---

## 8. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-18 | v0.1 | 初稿，提出 4 个 Boss 击杀触发的叙事绑定方案 | 项目方 |
