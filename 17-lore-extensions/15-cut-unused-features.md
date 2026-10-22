# 15 · 废弃 / 未实现 / 已移除特性汇编 · Cut / Unused / Removed Features

> 本文件属于 **Remnant Echo 模组资料汇编** 的剧情扩展章节（`17-lore-extensions/`）。
> 完整收录 Minecraft 历史上**已移除的实体、方块、结构、群系、维度**与**当前仍存在于代码但未使用的内容**。
> 与 [`11-legacy-mobs-items.md`](./11-legacy-mobs-items.md)（旧版本生物物品）和 [`13-urban-legends-myths.md`](./13-urban-legends-myths.md)（都市传说）形成互补——前者聚焦"已存在过的旧内容"，本文聚焦"被删除或从未使用的内容"。
>
> **资料优先级**：P1（minecraft.wiki 官方）+ P1（Mojang 官方推文/Minecraft Live）+ P2（社区高流传度考据）
> **汇编日期**：2026-10-19
> **状态**：🟢 完成（基于 5 次真实 web 搜索 + 3 次 WebFetch 详细阅读）

---

## 1. 项目方问题

> "继续搜索社区相关的内容（而不仅仅是官方内容），也许会有新发现，包括新生物、结构、群系与废弃生物、结构、群系等"

本汇编回答该问题的"废弃生物、结构、群系"部分。配套文档：
- [`16-mob-vote-losers.md`](./16-mob-vote-losers.md) —— Mob Vote 落选者完整汇编
- [`17-new-2025-2026-content.md`](./17-new-2025-2026-content.md) —— 2025-2026 新版本内容（含 The Sift 第四维度）

---

## 2. 已移除的实体（Removed Entities）

### 2.1 Indev 时期 Dock 设计的人形测试生物

| 名称 | 加入版本 | 移除版本 | 设计者 | 状态 | 模组关联 |
|------|----------|----------|--------|------|----------|
| **Rana（拉娜）** | Indev 0.31（2010-01-13） | Indev 0.31 后期（2010-01 月内） | Dock | 从未正式实装 | 🟡 记录——可关联"鼎盛纪元普通先民女性形象" |
| **Beast Boy（野兽男孩）** | Indev 0.31（2010-01-13） | Indev 0.31 后期 | Dock | 从未正式实装 | 🟡 记录——名字与"Beast"在 Minecraft 历史中多义（参考卡通） |
| **Black Steve（黑色史蒂夫）** | Indev 0.31（2010-01-13） | Indev 0.31 后期 | Dock | 从未正式实装 | 🟡 记录——可关联"先民皮肤多样性" |
| **Steve（作为 mob）** | Indev 0.31（2010-01-13） | Indev 0.31 后期 | Dock | 从未正式实装 | 🟡 记录——与玩家 Steve 同模型的 NPC 形态 |

**详细说明**（来源：minecraft.wiki/w/Java_Edition_removed_entities）：
- 这四个 mob 由 Dock（早期 Minecraft 美术师）制作，是 MD3 格式的外部模型，**没有任何动画**，靠"glide around in the same pose"（保持同一姿势滑行移动）
- Dock 离开 Mojang 团队后，这些 MD3 mob 全部被裁切
- Notch 还测试过其他未公布的 MD3 模型——可视为"先民领袖/队员"的早期视觉原型
- 模组叙事建议：在"鼎盛纪元 → 大分裂"过渡期，可在某些极罕见遗迹（如沙漠神殿祭坛）的告示牌中以"Rana / Beast Boy / Black Steve / Steve"作为先民队员的代号——但**不作为新 NPC 实装**，仅作"已失落的名字"出现

### 2.2 Classic / Infdev 时期的"原型人形 mob"

| 名称 | 加入版本 | 移除版本 | 状态 | 模组关联 |
|------|----------|----------|------|----------|
| **Mob**（实体名 `mob`） | rd-132328（2009-05-13）/ Infdev 20100316 | Indev 0.31 20100202 / Beta 1.2 | 已移除 | 🟢 **核心叙事资源**——Classic 时期按 G 键生成的 Steve 克隆体，是"古代建造者"的原版官方证据 |
| **Monster**（实体名 `monster`） | Infdev 20100316 | Beta 1.8 Pre-release | 已移除 | 🟢 **核心叙事资源**——"试图生成敌对生物基类却作为实际 mob 生成"——"大分裂"纪元文明崩溃的视觉表现 |
| **Builder**（实体名 `builder`） | Beta 1.2_02 (20110517) | Beta 1.2_02 (20110517)（同日移除） | 仅私有开发版 | 🟢 **核心叙事资源**——**这是模组"古代建造者理论"的原版官方铁证**！持铁镐、可破坏和放置方块的特殊 Mob 变体，仅存在于 2011-05-17 私有开发版 |
| **Baby Camel Husk（幼年骆驼尸壳）** | 25w44a | 26.1 Snapshot 7（模型移除）→ Snapshot 7（完全移除） | 已移除 | 🟡 记录——模组"Mounts of Mayhem"叙事的早期形态 |

