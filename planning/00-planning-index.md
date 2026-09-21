# 规划文档索引

> 本目录存放 **Remnant / Echo 模组**的所有设计规划文档。
> 与 `00-overview/` ~ `14-official-derivatives/` 的**原文资料汇编**不同，本目录的文档是**项目方的设计决策与思考过程**，会随开发进度持续更新。

---

## 🎯 顶层设计原则（最高优先级）

### 原则 0：「优先原版，实在没辙才自定义，且必须与原版有关」

本模组的核心原则是**优先用原版实现**，**实在没辙才自定义**，且自定义内容**必须与原版有强关联**。

不追求 100% 零自定义——这是不现实的，叙事模组总需要承载文本的载体、视觉差异化。但**自定义必须是最后手段**，且**必须能论证与原版的强关联**。

#### 三级优先级

| 层级 | 优先级 | 触发条件 | 占比预期 | 示例 |
|------|--------|----------|----------|------|
| **L1 优先原版** | ★★★★★ | 默认首选 | ~80% | 用 `written_book` 承载叙事文本 |
| **L2 原版组合** | ★★★★ | L1 不足时 | ~15% | `written_book` + `advancement` + `tellraw` 组合实现"线索书解锁" |
| **L3 必要自定义** | ★★ | L1/L2 均不足，且满足必要性 + 关联性 | ~5% | 残破笔记作为 `written_book` 的子类型，用 `CustomModelData` 改纹理但保持书本行为 |

#### 判定流程

```
设计提案
    ↓
L1: 能否用纯原版物品/方块/机制承载？
    ├─ 能 → 用 L1 ✅
    └─ 否 → L2
L2: 能否用多个原版物品/方块/机制组合实现？
    ├─ 能 → 用 L2 ✅
    └─ 否 → L3
L3: 自定义是否满足以下两个条件？
    ├─ 1. 必要性：原版无任何方式可实现（需文档论证）
    └─ 2. 关联性：自定义内容必须与原版有强关联（视觉/机制/来源/数据/退化）
        ├─ 都满足 → 用 L3，记录到 planning/custom-items-registry.md ✅
        └─ 任一不满足 → 提案不通过，重新设计 ❌
```

#### L3 自定义的「关联性」标准

自定义内容必须满足**至少 2 项**以下条件才允许：

| 关联维度 | 说明 | 示例 |
|----------|------|------|
| **视觉关联** | 纹理基于原版资产修改 | 残破笔记基于 `written_book` 纹理加泛黄/烧焦效果 |
| **行为关联** | 行为机制与原版物品一致 | 残破笔记可右键阅读、可放入讲台、可复制 |
| **来源关联** | 通过原版 loot 表/合成配方获得 | 残破笔记从原版结构箱子中获取 |
| **数据关联** | NBT/数据结构基于原版 | 残破笔记的 NBT 结构基于 `written_book`，仅追加 `CustomModelData` |
| **退化关联** | 失去模组时仍能正常运作（变成原版物品） | 失去模组后残破笔记退化为普通 `written_book`，仍可阅读 |

#### L3 自定义的「永远禁止」清单

以下自定义内容**永远禁止**，无论关联性多强：

| 禁止项 | 原因 |
|--------|------|
| ❌ 新维度 | 原版无对应维度，无法关联 |
| ❌ 新生物 | 原版无对应生物，无法关联 |
| ❌ 新 Boss（作为新实体） | 原版 Boss 体系完整，新实体无法关联；如需 Boss 变体，必须复用原版 Boss 的 NBT |
| ❌ 新种族 | 原版无对应种族，无法关联 |
| ❌ 新文明（作为新概念） | 原版无对应文明；如需"先民文明"叙事，仅作为对原版留白的解读 |
| ❌ 改变原版生物 AI/掉落 | 破坏原版体验 |
| ❌ 新驯服/骑乘机制 | 破坏原版交互 |
| ❌ 新数值系统（如"灵气值"、"梦境值"） | 全新游戏机制，无原版依据 |

