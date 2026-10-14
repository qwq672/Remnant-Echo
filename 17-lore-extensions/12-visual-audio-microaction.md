# 12 · 视觉听觉微动作设计

> 本文件属于 **Remnant Echo 模组资料汇编** 的剧情扩展章节（`17-lore-extensions/`）。
> 回应项目方 2026-09-21 指示："只叙事的话那么整个过程会很无聊，只有文字而没有视觉感受与听觉感受" + "代入角色或生物，描述一些细节层面的微动作之类的"。
>
> **资料优先级**：P2（基于已有规划文档整合+模组叙事创作）
> **汇编日期**：2026-09-21

---

## 1. 项目方问题

> "我之前貌似是只讲了是个叙事模组，实际上只叙事的话那么整个过程会很无聊，只有文字而没有视觉感受与听觉感受" + "你也可以代入角色或生物，描述一些细节层面的微动作之类的"

---

## 2. 模组定位澄清

按 [`24-design-followups-2`](../planning/24-design-followups-2.md) 模组定位已扩展为"补齐整个原版世界观+像电影一样的电影化碎片叙事+剧情不无聊"——**视觉+听觉+文学三位一体**。

本文档整合已有规划，并增加"微动作描述"作为新维度。

---

## 3. 视觉感受（粒子+光影+帧）

### 3.1 已有规划整合

按 [`24-design-followups-2`](../planning/24-design-followups-2.md) §Q18 粒子+ [`23-design-followups`](../planning/23-design-followups.md) §4 配乐+ [`26-music-scenario-catalog`](../planning/26-music-scenario-catalog.md)：

| 视觉元素 | 来源 | 实现方式 |
|----------|------|----------|
| L1 原版粒子（dragon_breath/squid_ink/sculk_soul/end_rod 等） | [`24-design-followups-2`](../planning/24-design-followups-2.md) §Q18 | L1 `/particle` 命令 |
| L2 原版粒子组合 | 同上 | L2 function 链式调用 |
| L3 自定义粒子（5 个候选：withering_wave/sculk_echo/pale_regret/colonial_echo/m_farewell） | 同上 | L3 自定义粒子纹理 |
| 光影提示 | [`24-design-followups-2`](../planning/24-design-followups-2.md) §Q17 | L1 advancement+ tellraw，玩家可关闭 |
| 时间/天气变化 | [`24-design-followups-2`](../planning/24-design-followups-2.md) §3.4 | L1 `/time set`+`/weather` |

### 3.2 新增：视觉帧设计

按"电影化碎片叙事"原则，每个关键叙事节点应有"视觉帧"设计：

| 场景 | 视觉帧 | 实现 |
|------|--------|------|
| 拾取笔记 #1 | 玩家视角聚焦笔记（粒子环绕） | L2 粒子+ tellraw 同步 |
| 击败凋灵 | 凋灵死亡瞬间粒子爆发（凋灵玫瑰色） | L1 大量 `wither` 粒子 |
| 监守者钻出 | 黑雾从地面升腾 | L1 `dragon_breath`+`squid_ink` |
| 苍白花园入口 | 白色粒子飘落 | L1 `pale_oak_sapling`+自定义 pale_regret 粒子 |
| 末影龙击败 | 末影龙爆炸动画+末地传送门激活 | L1 原版末影龙死亡动画 |
| 0 号唱片播放 | 金蓝色粒子从唱片机扩散 | L3 自定义 m_farewell 粒子 |

---

## 4. 听觉感受（配乐+音效）

### 4.1 已有规划整合

按 [`26-music-scenario-catalog`](../planning/26-music-scenario-catalog.md) 33 个配乐节点：

| 听觉元素 | 来源 | 实现方式 |
|----------|------|----------|
| L1 原版音乐（cat/mellohi/13/blocks/5/Relic/Pigstep/ward/11/wait 等） | [`26-music-scenario-catalog`](../planning/26-music-scenario-catalog.md) | L1 `/playsound` 命令 |
| L2 原版音乐组合（调速/调音量/多重 playsound） | 同上 | L2 function 链式调用 |
| L3 自创配乐（5 个候选：M.'s Farewell/Pale Regret/Sculk Echo/Withering Wave/Colonial Echo） | 同上 | L3 自定义音乐文件 |
| 原版音效（chest_open/book_take/enchant 等） | 同上 | L1 `/playsound` 命令 |