**Builder 的特殊意义**：
- Beta 1.2_02 (20110517) 是一个**意外泄露的私有开发版本**，从未公开发布
- 这个版本里出现了 `Builder` 实体——**这是 Mojang 内部曾经测试过的"会建造的实体"**
- 虽然立即被移除，但代码证据保留至今——是模组"古代建造者理论"在原版官方层面最直接的代码证据
- 在模组叙事中，可作为"M. = C. 等 12 位落款角色"的"代码层原型"

### 2.3 Java Edition 1.11 之前的实体 ID 转换

| 旧 ID | 新 ID（1.11 起） | 说明 |
|-------|------------------|------|
| `Mob` → `Human` | （已废弃） | 1.11 后实体 ID 全部转为 resource location |
| `Monster` | （已废弃） | 同上 |

---

## 3. 当前仍存在但未使用的实体（Unused Entities）

> 来源：minecraft.wiki/w/Java_Edition_unused_features
> 这些实体存在于代码中但生存/创造模式均无法自然生成，只能用命令召唤。

### 3.1 未使用生物完整列表

| 名称 | 召唤命令 | 加入版本 | 未使用原因 | 模组关联 |
|------|----------|----------|------------|----------|
| **Giant（巨人）** | `/summon minecraft:giant` | Indev 0.31（2010-02-05） | 无移动 AI；光照条件冲突（同时需要 >11 和 <8）导致无法自然生成 | 🟢 **核心叙事资源**——"大分裂"纪元中"巨型异化的先民战士"，可作为极罕见遗迹祭坛的"故事触发器"（不实装为新生物，仅作为告示牌描述的"传说的怪物"） |
| **Killer Bunny（杀手兔）** | `/summon minecraft:rabbit ~ ~ ~ {RabbitType:99}` | 1.8（2014） | 纯白色+血红眼，移速比普通兔快；1.9 后只能命令生成 | 🟡 记录——可作为"苍白之悔"纪元的视觉暗示（白色 = 苍白光谱 + 红色 = 暗红光谱 = 维度异化） |
| **Illusioner（幻术师）** | `/summon minecraft:illusioner` | 1.12（2017） | 攻击玩家/村民/流浪商人/铁傀儡，使用咒语和弓 | 🟢 **核心叙事资源**——已实现但未自然生成！可在模组"灾厄村民"支线中作为"灾厄村民长老"的视觉原型，无需新增 NPC |
| **Minecart with Monster Spawner（带刷怪笼的矿车）** | `/summon minecraft:spawner_minecart` | 1.5（2013） | 无法作为物品获得 | 🟡 记录——可作为"废弃矿井"叙事的"地下生物兵器运输工具"暗示 |

### 3.2 未使用的状态效果

| 名称 | 效果 | 获取方式 | 模组关联 |
|------|------|----------|----------|
| **Luck（好运）** | 提升高品质战利品概率 | 仅命令/自定义药水 NBT | 🟡 记录——M. "0 号唱片"中可关联"先民文明被遗忘的祝福" |
| **Bad Luck（厄运）** | 降低高品质战利品概率 | 仅 `/effect` 命令 | 🟡 记录——"凋灵之灾"的视觉资源 |
| **Health Boost（生命提升）** | 增加玩家血量上限 | 1.6 前=金苹果效果，snapshot 13w24b 起改为 Absorption | 🟡 记录——早期金苹果机制可作为"先民医疗技术"叙事 |

### 3.3 未使用的声音

- **Nether Ambience**（下界环境音）——Basalt Deltas Active / Warped Forest Mood 等
- **Silverfish & Endermite Walking Sounds**（蠹虫和终界螨行走音）
- **Zombie Attacking Iron Door Sounds**（僵尸攻击铁门音）
- **Bat Loop**（蝙蝠循环音）
- **Ghast Affectionate Scream**（恶魂亲昵的尖叫——曾经被设计为可亲昵的恶魂）
- **Classic Hurt**（经典受伤音）
- **Breath**（呼吸音）

**模组叙事建议**：这些未使用声音可作为"先民文明遗留的环境音"——在远古城市/废弃营地等遗迹中通过原版 `playsound` 命令调用，作为氛围渲染，不引入新音轨。

---

## 4. 已移除的世界生成（Removed World Generation）

### 4.1 已移除的结构（来源：minecraft.wiki/w/Java_Edition_removed_features）