#### 判定示例

| 设计提案 | 判定 | 理由 |
|----------|------|------|
| 用 `written_book` + NBT 承载叙事文本 | ✅ **L1** | 直接用原版物品 |
| 在原版村庄图书馆 loot 表中追加 `written_book` 条目 | ✅ **L1** | 直接用原版 loot 表 |
| `written_book` + `advancement` + `tellraw` 组合实现线索书解锁 | ✅ **L2** | 原版机制组合 |
| 在 `mossy_stone_bricks` 上右键触发 `tellraw` 显示铭文 | ✅ **L2** | 原版方块 + 原版触发器 |
| 自定义"残破笔记"物品，用 `CustomModelData` 改纹理但保持 `written_book` 行为 | ✅ **L3** | 满足视觉/行为/数据/退化 4 项关联 |
| 自定义"先民石碑"方块，材质基于原版石砖 + 雕刻纹理 | ✅ **L3** | 满足视觉关联；但需论证 L1/L2 不可行（为何不能直接用 `chiseled_stone_bricks`?） |
| 自定义"先民储藏室"结构，作为原版废弃矿井的变体追加生成 | ⚠️ **L3 待论证** | 必须论证为何不能在原版废弃矿井 loot 表中追加 |
| 自定义"守门人"Boss 作为末影龙的 NBT 变体（调整 Phase 行为） | ✅ **L3** | 复用原版 Boss，满足数据/行为关联 |
| 自定义"灵魂能量"机制作为新数值系统 | ❌ 不通过 | 全新游戏机制，无原版依据 |
| 自定义"虚空水晶"方块作为新材质 | ❌ 不通过 | 完全新材质，无原版关联 |
| 自定义"亚特兰蒂斯神殿"作为独立新结构 | ❌ 不通过 | 完全独立结构，与原版建筑风格冲突 |
| 自定义"光之子"作为新种族 | ❌ 不通过 | 完全新生物，无原版依据 |

#### L3 决策记录

所有 L3 决策必须记录到 `planning/custom-items-registry.md`，包含：
- 自定义内容名称
- 必要性论证（为何 L1/L2 不可行）
- 关联性论证（满足哪几项关联标准）
- 退化方案（失去模组时的行为）
- 决策日期与决策者

---

### 原则 1：以原版世界观为主

- 所有叙事内容**必须基于原版已有设定**（建筑、生物、物品、Boss）
- 不引入官方未提及的新种族、新文明、新纪元名称（除非作为"对原版留白的解读"）
- 模组的设定本质是**对原版留白的合理串联**，而非**新世界观的创造**

### 原则 2：贴合原版留白逻辑

- 不强行填补官方未解释的内容
- 只做**合理串联**：把原版零散的线索（如凋灵骷髅头颅、远古城市门框、紫珀砖工艺一致）用一条叙事线索串起来
- 留白处继续留白，不强行解释

### 原则 3：碎片化叙事

- 玩家在探索中自行拼凑真相
- 不出现对话、过场、引导箭头
- 叙事文本通过 `written_book`、`advancement` 提示、`tellraw` 命令呈现

### 原则 4：三界同源

- 主世界、下界、末地的建筑与生物源自同一支远古先民文明
- 这一设定**优先通过串联原版遗迹的石砖工艺一致性呈现**，而非通过新增自定义结构展示
- 如必须新增自定义结构作为叙事载体，需符合 L3 自定义标准

### 原则 5：基于官方衍生作品可参考，但以原版为准

- 可参考《Minecraft: Dungeons》《Minecraft: Legends》等官方衍生作中的设定
- 但以原版为准，衍生作的设定仅作叙事串联的辅助参考

---

## 📂 文档列表

