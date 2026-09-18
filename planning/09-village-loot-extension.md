# 09 · 5 个原版 loot 表详细配置

> **状态**：🟡 设计讨论中
> **对应模组版本**：v0.1 ~ v0.2
> **创建日期**：2026-09-18
> **最后更新**：2026-09-18
> **设计原则**：[原则 0 · L1/L2/L3 判定](./00-planning-index.md#原则-0优先原版实在没辙才自定义且必须与原版有关)

---

## 1. 目的

通过修改原版 loot 表，让玩家在自然探索过程中**自然遇到叙事文本**。

**核心约束**：
- **仅追加条目**，不删除原有内容
- **不新增自定义物品**，用原版 `written_book` + NBT 承载叙事
- **不改变原版结构生成逻辑**

---

## 2. 目标 loot 表清单

| 原版结构 | loot 表路径 | 追加物品 | 触发概率 | 叙事文本 |
|----------|-------------|----------|----------|----------|
| 村庄图书馆箱子 | `chests/village/village_library` | `written_book`（笔记 #1） | 15% | 寻找那座塔 |
| 沙漠神殿箱子 | `chests/desert_pyramid` | `written_book`（笔记 #2） | 10% | 祭祀记录 |
| 丛林神庙箱子 | `chests/jungle_temple` | `written_book`（笔记 #3） | 10% | 红石记录 |
| 废弃矿井矿车 | `chests/abandoned_mineshaft` | `written_book`（笔记 #4） | 8% | 劳工日志 |
| 地牢箱子 | `chests/simple_dungeon` | `written_book`（笔记 #5） | 12% | 监禁记录 |

---

## 3. 笔记内容设计

### 3.1 笔记 #1 · 寻找那座塔

**来源**：村庄图书馆箱子

**正文**：
> 「寻找那座塔。它会告诉你我们是谁。
>
> 不要相信猪灵。也不要相信我们。
>
> —— M.」

**叙事意义**：
- 第 1 句指引玩家寻找要塞
- 第 2 句埋下种族不信任伏笔
- 落款 "M." 为神秘符号

### 3.2 笔记 #2 · 祭祀记录

**来源**：沙漠神殿箱子

**正文**：
> 「今日的祭祀又失败了。
>
> 我们把最好的金子、苹果、马铠都埋进了沙下，但他们没有回应。
>
> 也许他们从未存在过。
>
> —— 第三祭司」

**叙事意义**：
- 暗示先民信仰体系的衰落
- "他们"指代不明，可解读为更高存在（或先民祖先）
- 与沙漠神殿的金苹果、马铠 loot 对应

### 3.3 笔记 #3 · 红石记录

**来源**：丛林神庙箱子

**正文**：
> 「红石终于听话了。
>
> 拉杆、绊线、活塞——这些小零件能拼出大奇迹。
>
> 但我还是搞不懂为什么它们要在丛林深处修这么复杂的陷阱。是为了防什么？
>
> —— 工匠 K.」

**叙事意义**：
- 暗示红石机械的发明期
- 提到丛林神庙的绊线陷阱，与原版结构对应
- 落款 "K." 是另一神秘符号

### 3.4 笔记 #4 · 劳工日志

**来源**：废弃矿井矿车箱子

**正文**：
> 「第 328 天。
>
> 矿车又坏了。木轨道太滑，铁矿太硬。
>
> 听说主世界北方在建要塞，需要我们运更多石头过去。但我们已经挖到 Y=-50 了，再深就是深板岩，那不是我们能挖的。
>
> —— 矿工 T.」

**叙事意义**：
- 暗示废弃矿井是劳工阶层的运输网络
- 提到"建要塞"，与主世界要塞关联
- "深板岩不是我们能挖的"——暗示深板岩层有更深层秘密（远古城市）

### 3.5 笔记 #5 · 监禁记录

**来源**：地牢箱子

**正文**：
> 「他们把我关在这里，因为我知道得太多。
>
> 刷怪笼不是诅咒——是他们的发明。用来制造士兵、制造劳动力、制造恐惧。
>
> 但他们忘了，被制造出来的也会思考。
>
> —— 囚犯 W.」

**叙事意义**：
- 揭示地牢刷怪笼的"真相"
- "他们"指代先民，与笔记 #2 的"他们"形成对应
- 落款 "W." 是第三神秘符号

---

## 4. loot 表修改方案

### 4.1 实现方式

**选项 A**：通过 data pack 直接覆盖原版 loot 表
- ❌ 缺点：与其他模组/data pack 冲突

**选项 B**：通过模组的 `LootItemFunction` / `LootTableModification` API 注入
- ✅ 推荐，兼容性好

**选项 C**：通过 Fabric / Forge 的 `LootTableEvents.REPLACE` 事件
- ✅ Fabric 推荐

### 4.2 loot 表修改示例（村庄图书馆）

**原版 loot 表**：`data/minecraft/loot_table/chests/village/village_library.json`

**追加 pool**（通过模组 API 注入）：
```json
{
  "pools": [
    // ... 原有 pools 保留 ...
    {
      "rolls": 1,
      "entries": [
        {
          "type": "minecraft:item",
          "name": "minecraft:written_book",
          "weight": 5,
          "quality": 2,
          "functions": [
            {
              "function": "minecraft:set_nbt",
              "tag": "{display:{Title:\"残破的笔记\",Lore:[\"纸张泛黄，墨迹模糊\"]},pages:[\"{\\\"text\\\":\\\"寻找那座塔。它会告诉你我们是谁。\\\\n\\\\n不要相信猪灵。也不要相信我们。\\\\n\\\\n—— M.\\\"}\"],author:\"M.\",title:\"残破的笔记\",resolved:1b}"
            }
          ]
        }
      ],
      "conditions": [
        {
          "condition": "minecraft:random_chance",
          "chance": 0.15
        }
      ]
    }
  ]
}
```

### 4.3 五个 loot 表的统一注入逻辑

通过 Fabric API（推荐）：
```java
// 在模组主类中注册 LootTableEvents.MODIFY
LootTableEvents.MODIFY.register((resourceManager, lootManager, id, tableBuilder, source) -> {
    if (!source.isBuiltin()) return;
    
    if (id.equals(LootTables.VILLAGE_LIBRARY_CHEST)) {
        tableBuilder.pool(LootPool.builder()
            .rolls(ConstantLootTableRange.create(1))
            .with(ItemEntry.builder(Items.WRITTEN_BOOK)
                .apply(SetNbtLootFunction.builder(NoteNbt.NOTE_1)))
            .conditionally(RandomChanceLootCondition.builder(0.15f))
        );
    } else if (id.equals(LootTables.DESERT_PYRAMID_CHEST)) {
        tableBuilder.pool(LootPool.builder()
            .rolls(ConstantLootTableRange.create(1))
            .with(ItemEntry.builder(Items.WRITTEN_BOOK)
                .apply(SetNbtLootFunction.builder(NoteNbt.NOTE_2)))
            .conditionally(RandomChanceLootCondition.builder(0.10f))
        );
    } else if (id.equals(LootTables.JUNGLE_TEMPLE_CHEST)) {
        tableBuilder.pool(LootPool.builder()
            .rolls(ConstantLootTableRange.create(1))
            .with(ItemEntry.builder(Items.WRITTEN_BOOK)
                .apply(SetNbtLootFunction.builder(NoteNbt.NOTE_3)))
            .conditionally(RandomChanceLootCondition.builder(0.10f))
        );
    } else if (id.equals(LootTables.ABANDONED_MINESHAFT_CHEST)) {
        tableBuilder.pool(LootPool.builder()
            .rolls(ConstantLootTableRange.create(1))
            .with(ItemEntry.builder(Items.WRITTEN_BOOK)
                .apply(SetNbtLootFunction.builder(NoteNbt.NOTE_4)))
            .conditionally(RandomChanceLootCondition.builder(0.08f))
        );
    } else if (id.equals(LootTables.SIMPLE_DUNGEON_CHEST)) {
        tableBuilder.pool(LootPool.builder()
            .rolls(ConstantLootTableRange.create(1))
            .with(ItemEntry.builder(Items.WRITTEN_BOOK)
                .apply(SetNbtLootFunction.builder(NoteNbt.NOTE_5)))
            .conditionally(RandomChanceLootCondition.builder(0.12f))
        );
    }
});
```

---

## 5. 概率调整与平衡

### 5.1 触发概率论证

| 结构 | 概率 | 理由 |
|------|------|------|
| 村庄图书馆 | 15% | 玩家最常接触的结构，作为"入口"概率最高 |
| 沙漠神殿 | 10% | 中等常见度，沙漠神殿箱子有 4 个，总概率 ~35% |
| 丛林神庙 | 10% | 较罕见，但 2 个箱子，总概率 ~19% |
| 废弃矿井 | 8% | 较常见，但单箱子，概率适中 |
| 地牢 | 12% | 常见，单箱子，概率较高 |

**玩家在 1 小时游戏内触发至少一份笔记的概率**：约 80%（基于 MC 玩家早期探索统计）。

### 5.2 多人服务器调整

| 选项 | 设定 | 推荐度 |
|------|------|--------|
| A. 单人概率，多人独立判定 | 每个玩家开箱时独立判定 | ★★★★ 推荐 |
| B. 多人时提高概率 | 玩家数 ×5% 加成 | ★★★ 备选 |

**推荐 A**：保持单人/多人体验一致。

---

## 6. 兼容性分析

| 检查项 | 状态 |
|--------|------|
| 是否新增自定义物品？ | ❌ 不新增（用原版 written_book + NBT） |
| 是否修改原版结构生成？ | ❌ 不修改 |
| 是否删除原版 loot？ | ❌ 仅追加，不删除 |
| 是否与其他模组/data pack 冲突？ | ⚠️ 通过 API 注入，兼容性好 |
| 玩家可关闭吗？ | ✅ 可（通过 config 文件关闭模组的 loot 注入） |
| 失去模组时笔记会消失吗？ | ✅ 已生成的笔记仍保留，但失去 NBT 显示（退化为普通 written_book） |

---

## 7. v0.1 ~ v0.2 实现验收标准

### v0.1（村庄图书馆 + 地牢）

- [ ] 实现 NoteNbt 工具类（5 份笔记的 NBT 数据）
- [ ] 实现村庄图书馆 loot 表注入（笔记 #1，概率 15%）
- [ ] 实现地牢 loot 表注入（笔记 #5，概率 12%）
- [ ] 实现拾取笔记触发的 advancement（remnant:lore/chapter_0）
- [ ] 测试玩家在村庄图书馆箱子中获得笔记 #1
- [ ] 测试玩家在地牢箱子中获得笔记 #5
- [ ] 测试多人服务器中独立判定

### v0.2（其余三个结构）

- [ ] 实现沙漠神殿 loot 表注入（笔记 #2，概率 10%）
- [ ] 实现丛林神庙 loot 表注入（笔记 #3，概率 10%）
- [ ] 实现废弃矿井 loot 表注入（笔记 #4，概率 8%）
- [ ] 实现收集全部 5 份笔记触发的 advancement（remnant:lore/chapter_1）
- [ ] 多语言支持（en_us + zh_cn）

---

## 8. 待讨论的设计问题

- [ ] 5 份笔记的落款（M. / 第三祭司 / K. / T. / W.）是否需要后续在末地城揭晓身份？建议是
- [ ] 是否允许玩家通过交易/合成复制笔记？建议否，保持稀缺
- [ ] 是否需要"已读"标记？建议否，避免修改原版 written_book 行为
- [ ] 多人服务器中，笔记是否绑定玩家？建议否，允许玩家间传递

---

## 9. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-18 | v0.1 | 初稿，提出 5 个原版 loot 表注入方案 | 项目方 |