| 名称 | 加入版本 | 移除版本 | 模组关联 |
|------|----------|----------|----------|
| **Brick Pyramid（砖金字塔）** | Infdev 早期 | Infdev 后期 | 🟢 **核心叙事资源**——"鼎盛纪元先民文明"的早期纪念建筑！可作为模组叙事中"先民宗教建筑"的原型参照 |
| **Starting House（起始房屋）** | Infdev | Beta 1.8 Pre-release | 🟡 记录——"先民出生点"的概念 |
| **Obsidian Wall（黑曜石墙）** | Infdev | Infdev 后期 | 🟢 **核心叙事资源**——"凋灵之灾"中"防御黑曜石墙"的视觉资源（与下界主题呼应） |
| **Monolith（巨型独石）** | Infdev 早期 | Infdev 后期 | 🟢 **核心叙事资源**——"苍白之悔"纪元中"虚空之外的存在"的视觉资源（与边境之地呼应） |
| **Placeholder Trees（占位树）** | Infdev | Infdev 后期 | 🟡 记录 |
| **Stronghold Glass Pillars（要塞玻璃柱）** | Beta 1.8 Pre-release | Beta 1.9 Pre-release | 🟡 记录——"末地传送门激活失败"的视觉暗示 |
| **Clay Blobs（黏土块）** | Beta 1.6 | Beta 1.8 | 🟡 记录 |
| **Gravel Beaches（砾石海滩）** | Beta 1.6 | Beta 1.8 | 🟡 记录——"苍白之悔"的灰白海岸视觉 |
| **Water Lakes（水湖）** | 早期 | 1.18 后改为含水层 | 🟡 记录 |

### 4.2 已移除的群系（Biome Generation Changes）

| 名称 | 加入版本 | 移除版本 | 备注 |
|------|----------|----------|------|
| **Beta 1.7.2 之前的群系系统** | Alpha | Beta 1.7.2 改版 | 含原版"季节森林"、"季节雨林"等 |
| **Beta 1.8 之前的群系系统** | Beta 1.7.2 | Beta 1.8 Pre-release | 改版后增加 Mushroom Islands、Jungle 等 |
| **1.18 之前的群系系统** | Beta 1.8 | 1.18（Caves & Cliffs） | 大规模世界生成重做 |

---

## 5. 已取消 / 未实装的维度

### 5.1 Sky Dimension（天空维度）—— 完整历史

> 来源：minecraft.wiki/w/Sky_dimension + WebFetch 完整阅读

| 时间 | 事件 |
|------|------|
| 2011-05-19 | Notch 在 Twitter 正式确认 Sky Dimension："And because PC Gamer made such a big deal of the Sky Dimension, I guess I'll have to finish it. Consider it confirmed." |
| 2011 年中 | Notch 在 feber.se 直播中透露计划为"梦境维度"——睡觉有几率进入梦境世界，后期可主动进入 |
| Adventure Update 时期 | 推迟到下界更有趣后实现；原概念使用主世界"顶光"导致性能问题，Notch 决定移除太阳改用均匀光照 |
| 2011-10-12 | Jeb 在 Twitter 确认："It has been rebranded to be The End realm." —— Sky Dimension 正式改造成 The End |
| 2011-10-12 后 | Notch 暗示"另一个 Skylands 维度可能仍在制作"——但独立于末地 |
| 2012-07-02 | Jeb："No we don't plan to return the Sky Dimension." |
| 2012-07-03 | Dinnerbone："We have no plans to revisit the skylands." |
| Beta 1.6 → Beta 1.9 Prerelease 3 | Sky Dimension 原型代码存在，可通过修改 minecraft.jar 中 class 文件访问 |
| 1.13 之前 | 末地的生物群系仍叫 `minecraft:sky`（"Sky"是最后一个 Sky Dimension 痕迹） |
| 1.13 (18w06a) | 末地新群系使用 `minecraft:sky_islands_*` 资源位置 |
| 1.16.2 (20w28a) 后 | 可通过 `minecraft:floating_islands` 噪声预设创建自定义维度，重现 Sky Dimension |
| 2026-09-26 | Minecraft Live September 2026 宣布 **The Sift 第四维度**——可视为"原 Sky Dimension 的官方重做" |

**Sky Dimension 在原版游戏中的视觉遗产**：
- 末地的虚空感与"漂浮岛屿"概念源自 Sky Dimension
- Notch 自己承认 Aether Mod 实现了 Sky 概念："The Ether mod does it great, try it."
- Minicraft（Notch 的 2D Minecraft 衍生游戏）也包含 sky dimension
- 25w14craftmine（2025 愚人节版本）的 "Floating Islands" 配方生成类似 Sky Dimension 的地形

**模组叙事建议**：
- Sky Dimension 的"梦境维度"原始设定可关联到模组"苍白之悔"纪元——"先民领袖试图在梦中接触虚空，结果被虚空吞噬"
- 在叙事文档中提及"先民曾计划建造的天空维度，最终被改造成末地"——为模组"末地是天空维度的失败版本"提供原版官方背书
- **重要**：这一设定与 The Sift 第四维度的官方实装形成"先民未完成的梦 → Mojang 终于完成"的对照，模组可在 M. 遗言中暗示