| 编号 | 文档 | 主题 | 状态 |
|------|------|------|------|
| 00 | [`00-planning-index.md`](./00-planning-index.md) | 规划总索引 + 顶层设计原则 | 🟢 v0.3 |
| 01 | [`01-spawn-point-design.md`](./01-spawn-point-design.md) | 玩家出生点叙事设计（原版 loot 表扩展） | 🟡 v0.2 |
| 02 | [`02-story-timeline-plan.md`](./02-story-timeline-plan.md) | 故事时间线规划（六大纪元） | 🟡 v0.2 |
| 03 | [`03-player-journey-map.md`](./03-player-journey-map.md) | 玩家体验路径图（十阶段 + 认知锁） | 🟡 v0.2 |
| 04 | [`04-auto-sync-strategy.md`](./04-auto-sync-strategy.md) | 自动同步方案（GitHub Action） | 🟢 计划中（v0.5+） |
| 05 | [`05-clue-book-system.md`](./05-clue-book-system.md) | 线索书系统设计（Patchouli 集成 + advancement 触发） | 🟡 v0.1 |
| 06 | [`06-cognitive-lock-mechanism.md`](./06-cognitive-lock-mechanism.md) | 认知锁机制（advancement 详细配置） | 🟡 v0.1 |
| 07 | [`07-boss-narrative-binding.md`](./07-boss-narrative-binding.md) | Boss 叙事绑定（原版 Boss 击杀触发记忆回放） | 🟡 v0.1 |
| 08 | [`08-music-disc-unlock-order.md`](./08-music-disc-unlock-order.md) | 唱片解锁顺序与剧情对应 | 🟡 v0.1 |
| 09 | [`09-village-loot-extension.md`](./09-village-loot-extension.md) | 5 个原版 loot 表详细配置 | 🟡 v0.1 |
| 10 | [`10-custom-items-registry.md`](./10-custom-items-registry.md) | L3 自定义物品登记表（论证 + 关联性 + 退化方案） | 🟡 v0.1 |
| 11 | [`11-localization-strategy.md`](./11-localization-strategy.md) | 多语言支持策略（首发 zh_cn + en_us，v1.0 前 8 语言） | 🟡 v0.1 |
| 12 | [`12-release-roadmap.md`](./12-release-roadmap.md) | 发布路线图（v0.1 ~ v1.0 全里程碑 + Gantt 图） | 🟡 v0.1 |
| 13 | [`13-save-compatibility.md`](./13-save-compatibility.md) | 存档兼容性策略（升级 / 卸载 / 重装三场景） | 🟡 v0.1 |
| 14 | [`14-trial-chamber-narrative.md`](./14-trial-chamber-narrative.md) | 试炼密室叙事（100% L1/L2，先民挑战设施） | 🟡 v0.1 |
| 15 | [`15-netherite-enchantment-essence.md`](./15-netherite-enchantment-essence.md) | 下界合金 / 附魔本质叙事（维度稳定材料 + 灵魂能量注入） | 🟡 v0.1 |
| 16 | [`16-worldview-overview.md`](./16-worldview-overview.md) | 面向读者的世界观总纲（三界同源 + 四大领域） | 🟡 v0.1 |
| 17 | [`17-mod-introduction-copy.md`](./17-mod-introduction-copy.md) | 对外模组介绍文案（一句话 / 段落 / 完整 / FAQ / 媒体） | 🟡 v0.1 |
| 18 | [`18-overworld-narrative.md`](./18-overworld-narrative.md) | 主世界叙事细化（遗迹/种族/事件矩阵 + 笔记 #15-#18 + 社区理论） | 🟡 v0.1 |
| 19 | [`19-nether-narrative.md`](./19-nether-narrative.md) | 下界叙事细化（遗迹/种族/事件矩阵 + 笔记 #19-#22 + 12 个社区理论） | 🟡 v0.1 |
| 20 | [`20-end-narrative.md`](./20-end-narrative.md) | 末地叙事 + 真结局核心（笔记 #23-#26 + End Poem 重新解读 + 13 个社区理论） | 🟡 v0.1 |
| 21 | [`21-narrative-causality-map.md`](./21-narrative-causality-map.md) | 模组叙事因果链总图（含完整 Mermaid flowchart + 思维导图建议） | 🟡 v0.1 |
| 22 | [`22-design-questions-answers.md`](./22-design-questions-answers.md) | 设计问答：11 个核心问题讨论与建议（待项目方审核） | 🟡 v0.1 |
| 23 | [`23-design-followups.md`](./23-design-followups.md) | 设计问答后续：重名查询+配乐重评+支线叙事建议 | 🟡 v0.1 |
| 24 | [`24-design-followups-2.md`](./24-design-followups-2.md) | 设计问答第三批：命名确认 Remnant Echo+定位扩展+主线Boss+预渲染视频否决+光影提示+粒子特效 | 🟡 v0.1 |
| 25 | [`25-design-followups-3.md`](./25-design-followups-3.md) | 设计问答第四批：命令工程化+叙事生物变体+动画策略 | 🟡 v0.1 |

