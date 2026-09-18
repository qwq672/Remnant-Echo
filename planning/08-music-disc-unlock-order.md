# 08 · 唱片解锁顺序与剧情对应

> **状态**：🟡 设计讨论中
> **对应模组版本**：v0.6（唱片与真结局）
> **创建日期**：2026-09-18
> **最后更新**：2026-09-18
> **设计原则**：[原则 0 · L1/L2/L3 判定](./00-planning-index.md#原则-0优先原版实在没辙才自定义且必须与原版有关)

---

## 1. 目的

将原版 22 张唱片（含 1.21+ 新增）与叙事进度绑定，作为玩家探索的"声音奖励"。

**核心约束**：
- **不新增自定义唱片**（0 号唱片除外，见 L3 论证）
- **不修改原版唱片的获取方式**（仍通过原版 loot 表/掉落获取）
- 仅通过 `advancement` 触发器在玩家首次获得唱片时解锁对应的叙事文本

---

## 2. 唱片清单与叙事对应

### 2.1 原版 22 张唱片

按 [13-music-discs/02-minecraft-wiki.md](../13-music-discs/02-minecraft-wiki.md) 整理：

| 唱片 | 作曲者 | 获取方式 | 叙事对应 |
|------|--------|----------|----------|
| 13 | C418 | 地牢、林地府邸箱子 | 先民早期地下探索 |
| cat | C418 | 地牢、林地府邸箱子 | 文明安定期生活 |
| blocks | C418 | 地牢、林地府邸箱子 | 鼎盛期大兴土木 |
| chirp | C418 | 地牢、林地府邸箱子 | 红石发明前娱乐 |
| far | C418 | 地牢、林地府邸箱子 | 大陆探索 |
| mall | C418 | 地牢、林地府邸箱子 | 商业繁荣 |
| mellohi | C418 | 埋藏的宝藏箱子 | 祭祀/庆典 |
| stal | C418 | 地牢、林地府邸箱子 | 要塞军营警戒 |
| strad | C418 | 地牢、林地府邸箱子 | 贵族/学者书房 |
| ward | C418 | 远古城市箱子 | 黑暗之地守卫 |
| 11 | C418 | 地牢、林地府邸箱子 | 最后逃亡录音 |
| wait | C418 | 地牢、林地府邸箱子 | 文明余响 |
| Pigstep | Lena Raine | 堡垒遗迹箱子 | 猪灵战舞 |
| otherside | Lena Raine | 要塞、地牢箱子 | 异界回响 |
| 5 | Lena Raine | 远古城市（碎片合成） | 监守者觉醒 |
| Relic | Aaron Cherof | 古迹废墟（brush 考古） | 文明残响 |
| Creator | Lena Raine | 试炼密室装饰陶罐 | 创造者意志 |
| Creator (Music Box) | Lena Raine | 试炼密室装饰陶罐 | 治愈变体 |
| Precipice | Aaron Cherof | 试炼密室装饰陶罐 | 悬崖边缘 |
| Tears | Lena Raine | 1.21.5+ 锡罐（？） | 待定 |

### 2.2 模组新增唱片

**0 号唱片（L3 自定义，待论证）**

#### L3 自定义论证

**必要性**：
- L1（用原版唱片）：22 张原版唱片均无"先民领袖遗言"的叙事对应，无法承载真结局
- L2（用 `written_book` 承载遗言）：与"玩家通过 0 号唱片听遗言"的叙事不符，且 `written_book` 是文本而非音频
- L3（自定义"0 号唱片"）：通过合成配方获得，作为真结局的最终奖励

**关联性**（满足 4 项）：
| 关联维度 | 满足情况 |
|----------|----------|
| 视觉关联 | ✅ 纹理基于原版 `music_disc_13` 修改（加黑色裂纹） |
| 行为关联 | ✅ 行为与原版唱片一致（可放入唱片机、播放音轨） |
| 来源关联 | ✅ 通过合成配方获得（22 张原版唱片 + 下界之星） |
| 数据关联 | ✅ NBT 结构基于原版 `music_disc`，仅追加 `CustomModelData` |
| 退化关联 | ✅ 失去模组时退化为普通 `music_disc_13`，仍可在唱片机播放原音轨 |

**退化方案**：
- 失去模组时，0 号唱片退化为 `minecraft:music_disc_13`
- 玩家仍可在唱片机播放 C418 的 13 号唱片
- 合成配方中的下界之星仍保留

**结论**：0 号唱片满足 L3 标准，允许作为唯一自定义唱片。

---

## 3. 唱片解锁叙事的触发机制

### 3.1 触发流程

```
玩家获得原版唱片（通过原版 loot 表/掉落）
    ↓
触发原版 inventory_changed advancement
    ↓
advancement reward 调用 function
    ↓
function 通过 tellraw 显示该唱片的叙事解读
    ↓
同时解锁线索书对应章节的"唱片解读"内容
```

### 3.2 advancement 配置示例

**13 号唱片首次获得**：
```json
// data/remnant/advancement/lore/disc_13.json
{
  "display": {
    "icon": { "item": "minecraft:music_disc_13" },
    "title": "13 · 洞穴探索录音",
    "description": "先民早期地下探索的回响",
    "show_toast": true,
    "announce_to_chat": false,
    "hidden": true
  },
  "criteria": {
    "get_disc_13": {
      "trigger": "minecraft:inventory_changed",
      "conditions": {
        "items": [
          {
            "items": ["minecraft:music_disc_13"]
          }
        ]
      }
    }
  },
  "rewards": {
    "function": "remnant:lore/on_disc_13_acquired"
  }
}
```

**触发 function**：
```mcfunction
# data/remnant/functions/lore/on_disc_13_acquired.mcfunction

# 仅首次触发显示
execute unless entity @s[advancements={remnant:lore/disc_13=true}] run tellraw @s [{"text":"你获得了 13 号唱片。","color":"gold","italic":true}]

execute unless entity @s[advancements={remnant:lore/disc_13=true}] run tellraw @s [{"text":"放入唱片机，听到的是先民早期的洞穴探索录音——","color":"gray","italic":true},{"text":"脚步声、镐声、远处的低吟。","color":"gray","italic":true}]

# 解锁线索书"唱片解读"页面
advancement grant @s only remnant:lore/disc_13
```

---

## 4. 唱片与线索书章节的对应

| 唱片 | 解锁的线索书内容 | 章节 |
|------|------------------|------|
| 13 | 洞穴探索录音解读 | 第 2 章补充 |
| cat | 文明安定期生活解读 | 第 2 章补充 |
| blocks | 鼎盛期建造解读 | 第 2 章补充 |
| chirp | 早期电路音乐解读 | 第 2 章补充 |
| far | 大陆探索解读 | 第 2 章补充 |
| mall | 商业繁荣解读 | 第 2 章补充 |
| mellohi | 祭祀庆典解读 | 第 2 章补充 |
| stal | 要塞军营警戒解读 | 第 2 章补充 |
| strad | 贵族学者书房解读 | 第 2 章补充 |
| ward | 黑暗之地守卫解读 | 第 5 章补充 |
| 11 | 最后逃亡录音解读 | 第 9 章补充 |
| wait | 文明余响解读 | 第 7 章补充 |
| Pigstep | 猪灵战舞解读 | 第 3 章补充 |
| otherside | 异界回响解读 | 第 5 章补充 |
| 5 | 监守者觉醒解读 | 第 5 章补充 |
| Relic | 文明残响解读 | 第 6 章补充 |
| Creator | 创造者意志解读 | 第 7 章补充 |
| Creator (Music Box) | 治愈变体解读 | 第 7 章补充 |
| Precipice | 悬崖边缘解读 | 第 7 章补充 |
| 0 号唱片 | 先民领袖遗言 | 终章 |

---

## 5. 0 号唱片的合成配方

**合成配方**：22 张原版唱片 + 1 个下界之星

```
[ 13 ][ cat ][blocks]
[chip][star ][wait ]
[Pig ][other][5    ]
```

- 22 张原版唱片按特定顺序排列在合成台中
- 中央放置下界之星（象征三界同源 + 凋灵的产物）
- 合成结果：1 个 0 号唱片

**advancement 触发**：
```json
// data/remnant/advancement/lore/craft_disc_0.json
{
  "display": {
    "icon": { "item": "minecraft:music_disc_13" },
    "title": "0 号唱片 · 先民领袖的遗言",
    "description": "M. 的最后声音",
    "show_toast": true,
    "announce_to_chat": true,
    "hidden": false,
    "frame": "challenge"
  },
  "criteria": {
    "craft_disc_0": {
      "trigger": "minecraft:recipe_crafted",
      "conditions": {
        "recipe": "remnant:disc_0"
      }
    }
  },
  "rewards": {
    "function": "remnant:lore/on_disc_0_crafted"
  }
}
```

**触发 function**：
```mcfunction
# data/remnant/functions/lore/on_disc_0_crafted.mcfunction

tellraw @s [{"text":"你合成了 0 号唱片。","color":"gold","bold":true}]

tellraw @s [{"text":"放入唱片机——","color":"yellow","italic":true}]

# 等待玩家放入唱片机（延迟 5 秒后检查）
schedule function remnant:lore/disc_0_play 5s

# 解锁线索书终章
advancement grant @s only remnant:lore/chapter_final
```

**0 号唱片播放叙事**：
```mcfunction
# data/remnant/functions/lore/disc_0_play.mcfunction

# 检测玩家是否在 5 秒内将 0 号唱片放入唱片机
# 若放入，触发完整叙事
execute as @s at @s if block ~ ~ ~ minecraft:jukebox{RecordItem:{id:"minecraft:music_disc_13",tag:{CustomModelData:0}}} run tellraw @s [{"text":"「他们不是英雄，不是叛徒，不是怪物。","color":"aqua","italic":true},{"text":"他们只是一群完成任务的士兵，","color":"aqua","italic":true},{"text":"在任务完成后发现……","color":"aqua","italic":true},{"text":"总部已经不在了。」","color":"aqua","italic":true}]

execute as @s at @s if block ~ ~ ~ minecraft:jukebox{RecordItem:{id:"minecraft:music_disc_13",tag:{CustomModelData:0}}} run tellraw @s [{"text":"—— M.","color":"gold","italic":true}]
```

---

## 6. 兼容性分析

| 检查项 | 状态 |
|--------|------|
| 是否新增自定义唱片？ | ✅ 仅 1 个（0 号唱片），符合 L3 标准 |
| 是否修改原版唱片获取方式？ | ❌ 不修改 |
| 是否改变原版唱片行为？ | ❌ 不改变 |
| 是否阻止玩家获取原版唱片？ | ❌ 不阻止 |
| 0 号唱片退化方案？ | ✅ 失去模组时退化为 `music_disc_13` |
| 多人服务器兼容性？ | ✅ 每个玩家独立判定 advancement |

---

## 7. v0.6 实现验收标准

- [ ] 实现 22 张原版唱片的 advancement 触发器
- [ ] 实现对应的 22 个触发 function
- [ ] 实现线索书"唱片解读"页面（22 个）
- [ ] 实现 0 号唱片物品（L3 自定义，含 `CustomModelData`）
- [ ] 实现 0 号唱片合成配方（22 原版唱片 + 1 下界之星）
- [ ] 实现 0 号唱片播放时触发先民领袖遗言叙事
- [ ] 实现真结局 advancement
- [ ] 多语言支持（en_us + zh_cn）

---

## 8. 待讨论的设计问题

- [ ] 0 号唱片的音轨：使用 C418 现有曲目 + 静默？还是新增音轨（L3 自定义音轨需满足关联性）？
- [ ] 0 号唱片的合成配方是否需要解锁条件？建议是（先解锁全部 22 张原版唱片的 advancement）
- [ ] 玩家可否通过创造模式直接获取 0 号唱片？建议是（创造模式不限制）
- [ ] 多人服务器中，0 号唱片是否可交易？建议否（保持真结局稀缺性）

---

## 9. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-18 | v0.1 | 初稿，提出 22 张原版唱片 + 0 号唱片（L3 自定义）方案 | 项目方 |