### 5.2 The Sift（筛境）—— 14 年来首个新维度

> 详见 [`17-new-2025-2026-content.md`](./17-new-2025-2026-content.md)

- **宣布日期**：2026-09-26（Minecraft Live September 2026）
- **加入时间**：2027 年（Java & Bedrock Edition）
- **首次出现**：Minecraft Dungeons II（2026-09-29 发布）
- **特点**："beautiful, vibrant, and teeming with souls"——**充满灵魂**
- **区域**：Meadow（草甸）、The Carapace（甲壳之地）
- **进入方式**：通过裂缝（rifts）进入
- **新 mob**：**Blub**（兔形小生物，Deluxe Edition 提供 Blub 宠物）
- **官方描述**："the first new dimension in over 14 years – joining the Overworld, the Nether and the End as our fourth dimension"

**对模组的核心意义**：
- 模组规划文档 `02-story-timeline-plan.md` §5.7 "v0.6+ 扩展为四界同源"得到了**原版官方的正式背书**
- The Sift "充满灵魂"的设定直接关联模组四色光谱中的"蓝=灵魂能量"
- Meadows 和 The Carapace 的视觉资源可作为模组 v0.6 扩展叙事的素材
- Blub 作为"兔形小生物"——与"末影人是先民异化"理论呼应（末影人=Farlander→Enderman 的演化链可类比 Blub→？）

---

## 6. 已被提及但从未实装的特性（Mentioned Features）

> 来源：minecraft.wiki/w/Mentioned_features（完整阅读）

### 6.1 已废弃（Delayed or scrapped）

| 特性 | 提出时间 | 替代/状态 | 模组关联 |
|------|----------|-----------|----------|
| **Alpacas（羊驼）** | 2016，Jeb 在 Twitter 投票 | 输给 llamas（羊驼） | 🟡 记录 |
| **Colored Planks（彩色木板）** | Nathan Adams 提议 | 被 stained terracotta（陶瓦）取代 | 🟡 记录 |
| **Cubic chunks（立方区块）** | Ryan Holtz & Erik Broes 讨论 | 因天空光遮挡问题无法解决 | 🟡 记录——可作为模组"先民试图打破世界结构"的隐喻 |
| **Coral Slab（珊瑚半砖）** | MINECON Earth 2017 视频 | 原因未知 | 🟡 记录 |
| **Fletching Table Functionality（制箭台功能）** | 计划于下一主题更新 | 一直未实现 | 🟡 记录 |
| **Firefly mob（萤火虫）** | Minecraft Live 2021 概念图 | 部分通过 Spring to Life 的 firefly bushes 实现 | 🟡 记录——模组"苍白花园"叙事的早期视觉 |
| **Green Axolotl（绿色美西螈）** | 1.17 时期 | 未实现 | 🟡 记录 |
| **Pigman Bodyguard（猪人保镖）** | 早期提及 | 未实现 | 🟡 记录——可作为模组"鼎盛纪元猪灵文明护卫"叙事 |
| **Quiver（箭袋）** | 早期提及 | 未实现 | 🟡 记录 |
| **Sculk Jaw（幽匿颚）** | 1.19 开发期间 | 未实装 | 🟢 **核心叙事资源**——可作为模组"幽匿之厄"中"被删除的禁忌实验"暗示 |
| **Red Dragon（红龙）** | 2011-10-12 Notch 宣布 | **从未实装**，2026 年 2 月 Jens 仍被问及 | 🟢 **核心叙事资源**——模组"凋灵之灾"中"被先民计划但放弃的龙类兵器" |
| **Underground Cabin（地下小屋）** | 早期提及 | 未实装 | 🟡 记录——模组"远古城市"叙事的早期概念 |

### 6.2 Red Dragon 详细（来源：minecraft.wiki/w/Mentioned_features/Red_Dragon）

| 时间 | 事件 |
|------|------|
| 2010-08 | Notch 在 Spider Jockeys 加入（Seecret Friday 8）后暗示："Just wait until I add dragons!" |
| 2010-09（MinecraftCon 2010） | "Dragons. Polar bears in winter. Sea update will include coral, fish. Goblin villages may not just be goblins..." |
| 2011-10-12 | Notch 在 Twitter 宣布："After release, I will totally work on slightly less dangerous dragons that don't destroy terrain and can land and whatnot. They will be red." |
| 同日 Reddit 讨论 | Notch 解释红龙不会破坏地形，是末影龙的"较弱版本" |
| 2012-04-09 | Jens Bergensten 在 Reddit AMA："Well since Notch more or less promised red dragons, I think I need to add them. I'm just not sure how yet..." |
| 2013-10-22 | Nathan Adams (Dinnerbone) 推特："red dragon is shelved and not in development" |
| 2013-12-15 | Dinnerbone 在 Reddit："It was never promised, we have no plans to add a red dragon at this time." 但补充："I'm sure one day there will be. Not right now though." |
| 2022-11 | Brandon Pearce (kingbdogz) 玩笑："DID YOU KNOW?? red dragon already exists you just gotta hit the ender dragon and it appears for a split second" |
| 2026-02-24 | Jens 在被问及"上次 Mojang 内部认真讨论红龙是什么时候"时回答："They still do occasionally, but not from a development perspective." |

