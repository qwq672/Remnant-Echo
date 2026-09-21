# 25 · 设计问答第四批 · 命令工程化 / 叙事生物变体 / 动画

> **状态**：🟡 设计讨论中（部分待项目方审核）
> **对应模组版本**：v0.1+ 设计阶段
> **创建日期**：2026-09-21
> **最后更新**：2026-09-21
> **设计原则**：[原则 0 · L1/L2/L3 判定](./00-planning-index.md#原则-0优先原版实在没辙才自定义且必须与原版有关)
> **关联章节**：[`24-design-followups-2.md`](./24-design-followups-2.md) · [`10-custom-items-registry.md`](./10-custom-items-registry.md) · [`22-design-questions-answers.md`](./22-design-questions-answers.md)

---

## 1. 目的

本文档是 [`24-design-followups-2.md`](./24-design-followups-2.md) 的后续讨论，记录项目方 2026-09-21 提出的 3 个关键工程化问题：

1. **Q19**：直接用命令实现会不会"整的太那啥了"？
2. **Q20**：是否需要为部分带叙事的生物重新搞一个版本（如村民，村民的手分不开）？
3. **Q21**：是否需要一点动画为生物增加灵活、生动感，并为剧情场景方便？

**核心转折点**：用户开始关注模组的工程化与体验质量——这是从"资料阶段"过渡到"代码阶段"的关键问题。

---

## 2. Q19 · 直接用命令实现会不会"整的太那啥了"？

### 2.1 项目方问题

> "我好像意识到了一个问题，那就是直接用命令的话会不会整的太那啥了"

### 2.2 协作者回答

**项目方的担心完全合理**。纯命令（function + tellraw + particle + playsound）在玩家视角下是"无缝"的，但在以下维度确实显得"太那啥"：

| 维度 | 纯命令实现的问题 |
|------|------------------|
| **工程感** | 大量 JSON 配置+function 调用，缺乏代码抽象，可维护性差 |
| **错误处理** | function 失败时玩家无任何反馈，难以调试 |
| **多人同步** | advancement 触发在多人服务器可能有延迟 |
| **复杂叙事** | 多段 tellraw 的节奏控制、条件分支、状态管理难以用纯 JSON 实现 |
| **玩家感知** | 虽然玩家看不到命令文本，但 function 触发的"突然弹窗"仍有"命令方块味" |

### 2.3 三级工程化策略

按 L1/L2/L3 原则，协作者提出**三级工程化策略**，与原 L1/L2/L3 优先原则叠加使用：

| 工程等级 | 实现方式 | L 等级叠加 | 适用场景 |
|----------|----------|------------|----------|
| **E1 纯 datapack** | function JSON + advancement JSON + tellraw + particle + playsound | L1 | 简单叙事触发（笔记拾取→advancement→tellraw 显示文本） |
| **E2 Java 封装** | 用 Fabric mod 的 Java 代码封装 function 调用，玩家完全感知不到命令 | L2 | 复杂叙事节奏（多段 tellraw 的时间间隔、条件分支、状态管理） |
| **E3 Java Mixin 拦截** | 用 Mixin 拦截原版事件（如玩家进入特定位置、击杀特定 Boss），在 Java 层触发叙事 | L3 | 关键叙事节点（击败末影龙后立即触发守门人真相，需要精确时机控制） |

### 2.4 推荐做法

**模组本来就是 Fabric mod，会有 Java 代码**——按 [`10-custom-items-registry.md`](./10-custom-items-registry.md) 已论证 5 个 L3 自定义物品需要 Java 注册。所以模组**不是纯 datapack**，而是 Fabric mod + datapack 混合架构。

**具体推荐**：

| 叙事场景 | E 等级 | 实现方式 |
|----------|--------|----------|
| 笔记拾取 → tellraw 显示文本 | E1 | advancement 触发 function，function 调用 tellraw |
| 击败末影龙 → 守门人真相多段叙事 | E2 | Java 代码监听 `PlayerKilledEntityEvent`，按节奏调用 function（每段 tellraw 间隔 2 秒） |
| 玩家进入远古城市 → 触发"幽厄氛围" | E3 | Mixin 拦截 `PlayerEnterChunkEvent`，Java 层判断是否为远古城市 chunk，触发配乐+粒子+叙事 |
| 玩家合成 0 号唱片 → 真结局动画序列 | E3 | Mixin 拦截 `RecipeCraftedEvent`，Java 层触发完整叙事序列（配乐+粒子+tellraw+时间停止） |

### 2.5 工程化架构建议

```
┌─────────────────────────────────────┐
│  Java 层（Fabric mod）              │
│  ├ Mixin 拦截原版事件               │
│  ├ Event Handler 订阅               │
│  ├ 状态管理（玩家叙事进度）         │
│  └ 调用 datapack function           │
└────────────────┬────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────┐
│  Datapack 层（data/remnant/）       │
│  ├ advancements/*.json              │
│  ├ functions/*.mcfunction           │
│  ├ loot_tables/*.json              │
│  └ predicates/*.json               │
└────────────────┬────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────┐
│  资源层（assets/remnant/）           │
│  ├ lang/*.json                      │
│  ├ textures/*                       │
│  ├ models/*                          │
│  └ patchouli_books/                 │
└─────────────────────────────────────┘
```

**关键点**：玩家完全感知不到"命令"——所有叙事触发都由 Java 代码主动调度，datapack function 是被调用的工具，而非玩家可见的命令方块。

### 2.6 结论

**Q19 回答**：
- 纯命令（E1）确实"太那啥"，**不作为模组主要实现方式**
- ✅ 模组采用 **E1 + E2 + E3 三级工程化策略**：
  - E1（~30%）：简单叙事触发（datapack function + advancement）
  - E2（~50%）：复杂叙事节奏（Java 代码封装 function 调用）
  - E3（~20%）：关键叙事节点（Java Mixin 拦截原版事件）
- 玩家完全感知不到命令存在——模组体验与"专业 Fabric mod"一致

---

## 3. Q20 · 是否需要为叙事生物重新搞一个版本（如村民手分不开）？

### 3.1 项目方问题

> "并且是否可能需要考虑为部分带叙事的生物重新搞一个版本（例如村民，村民的手分不开）"

### 3.2 原版生物模型限制

原版村民模型的关键限制：

| 限制 | 影响 |
|------|------|
| **手臂合拢** | 村民的手分不开，无法做"递东西"、"指路"、"写字"等动作 |
| **无手指** | 无法做精细动作（如拿笔、翻书页） |
| **有限表情** | 只有"yes/no/head_shake"三种表情，无法做"惊讶"、"悲伤"等复杂表情 |
| **无随身物品** | 村民身上没有"背包"、"口袋"等可挂载物品的位置 |
| **动画有限** | 只有 walking、head_shake、arms_crossed 三种动画 |

### 3.3 L 等级评估

按 [原则 0 · 永远禁止清单](./00-planning-index.md#l3-自定义的永远禁止清单)：

| 候选方案 | L 等级 | 是否允许 | 论证 |
|----------|--------|----------|------|
| L1：用原版村民 + particle 模拟动作 | L1 | ✅ 允许 | 用 `note_particle` 表示"递笔记"、`happy_villager` 表示"赞同"——但视觉感弱 |
| L2：用原版村民 + advancement 触发"虚拟动作" | L2 | ✅ 允许 | advancement 触发 tellraw 描述"村民递给你一份笔记"，无视觉动作 |
| L3：自定义"叙事村民"变体（NBT + CustomModelData） | L3 | ✅ 允许（有条件） | 必须基于原版村民纹理衍生，行为与原版村民 AI 一致，退化时退化为普通村民 |
| L3：自定义全新村民模型（含自定义骨骼） | L3 | ❌ 禁止 | 完全新模型，违反"新生物"清单 |
| L3：修改原版村民 AI（添加新动作） | L3 | ❌ 禁止 | 违反"改变原版生物 AI"清单 |

### 3.4 L3 自定义"叙事村民"变体的论证

按 L3 论证流程：

#### 必要性论证

| 候选方案 | 为何不可行 |
|----------|------------|
| L1：原版村民 + particle | ❌ particle 模拟"递笔记"视觉感极弱，玩家难以理解"村民在递东西" |
| L2：原版村民 + advancement | ❌ tellraw 描述"村民递笔记"无视觉动作，违反"碎片化叙事通过环境呈现"原则 |
| L3：自定义"叙事村民"变体 | ✅ 必要——通过 CustomModelData 改变村民纹理（如"递笔记"姿势的纹理变体），玩家视觉明确 |

**结论**：关键叙事 NPC（如"古老图书管理员"、"考古学家村民"）需要 L3 自定义变体，以承载"递笔记"等关键视觉叙事动作。

#### 关联性论证

| 关联维度 | 满足情况 | 说明 |
|----------|----------|------|
| **视觉关联** | ✅ | 纹理基于原版村民纹理衍生，仅修改"手臂姿势"（如手臂分开、手心向上） |
| **行为关联** | ✅ | 行为与原版村民 AI 完全一致（行走、避难、交易） |
| **来源关联** | ✅ | 通过原版村庄生成逻辑触发，仅替换特定村民的 NBT |
| **数据关联** | ✅ | NBT 基于 `VillagerEntity`，仅追加 `CustomModelData` 字段 |
| **退化关联** | ✅ | 失去模组时退化为普通村民，仍可正常交易 |

#### 退化方案

```
模组卸载时的行为：
1. 自定义"叙事村民"变体的 NBT 中 CustomModelData 字段被忽略
2. 村民纹理退化为原版村民纹理
3. 村民仍可正常交易（保留原版 VillagerEntity 的所有 NBT）
4. 玩家失去"递笔记"视觉动作，但叙事文本仍可通过 tellraw 显示
```

### 3.5 推荐做法

**核心立场**：不替换原版村民，**仅追加少数"叙事村民"变体**作为关键叙事 NPC。

#### 叙事村民变体清单（L3 自定义候选）

| 变体名 | 出现位置 | 视觉特征 | 叙事功能 | 优先级 |
|--------|----------|----------|----------|--------|
| **古老图书管理员** | 村庄图书馆（按 01 方案 B 替换的 bookshelf 附近） | 基于原版图书管理员纹理，加"年迈"特征（白发、皱纹） | 玩家右键时显示笔记 #1 内容（与笔记 #1 互补，非重复） | ★★★★★ v0.1 必备 |
| **考古学家村民** | 村庄考古棚（按 01 方案 C 新增结构） | 基于原版制图师纹理，加"考古装备"特征（戴帽子、腰间挂刷子） | 玩家右键时显示笔记 #15 内容（古迹废墟指引） | ★★★★ v0.1 必备 |
| **流浪者长老** | 流浪商人羊驼队伍中的特殊 NPC | 基于原版流浪商人纹理，加"年迈"特征 | 玩家右键时显示笔记 #16 内容（航海者清单） | ★★★ v0.2 |
| **末地殖民军后裔** | 末地城图书馆 | 基于原版末影人纹理，加"半人半末影"特征 | 玩家右键时显示笔记 #23 内容（殖民军日志） | ★★★★★ v0.5 真结局核心 |

#### 不创建变体的生物

以下生物**不创建变体**，仍用原版+ L1 particle+ L2 tellraw 实现：
- 骷髅、僵尸、苦力怕、蜘蛛等敌对生物（无叙事交互需求）
- 灾厄村民（用原版 raid 机制，tellraw 解读即可）
- 普通村民（保留原版，不替换）

### 3.6 工作量估算

| 工作 | 数量 | 工作量 |
|------|------|--------|
| L3 自定义叙事村民变体 | 4 个（古老图书管理员/考古学家村民/流浪者长老/末地殖民军后裔） | 中（每变体 1 张纹理 + NBT 配置 + Java Mixin 注册） |
| L1 particle 模拟动作 | ~20 个场景 | 极低（仅 `/particle` 命令配置） |
| L2 tellraw 文本叙事 | ~30 个场景 | 低（function 调用） |

**总工作量**：占美术工作量的 40%（在美术 15% 总占比内），占代码工作量的 20%（在代码 30% 总占比内）

### 3.7 结论

**Q20 回答**：
- ✅ **需要**为部分带叙事的生物创建 L3 自定义变体
- 仅限 4 个关键叙事 NPC（古老图书管理员/考古学家村民/流浪者长老/末地殖民军后裔）
- 变体基于原版生物纹理衍生，行为与原版一致，失去模组时退化为原版生物
- 其他生物仍用 L1 particle + L2 tellraw 实现，不创建变体

---

## 4. Q21 · 是否需要动画为生物增加灵活、生动感？

### 4.1 项目方问题

> "并且可能需要一点动画啥的来为生物增加灵活、生动感并且也为剧情内的场景方便一点"

### 4.2 原版动画限制

原版生物动画系统有限：

| 生物 | 原版动画 | 限制 |
|------|----------|------|
| 村民 | walking、head_shake、arms_crossed | 无法做"递笔记"、"指路"等动作 |
| 末影人 | walking、screaming、attacking | 无法做"回忆"、"悲伤"等情绪动画 |
| 凋灵骷髅 | walking、attacking | 无法做"痛苦"、"挣扎"等动画 |
| 监守者 | walking、attacking、sniffing | 无法做"觉醒过程"等过渡动画 |

### 4.3 L 等级评估

| 候选方案 | L 等级 | 是否允许 | 论证 |
|----------|--------|----------|------|
| L1：用原版动画 + particle 模拟"动作" | L1 | ✅ 允许 | 用 `note_particle` + `happy_villager` 模拟"村民思考"、"村民赞同"——视觉感弱但可行 |
| L2：用原版动画 + 多重 particle 形成"动作序列" | L2 | ✅ 允许 | function 链式调用 particle，形成"动作序列"（如村民"递笔记"= particle_smoke → particle_book_take → particle_note） |
| L3：自定义动画（用 Java Mixin 修改 ModelPart） | L3 | ⚠️ 谨慎允许 | 必须不修改原版 AI，仅添加新动画状态；需严格论证 |
| L3：完全自定义生物模型（含新骨骼） | L3 | ❌ 禁止 | 违反"新生物"清单 |
| L3：修改原版生物 AI 触发新动画 | L3 | ❌ 禁止 | 违反"改变原版生物 AI"清单 |

### 4.4 L3 自定义动画的论证（谨慎）

**核心立场**：**原则上不创建自定义动画**，仅在以下场景考虑：

| 场景 | 是否需要 L3 自定义动画 | 理由 |
|------|------------------------|------|
| 古老图书管理员"递笔记" | ✅ 需要 | 关键叙事动作，原版村民手臂合拢无法承载 |
| 考古学家村民"指路" | ✅ 需要 | 关键叙事动作，需手指方向 |
| 末地殖民军后裔"回忆" | ⚠️ 可选 | 可用 particle + tellraw 替代（"回忆"粒子+多段文本） |
| 监守者"觉醒"过渡 | ❌ 不需要 | 原版 sniffing 动画已足够 |
| 凋灵骷髅"痛苦挣扎" | ❌ 不需要 | 原版 attacking 动画已足够 |

### 4.5 L3 自定义动画的实现方式

按 Fabric mod 的 Mixin 机制：

```java
// 伪代码示例：用 Mixin 修改 VillagerEntity 的渲染
@Mixin(VillagerEntityRenderer.class)
public class NarratorVillagerRendererMixin {
    @Inject(
        method = "setupAnimates",
        at = @At("TAIL")
    )
    private void addNarratorAnimates(VillagerEntity entity, float limbSwing, float limbSwingAmount, 
                                     float ageInTicks, float headYaw, float headPitch, 
                                     float scale, MatrixStack matrixStack, VertexConsumer buffer, 
                                     int packedLight, CallbackInfo ci) {
        if (entity.hasCustomName() && "narrator_librarian".equals(entity.getCustomName().getString())) {
            // 调用手臂骨骼，使其分开
            ModelPart rightArm = ((VillagerModelAccessor)model).getRightArm();
            rightArm.xRot = (float)Math.toRadians(-45); // 手臂抬起 45 度
            rightArm.yRot = (float)Math.toRadians(30);  // 手臂向外分开
        }
    }
}
```

**关键约束**：
- 仅在 NBT 标记为"叙事 NPC"时触发新动画
- 不修改原版村民的默认动画
- 玩家卸载模组后，村民动画退化为原版

### 4.6 推荐做法

**L1+L2 优先**（~80% 场景）：
- 用原版动画 + particle 模拟"动作"（村民"思考"= `note_particle` 在头顶；村民"赞同"= `happy_villager` 粒子）
- 用 function 链式调用 particle 形成"动作序列"

**L3 自定义动画（谨慎）**（~20% 场景）：
- 仅在 4 个叙事 NPC 的关键动作（递笔记/指路）使用 Mixin 修改 ModelPart
- 不修改原版 AI，仅添加新动画状态
- 退化时退化为原版动画

### 4.7 替代方案：用 Cinematic 叙事序列

若项目方希望"电影感"更强，可考虑 **L3 自定义"叙事序列"function**：

```mcfunction
# data/remnant/functions/cinematic/villager_give_note.mcfunction
# 模拟"村民递笔记"的电影化序列

# Step 1: 时间停止（仅 5 秒）
effect give @s minecraft:slowness 5 255 true
effect give @s minecraft:blindness 1 255 true

# Step 2: 配乐切换
stopsound @s
playsound minecraft:block.chest.open master @s ~ ~ ~ 0.5 1

# Step 3: 粒子序列（模拟"村民伸手"）
particle minecraft:note ~ ~1 ~ 0.5 0.5 0.5 0 5
execute at @e[type=villager,limit=1] run particle minecraft:happy_villager ~ ~1 ~ 0.3 0.5 0.3 0 3

# Step 4: 等待 1 秒（function 调用 schedule）
schedule function remnant:cinematic/villager_give_note_step2 20t

# Step 5: 叙事文本显示
tellraw @s {"text":"古老图书管理员递给你一份残破的笔记...","color":"gray","italic":true}
```

**优点**：
- 不需要 Java Mixin（避免 L3 复杂性）
- 玩家感知到"电影化序列"
- 通过原版 particle + effect + playsound + tellraw 实现

**缺点**：
- 视觉感仍弱于真正的自定义动画
- 时间停止可能影响玩家体验

### 4.8 结论

**Q21 回答**：
- ✅ **需要少量动画**为生物增加灵活、生动感
- **L1+L2 优先**（~80%）：用原版动画 + particle 模拟"动作"
- **L3 自定义动画**（~20%）：仅在 4 个叙事 NPC 的关键动作使用 Mixin 修改 ModelPart
- **替代方案**：L3 自定义"叙事序列"function，用原版 particle + effect + playsound + tellraw 实现"电影化序列"，避免 Mixin 复杂性

---

## 5. 总结：本批次决策速查

| 项目方问题 | 协作者回答 |
|------------|------------|
| Q19 直接命令太那啥 | ✅ 担心合理——采用 E1/E2/E3 三级工程化（datapack→Java 封装→Mixin 拦截），玩家完全感知不到命令 |
| Q20 叙事生物变体 | ✅ 需要——仅 4 个关键叙事 NPC（古老图书管理员/考古学家村民/流浪者长老/末地殖民军后裔）创建 L3 自定义变体，基于原版纹理衍生 |
| Q21 生物动画 | ✅ 需要少量——L1+L2 优先（particle 模拟），L3 Mixin 仅用于关键动作（递笔记/指路）；或用"叙事序列 function"作替代 |

---

## 6. 待项目方最终确认

- [ ] **Q19 工程化策略**：是否采用 E1+E2+E3 三级工程化（推荐），还是仅用 E1 纯 datapack？
- [ ] **Q20 叙事村民变体清单**：是否启动 4 个 L3 自定义叙事 NPC？是否按 v0.1（古老图书管理员+考古学家村民）/v0.2（流浪者长老）/v0.5（末地殖民军后裔）分阶段实施？
- [ ] **Q21 动画策略**：选择 L3 Mixin 修改 ModelPart（更精美但复杂），还是用 L3 "叙事序列 function"（更简单但视觉感弱）？

---

## 7. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-21 | v0.1 | 初稿，记录项目方 9-21 提出的 3 个关键工程化问题（命令工程化/叙事生物变体/动画），提出 E1/E2/E3 三级工程化策略 + 4 个 L3 自定义叙事 NPC 候选 + L1/L2/L3 三级动画策略 | 协作者 |