### 4.2 新增：音效细节设计

按"电影化碎片叙事"原则，每个关键叙事节点应有"音效细节"：

| 场景 | 音效细节 | 实现 |
|------|----------|------|
| 玩家拾取笔记 #1 | `book_open` 音效+轻柔 cat 配乐 | L1 `/playsound` |
| 凋灵召唤 | `wither_spawn` 音效+`large_smoke` 粒子音效 | L1 原版+L2 组合 |
| 监守者钻出 | `sculk_sense` 音效+`heartbeat` 持续音效 | L1 原版+L2 持续调度 |
| 嘎枝激活 | `wood_crack` 音效+`note` 低音 | L1 原版 |
| 末影龙战 | 原版末影龙 BGM+`dragon_breath` 音效 | L1 原版 |
| 0 号唱片播放 | 自定义 m_farewell 配乐+`end_rod` 粒子音效 | L3+L1 组合 |

---

## 5. 微动作描述（新维度，文学创作）

### 5.1 项目方需求

项目方希望"代入角色或生物，描述一些细节层面的微动作"——这是文学创作的扩展。

### 5.2 微动作描述示例

按模组叙事，**12 位落款角色**（M./H./K./T./E./B./N./G./L./C./R./S.）+ 4 个 L3 自定义叙事 NPC（古老图书管理员/考古学家村民/流浪者长老/末地殖民军后裔）应有微动作描述。

#### 5.2.1 M.（先民领袖，曾经的 C.）

**笔记 #1 拾取时的微动作 tellraw**：
> 「你拾起笔记，纸张泛黄，墨迹模糊。字迹似乎在颤抖——是写的人害怕，还是阅读的人？最后一行有一个符号，像是字母 M。
>
> M. 写下这行字时，手指在颤抖。他听到下界要塞的轰鸣声从远处传来——那是凋灵实验失控的前兆。他抬头看向窗外，紫珀砖的塔楼在末地的紫雾中若隐若现。
>
> 他知道，这是他最后一次以"C."的身份写信。」

#### 5.2.2 古老图书管理员（L3 自定义 NPC）

**玩家右键交互时的微动作 tellraw**：
> 「古老图书管理员抬起头，浑浊的眼睛看着你。他的手指在书页上停留——那是一本泛黄的笔记，与他一样苍老。
>
> 他没有说话，只是从书架背后取出一卷残破的笔记，递给你。
>
> 他的手在颤抖——不是因为害怕，而是因为等待太久。」

#### 5.2.3 考古学家村民（L3 自定义 NPC）

**玩家右键交互时的微动作 tellraw**：
> 「考古学家村民正在用刷子清理一块可疑的砾石。他抬头看了你一眼，点了点头，仿佛在确认你是"值得托付"的人。
>
> 他从腰间取出一份残破的笔记，递给你——上面记着古迹废墟的位置。
>
> 他的眼神中带着一丝焦急——仿佛他知道，时间不多了。」

#### 5.2.4 监守者（关键 Boss）

**监守者钻出地面时的微动作 tellraw**：
> 「你听到地面的颤抖——不是地震，是某种"苏醒"。
>
> 黑雾从地面升腾，幽匿感知到你的存在。一只巨大的手掌从地下伸出——指节粗大，没有眼睛，只有张大嘴在嘶吼。
>
> 监守者不是为了杀你而来——他是为了"完成"什么。但他已经不记得是什么了。」

#### 5.2.5 末影龙（最终守门人）

**末影龙战前的微动作 tellraw**：
> 「末影龙盘旋在末地岛上空，紫色的翅膀在虚空中扇动。它没有看你——它的眼睛盯着末地传送门，仿佛在守护什么。
>
> 它不是怪物——它是被制造出来的。它知道，但它必须守护。
>
> 它的龙息带着紫色粒子——那是先民维度能量的残留。」