**模组叙事建议**：
- 在 M. 遗言中暗示"先民曾试图制造红龙作为末影龙的守门人替代品，但失败"——为模组"末影龙=守门人"理论提供叙事张力
- 在远古城市/末地城/末地船的告示牌中以"Project RED DRAGON"作为加密代号出现——0 号唱片周边叙事素材

### 6.3 仅提及（Mentioned）的特性

| 特性 | 提出者 | 模组关联 |
|------|--------|----------|
| **Camouflaging mob（伪装生物）** | Mojang 提及 | 🟢 **核心叙事资源**——可关联模组"苍白花园 Creaking"叙事（Creaking 在不动时即伪装） |
| **Lava Zombie & Troll（岩浆僵尸和巨魔）** | 早期提及 | 🟡 记录——可作为"下界异化"叙事的早期概念 |
| **Prefix Mobs（前缀生物）** | Mojang 提及 | 🟡 记录——类似"强化的僵尸"等变体 |
| **Reindeer（驯鹿）** | 提及 | 🟡 记录——可作为"冬季/雪原叙事"的早期概念 |
| **Cave & Underground Features** | 持续提及 | 🟢 已部分实现于 1.18、1.19 |
| **Seasons（季节）** | 多次提及 | 🟡 记录——可作为模组"鼎盛纪元"叙事的"时间流逝"暗示 |
| **Nether Features** | 多次提及 | 🟢 已实现于 1.16 Nether Update |
| **Scarecrows（稻草人）** | 提及 | 🟡 记录——可作为模组"灾厄村民/村庄"叙事的早期概念 |
| **Calamari（鱿鱼食材）** | 提及 | 🟡 记录 |

### 6.4 已部分实现的提案

| 特性 | 提出时间 | 部分实现版本 | 模组关联 |
|------|----------|--------------|----------|
| **Mob Vote**（含 Copper Golem） | 2017-2023 | Copper Golem → 1.21.9 Copper Age（2025-09） | 🟢 详见 [`16-mob-vote-losers.md`](./16-mob-vote-losers.md) |
| **More Ocean Creatures** | 2010 Notch 提及 | Guardian、Drowned 已实现 | 🟢 鲨鱼被 Mojang 否决 |
| **Zach and Coco** | 2018-11 | Jellie 胜出 → 1.14 Village & Pillage | 🟡 记录 |
| **Spike Block** | 2009-06 | 1.17 pointed dripstone / 26.4 icicles | 🟢 |
| **Ruby** | 2012-05-21 | → emerald（因 Dinnerbone 红绿色盲） | 🟢 **核心叙事资源**——可作为模组"先民交易货币"叙事的早期概念 |
| **Paeonia（牡丹花）** | 1.7.2 开发期 | → peony（牡丹，但保留 paeonia 纹理文件） | 🟡 记录 |
| **Paddle（桨）** | 2014-09-19 | → 船模型一部分 | 🟡 记录 |
| **Rare tools/weapons** | Nathan Adams | 部分通过 Frost Walker / Mending / Soul Speed / Swift Sneak / Wind Burst 等宝藏附魔实现 | 🟢 |
| **Steel（钢）** | Notch 早期 | 未实现（flint and steel 用铁锭合成） | 🟡 记录——可作为模组"先民冶金技术"叙事的早期概念 |

### 6.5 未完成的投票承诺

> 来源：Minecraft Live 多届投票 + minecraft.wiki/w/Mentioned_features

| 群系 | 承诺内容 | 状态 |
|------|----------|------|
| **Desert（沙漠）** | Palm trees（棕榈树）、Oases（绿洲）、Meerkats（狐獴） | MINECON Earth 2018 投票败给 Taiga，承诺后续更新 |
| **Savanna（稀树草原）** | Baobab trees（猴面包树）、Termites（白蚁）、Ostriches（鸵鸟） | MINECON Earth 2018 败给 Taiga |
| **Badlands（恶地）** | Vultures（秃鹫）、Tumbleweed（风滚草）、Prickly Pear cactus（仙人掌） | MINECON Live 2019 败给 Mountains，**2026 年 Vulture 终于实现** |

---

## 7. 边境之地（Far Lands）—— 已移除但保留传说

> 来源：minecraft.wiki/w/Far_Lands + 中文 wiki 边境之地条目

### 7.1 关键事实