---

## 📅 后续将补充的规划文档（计划中）

- `26-testing-matrix.md` — 测试矩阵（功能 / 兼容性 / 多人 / 长存档测试）
- `27-fabric-loader-selection.md` — 加载器选型论证（Fabric vs NeoForge）
- `28-community-contribution-guide.md` — 社区贡献指南（翻译 PR 流程）

> **注**：原计划的 `11-localization-strategy.md` / `12-release-roadmap.md` / `13-save-compatibility.md` 已于 2026-09-18 完成，后续 `18-21` 也于同日完成，`22/23/24/25-design-followups-2/3` 于 2026-09-21 完成，本节列表为后续待补。

---

## 📌 修订规则

- 规划文档**重大变更**需在文档末尾的「修订历史」记录
- 旧版本不删除，保留为 `01-spawn-point-design-v0.1.md` 等形式
- 与代码实现冲突时，以**代码实现**为准并反向更新文档
- 任何新增/修改设计必须先通过「原则 0」的 L1/L2/L3 判定流程

---

## 📝 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-18 | v0.1 | 初稿，确立「补不是添」原则 | 项目方 |
| 2026-09-18 | v0.2 | 细化为三级优先级（L1/L2/L3）与关联性标准 | 项目方 |
| 2026-09-18 | v0.3 | 新增 L3 决策记录机制与判定示例；明确"永远禁止"清单 | 项目方 |
| 2026-09-18 | v0.4 | 文档列表新增 11~17（localization / release-roadmap / save-compat / trial-chamber / netherite-enchant / worldview-overview / mod-introduction）；后续待补清单更新为 18~20 | 项目方 |
| 2026-09-18 | v0.5 | 文档列表新增 18~21（overworld-narrative / nether-narrative / end-narrative / narrative-causality-map）；后续待补清单更新为 22~24；新增 15-community-lore 社区传说汇编章节（基于 8 次真实 web 搜索） | 项目方 |
| 2026-09-21 | v0.6 | 文档列表新增 22（design-questions-answers，回应项目方 9-20 夜间提出的 11 个核心设计问题）；后续待补清单更新为 23~25 | 项目方 |
| 2026-09-21 | v0.7 | 文档列表新增 23（design-followups，重名查询+配乐重评+支线叙事建议，基于 3 次真实 web 搜索）；后续待补清单更新为 24~26 | 项目方 |
| 2026-09-21 | v0.8 | 文档列表新增 24（design-followups-2，命名确认 Remnant Echo+定位扩展+主线Boss+预渲染视频否决+光影提示+粒子特效）；后续待补清单更新为 25~27；命名最终确认为 Remnant Echo | 项目方 |
| 2026-09-21 | v0.9 | 文档列表新增 25（design-followups-3，命令工程化 E1/E2/E3+4 个 L3 自定义叙事 NPC+L1/L2/L3 三级动画策略）；后续待补清单更新为 26~28 | 项目方 |