### 5.3 微动作描述的创作原则

1. **代入选定角色**：每个 tellraw 必须以选定角色或生物的视角描述
2. **细节层面**：不写"他做了什么"，而写"他的手指在颤抖/他抬头看了一眼/他指节的肌肉绷紧"
3. **不超过 5 段**：保持简洁，避免冗长
4. **与配乐+粒子同步**：每个微动作 tellraw 触发时，应同步触发配乐+粒子
5. **不剥夺玩家控制**：tellraw 显示在聊天框，玩家可继续游戏

---

## 6. 三位一体设计示例

### 6.1 玩家拾取笔记 #1（M1 主线种子埋下）

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

### 6.2 击败末影龙（M8 守门人真相）

```mcfunction
# data/remnant/functions/lore/on_dragon_killed.mcfunction

# 视觉：末影龙死亡动画+末地传送门激活（原版）+dragon_breath 粒子爆发
particle minecraft:dragon_breath ~ ~2 ~ 2 1 2 0 50

# 听觉：原版末影龙死亡音效+ward 唱片切换
stopsound @s
playsound minecraft:entity.ender_dragon.death master @s ~ ~ ~ 1 1

# 微动作 tellraw（末影龙视角）
tellraw @s {"text":"末影龙盘旋在末地岛上空，紫色的翅膀在虚空中扇动。","color":"gray","italic":true}
tellraw @s {"text":"它没有看你——它的眼睛盯着末地传送门，仿佛在守护什么。","color":"gray","italic":true}
tellraw @s {"text":"它不是怪物——它是被制造出来的。它知道，但它必须守护。","color":"gray","italic":true}
tellraw @s {"text":"","extra":[{"text":"你击败了它。它的最后一道门，被你打开了。","color":"gold"}]}

# 触发守门人真相 advancement
advancement grant @s only remnant:lore/dragon_killed
```

### 6.3 0 号唱片播放（M10 真结局）

```mcfunction
# data/remnant/functions/lore/on_disc0_play.mcfunction

# 视觉：金蓝色粒子从唱片机扩散（L3 自定义 m_farewell 粒子）
particle remnant:m_farewell ~ ~1 ~ 1 1 1 0 30

# 听觉：L3 自创配乐 m_farewell（基于 C418 ambient 风格）
playsound remnant:music.m_farewell master @s ~ ~ ~ 0.8 1

# 微动作 tellraw（M. 遗言 9 段，按 26-music-scenario-catalog §10.2）
tellraw @s {"text":"他们不是英雄，不是叛徒，不是怪物。","color":"gray","italic":true}
# ... 8 段（详见 20-end-narrative §14.2）
tellraw @s {"text":"","extra":[{"text":"这个世界，现在交给你了。","color":"gold"}]}
tellraw @s {"text":"","extra":[{"text":"—— M.（曾经的 C.）","color":"aqua","italic":true}]}

# 触发真结局 advancement
advancement grant @s only remnant:lore/true_ending
```

---

## 7. 微动作描述的角色清单

按 [`09-mob-relationships`](./09-mob-relationships.md) + [`25-design-followups-3`](../planning/25-design-followups-3.md)：