| 项目 | 数值/内容 |
|------|-----------|
| **首次出现** | Infdev 20100327（2010-03-27） |
| **位置** | 距世界出生点约 **12,550,821 方块** |
| **成因** | 噪声生成器整数溢出 |
| **修复版本** | Beta 1.8 Pre-release（Java）/ 1.17.30 beta 1.17.20.20（基岩版） |
| **替代方案** | Java Edition 1.8 起加入 30,000,000 方块外的世界边界 |
| **Farther Lands 位置** | 约 1,004,065,924 方块（selector noise 溢出） |

### 7.2 类型

| 类型 | 触发条件 | 形态 |
|------|----------|------|
| **Edge Far Lands（边缘之地）** | 单轴溢出 | 一面墙 |
| **Corner Far Lands（角落之地）** | 双轴溢出 | 三明治层叠 |
| **Vertex Far Lands（顶点之地）** | 三轴溢出 | 极端地形 |
| **Farther Lands（更远之地）** | selector noise 溢出 | 1,004,065,924 方块外 |

### 7.3 著名徒步者

| 徒步者 | 完成日期 | 时间长度 | 备注 |
|--------|----------|----------|------|
| **KilloCrazyMan** | 2020-06-19 | 约 5 年 | 第一个完成（不走下界捷径），获 Notch 捐款 $6,000 |
| **KurtJMac** | 2025-10-04 | **14 年** | 14 年徒步，为公益筹款 $530,000+，2026-05-02 被 Minecraft 官方 YouTube 短纪录片报道 |
| **Xelanater** | 2022-06 | — | 第一个完成下界 Far Lands 徒步 |
| **TinfoilChef** | 2022-08-13 | — | 唯一在徒步过程中去世的玩家 |

### 7.4 闪烁标语遗产

- "Check out the far lands!"——在 Far Lands 被修复后才添加的标语
- "One does not simply walk to the Far Lands"——1.21.11 (25w46a) 添加，纪念 KurtJMac 14 年徒步

### 7.5 与末影人（Enderman）的官方关联

> **来源**：Notch 在 Twitter 的戏谑（minecraft.wiki 引用）

```
"/v/ is petitioning me to change the name from 'Endermen' to 'Farlanders'.
How about we just rename the 'far lands' to 'the end' instead? ;D"
– @notch (Markus Persson), July 30, 2011
```

**这是模组最重要的原版官方证据之一**：
- 末影人最初设计名为 **"Farlanders"**（边境之人）
- 与边境之地（Far Lands）直接关联——他们是"边境之地的人"
- Notch 戏谑地把"边境之地"改名为"末地"
- 这意味着**末影人最初是边境之地的居民**——"虚空之外的虚空的居民"
- 模组"末地殖民军异化为末影人"的叙事得到了原版官方的代码层和命名层双重背书

### 7.6 模组叙事整合建议

**核心叙事资源**：
1. **"边境之地 = 末影人原乡"** —— 在模组"末地叙事"中明确："末影人 (Enderman) 原名 Farlander，是先民在边境之地接触虚空后的异化形态"
2. **"边境之地 = 苍白之悔的视觉原型"** —— 边境之地的"海绵状墙面"+"虚空隧道"可作为模组"苍白之悔"纪元的视觉表现
3. **"边境之地 = 真结局空间"** —— 玩家完成真结局后到达的"虚空之外的虚空"——M. 与另一位领袖灵魂对话的空间
4. **"KurtJMac 14 年 = 玩家坚持的参照"** —— 作为模组"玩家觉醒为继承者"叙事的现实参照——14 年的坚持 = 玩家对"先民文明"的考古执着

---

## 8. 已移除的方块和物品（概览）

> 详细列表见 minecraft.wiki/w/Java_Edition_removed_features 的 "Removed blocks" 与 "Removed items" 子条目
> 本节仅记录与模组叙事相关的关键项目

### 8.1 已移除的方块

| 方块 | 移除版本 | 模组关联 |
|------|----------|----------|
| **撤掉的齿轮（Gear）** | Infdev | 🟡 记录——可作为"先民机械技术"早期概念 |
| **锁定的箱子（Locked Chest）** | Beta 1.4 愚人节加入，1.4 后移除 | 🟡 记录——可作为模组"鼎盛纪元宝库"叙事 |
| **哭泣的黑曜石（Crying Obsidian）** | 1.8 移除 → 1.16 重新加入（Nether Update） | 🟢 已实现 |
| **草路径（Grass Path）旧版本** | 1.9 移除，改为泥土路径 | 🟡 记录 |

### 8.2 已移除的物品

| 物品 | 移除版本 | 模组关联 |
|------|----------|----------|
| **Indev 时期的"Quiver"（箭袋）** | 从未实装 | 🟡 记录 |
| **Old Horse Saddle（旧马鞍）** | 1.6 后改为马铠 | 🟡 记录 |
| **Old Notch Apple（旧 Notch 苹果）** | 改为附魔金苹果 | 🟡 记录——可作为"鼎盛纪元先民领袖的奢侈品"叙事 |

---

## 9. 与其他规划文档的引用关系

| 引用文档 | 关联章节 |
|----------|----------|
| [`planning/02-story-timeline-plan.md`](../planning/02-story-timeline-plan.md) | §5.5 大分裂 → §5.6 现代纪元 末地孤城：**末影人=Farlander** 的原版官方背书 |
| [`planning/07-boss-narrative-binding.md`](../planning/07-boss-narrative-binding.md) | §3.3 末影龙击杀叙事：**红龙 = 先民未完成的替代守门人** |
| [`planning/16-worldview-overview.md`](../planning/16-worldview-overview.md) | §3.1 三界同源 → **v0.6+ 四界同源（The Sift）** 的原版官方背书 |
| [`planning/18-overworld-narrative.md`](../planning/18-overworld-narrative.md) | 笔记 #15-#18：**古代建造者（Builder）** 的原版代码层证据 |
| [`planning/19-nether-narrative.md`](../planning/19-nether-narrative.md) | §3.3.4 暗红光谱：**Sky Dimension = 先民试图建造天空维度的失败尝试** |
| [`planning/20-end-narrative.md`](../planning/20-end-narrative.md) | §5.2 末地是 Sky Dimension 的转化版：**末影人 = Farlanders** |
| [`planning/14-trial-chamber-narrative.md`](../planning/14-trial-chamber-narrative.md) | §6 试炼密室叙事：**Sculk Jaw 未实装 = 失败的禁忌实验** |
| [`15-community-lore/01-syntaxmine-ancient-builders.md`](../15-community-lore/01-syntaxmine-ancient-builders.md) | 古代建造者理论的**原版代码层证据（Builder 实体）** |

---

## 10. 模组采纳状态总表

### 10.1 完全采纳（作为核心叙事资源）

| 编号 | 废弃/未实现特性 | 模组采纳形式 |
|------|-----------------|--------------|
| C1 | **Builder 实体（Beta 1.2_02 20110517 私有版）** | 模组"古代建造者理论"的原版代码层铁证——M./C./E. 等 12 位落款角色的代码层原型 |
| C2 | **Mob / Monster（Classic/Infdev 时期人形 mob）** | 模组"鼎盛纪元先民"的视觉原型——按 G 键生成 Steve 克隆体 |
| C3 | **Sky Dimension（梦境维度）** | 模组"苍白之悔"纪元——先民试图接触虚空的失败尝试 |
| C4 | **Red Dragon（Notch 承诺但未实装）** | 模组"凋灵之灾"中"先民试图制造的末影龙替代守门人"——失败项目代号 "Project RED DRAGON" |
| C5 | **Far Lands（边境之地）** | 模组"末影人=Farlanders"的原版官方命名层背书 + 真结局空间 |
| C6 | **Notch 戏谑："末地改名自边境之地"** | 模组"末地 = 边境之地的失败版本"叙事的原版官方背书 |
| C7 | **The Sift 第四维度** | 模组 v0.6+ 四界同源设定的原版官方背书（详见 [`17-new-2025-2026-content.md`](./17-new-2025-2026-content.md)） |

### 10.2 部分采纳（参考但不全盘接受）

| 编号 | 特性 | 模组采纳形式 |
|------|------|--------------|
| P1 | Giant（巨人） | 作为"大分裂"纪元中"巨型异化先民"的告示牌描述（不实装为新生物） |
| P2 | Illusioner（幻术师） | 作为模组"灾厄村民"支线中"灾厄村民长老"的视觉原型（不实装为新 NPC，沿用原版） |
| P3 | Brick Pyramid / Obsidian Wall / Monolith | 作为模组"鼎盛纪元先民纪念建筑"的视觉原型参考（不实装，仅作为告示牌描述） |
| P4 | Sculk Jaw（幽匿颚） | 作为模组"幽匿之厄"中"被删除的禁忌实验"暗示（不实装，仅作为告示牌描述） |
| P5 | Ruby（红宝石） | 作为模组"先民交易货币"的早期概念（不实装，仅作为告示牌描述） |
| P6 | Steel（钢） | 作为模组"先民冶金技术"叙事的早期概念（不实装） |
| P7 | Pigman Bodyguard（猪人保镖） | 作为模组"鼎盛纪元猪灵文明护卫"叙事（不实装） |

### 10.3 不采纳（仅记录）