| 角色 | 来源 | 微动作场景 | 优先级 |
|------|------|------------|--------|
| M.（先民领袖，曾经的 C.） | 笔记 #1/#10/#14/#17/#18/#26 | 6 个场景 | ★★★★★ v0.1+ |
| H.（守考者） | 笔记 #7/#8/#9 | 3 个场景 | ★★★ v0.4 |
| K.（矿工） | 笔记 #11 | 1 个场景 | ★★ v0.3 |
| T.（提炼者） | 笔记 #12 | 1 个场景 | ★★ v0.3 |
| E.（匠人） | 笔记 #13/#17/#25 | 3 个场景 | ★★★ v0.5 |
| B.（凋灵实验工程师） | 笔记 #19 | 1 个场景 | ★★★ v0.3 |
| N.（自然学者） | 笔记 #20 | 1 个场景 | ★★ v0.3 |
| G.（埋葬者） | 笔记 #21 | 1 个场景 | ★★ v0.3 |
| L.（猪灵领袖） | 笔记 #22 | 1 个场景 | ★★★ v0.3 |
| C.（末地殖民军指挥官） | 笔记 #23/#24 | 2 个场景 | ★★★★★ v0.5 |
| R.（撤退者） | 笔记 #15 | 1 个场景 | ★★ v0.2 |
| S.（航海者） | 笔记 #16 | 1 个场景 | ★★ v0.2 |
| 古老图书管理员（L3 NPC） | 玩家右键交互 | 1 个场景 | ★★★★★ v0.1 |
| 考古学家村民（L3 NPC） | 玩家右键交互 | 1 个场景 | ★★★★ v0.1 |
| 流浪者长老（L3 NPC） | 玩家右键交互 | 1 个场景 | ★★★ v0.2 |
| 末地殖民军后裔（L3 NPC） | 玩家右键交互 | 1 个场景 | ★★★★★ v0.5 |

**总计 25 个微动作场景**——按 v0.1~v0.6 分阶段实施。

---

## 8. 模组采纳建议

| 候选 | 采纳方式 | L 等级 | 优先级 |
|------|----------|--------|--------|
| 视觉帧设计（粒子+光影） | L1+L2+L3（按场景） | L1/L2/L3 | ★★★★★ v0.1+ |
| 听觉细节设计（配乐+音效） | L1+L2+L3（按 26 文档） | L1/L2/L3 | ★★★★★ v0.1+ |
| 微动作 tellraw（M.视角 6 场景） | L1 tellraw 文本 | L1 | ★★★★★ v0.1+ |
| 微动作 tellraw（其他 11 角色 19 场景） | L1 tellraw 文本 | L1 | ★★★ v0.2+ |
| 微动作 tellraw（4 个 L3 NPC 4 场景） | L1 tellraw 文本 | L1 | ★★★★ v0.1+ |
| 三位一体同步（视觉+听觉+微动作） | L2 function 链式调用 | L2 | ★★★★★ v0.1+ |

---

## 9. 与已有规划文档的关联

- [`24-design-followups-2`](../planning/24-design-followups-2.md) §Q9 配乐+§Q17 光影提示+§Q18 粒子——本章节是其整合
- [`25-design-followups-3`](../planning/25-design-followups-3.md) §3 4 个 L3 自定义叙事 NPC——本章节是其微动作设计
- [`26-music-scenario-catalog`](../planning/26-music-scenario-catalog.md) 33 个配乐节点——本章节是其听觉部分
- [`09-mob-relationships`](./09-mob-relationships.md) 12 位落款角色——本章节是其微动作描述对象
- [`20-end-narrative`](../planning/20-end-narrative.md) §14.2 M. 遗言 9 段——本章节是其 M10 真结局微动作

---

## 10. 待补充调研

- [ ] M. 遗言 9 段的完整文本（按 [`20-end-narrative`](../planning/20-end-narrative.md) §14.2，待详化）
- [ ] 4 个 L3 自定义叙事 NPC 的完整微动作描述
- [ ] 22 张笔记的完整内容（按 [`09-village-loot-extension`](../planning/09-village-loot-extension.md)+ [`14-trial-chamber-narrative`](../planning/14-trial-chamber-narrative.md)+ [`15-netherite-enchantment-essence`](../planning/15-netherite-enchantment-essence.md)+ [`18-overworld-narrative`](../planning/18-overworld-narrative.md)+ [`19-nether-narrative`](../planning/19-nether-narrative.md)+ [`20-end-narrative`](../planning/20-end-narrative.md) 整理）

---

## 11. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-21 | v0.1 | 初稿，整合已有视觉（粒子+光影）+听觉（配乐+音效）规划，新增微动作描述维度（25 个场景，按 12 落款角色+4 个 L3 NPC 整理）+三位一体设计示例（M1/M8/M10 三个关键节点）+模组采纳建议 | 项目方 |