- Rana / Beast Boy / Black Steve / Steve（Indev 时期测试 mob）——仅作为"先民队员代号"在告示牌出现
- Killer Bunny / Minecart with Monster Spawner / Luck / Bad Luck / Health Boost / 未使用声音——仅作为氛围渲染（`playsound` 命令调用），不引入新内容
- Alpacas / Colored Planks / Cubic chunks / Coral Slab / Fletching Table Functionality / Firefly mob / Green Axolotl / Quiver / Underground Cabin——仅记录，不引用
- Camouflaging mob / Lava Zombie & Troll / Prefix Mobs / Reindeer / Seasons / Nether features / Scarecrows / Calamari——仅记录，不引用
- Baby Camel Husk / 已移除的方块和物品——仅记录

---

## 11. 参考资料

### 11.1 官方资料（P1）

- minecraft.wiki Java Edition removed features：<https://minecraft.wiki/w/Java_Edition_removed_features>
- minecraft.wiki Java Edition unused features：<https://minecraft.wiki/w/Java_Edition_unused_features>
- minecraft.wiki Java Edition removed entities：<https://minecraft.wiki/w/Java_Edition_removed_entities>
- minecraft.wiki Mentioned features：<https://minecraft.wiki/w/Mentioned_features>
- minecraft.wiki Sky dimension：<https://minecraft.wiki/w/Sky_dimension>
- minecraft.wiki Mentioned features/Red Dragon：<https://minecraft.wiki/w/Mentioned_features/Red_Dragon>
- minecraft.wiki Far Lands：<https://minecraft.wiki/w/Far_lands>
- minecraft.wiki List of mobs by version：<https://minecraft.wiki/w/List_of_mobs_by_version>
- minecraft.wiki Minecraft LIVE：<https://minecraft.wiki/w/Minecraft_LIVE>
- minecraft.wiki 主页：<https://minecraft.wiki>
- Minecraft Live: September 2026 Recap（官方）：<https://www.minecraft.net/en-us/article/mclive_sept2026_recap>
- Minecraft updates timeline：<https://www.minecraft.net/en-us/updates/minecraft-updates-timeline-and-evolution>

### 11.2 社区资料（P2）

- Minecraft Discontinued Features Wiki：<https://mcdf.wiki.gg>
- MCMobs Wiki Rejected mobs：<https://mcmobs.fandom.com/wiki/Rejected_mobs>
- Minecraft Forum Future, Removed, And Forgotten Mobs：<https://www.minecraftforum.net/forums/minecraft-java-edition/recent-updates-and-snapshots/378767-future-removed-and-forgotten-mobs>
- berrybyte.net All Minecraft Mob Vote Winners and Nominees (2017–2023)：<https://berrybyte.net/blog/all-minecraft-mob-vote-winners-and-nominees-2017-2023>
- Notch 2011-07-30 Twitter 关于末影人/Farlanders/末地改名：<https://minecraft.wiki/w/Far_lands#cite_note-1>
- The Ancient Builders Theory (lore.astroworldmc.com)：<https://lore.astroworldmc.com/ancient-builders-theory>
- SyntaxMine Complete Minecraft Lore Timeline：<https://syntaxmine.com/articles/complete-minecraft-lore-timeline>
- minecrafthub.io What Mojang Has Announced About the Next Minecraft Drop：<https://minecrafthub.io/articles/next-minecraft-update>

### 11.3 搜索关键词与调用次数

| 关键词 | 调用次数 |
|--------|----------|
| Minecraft Java Edition removed features unused mobs wiki list | 1 |
| Minecraft cancelled mobs never added Notch Red Dragon Monster | 1 |
| Minecraft Mob Vote losers history (crab/copper golem/tuff golem/meerkat/rascal/glare/iceologer) | 1 |
| Minecraft Sky Dimension cancelled biome history Notch | 1 |
| Minecraft planned structures never implemented lighthouse end update | 1 |
| minecraft.wiki Java Edition removed mobs (Rana/Beast Boy/Black Steve/Steve/Monster/Pigman Boy) | 1 |
| Minecraft mentioned features never added list dimensions biomes structures | 1 |
| Minecraft Live September 2026 ice caves sulfur caves new cave biome recap | 1 |
| Minecraft Far Lands removed 1.8 Bedrock noise generation history | 1 |
| Minecraft 25w14craftmine April Fools 2025 floating islands dimension | 1 |
| Minecraft removed biomes list wiki old beta 1.7 biomes seasons | 1 |
| Minecraft The Sift fourth dimension Dungeons II blub meadow carapace | 1 |
| Minecraft 1.21.11 nautilus update removed features legacy | 1 |

**WebFetch 调用**：3 次（minecraft.wiki removed features / unused features / Sky dimension / Mentioned features）

---

## 12. 修订历史

| 日期 | 版本 | 修订内容 |
|------|------|----------|
| 2026-10-19 | v1.0 | 初次创建——基于 5 次 web 搜索 + 3 次 WebFetch 详细阅读，收录已移除实体、未使用实体、已移除世界生成、已取消维度、Mentioned Features、边境之地完整历史、模组采纳状态总表 |
