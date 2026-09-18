# 17 · 模组介绍文案

> **状态**：🟡 设计讨论中
> **对应模组版本**：v0.9 预发布 / v1.0 正式发布
> **创建日期**：2026-09-18
> **最后更新**：2026-09-18
> **设计原则**：[原则 0 · L1/L2/L3 判定](./00-planning-index.md#原则-0优先原版实在没辙才自定义且必须与原版有关)
> **关联章节**：[`BLUEPRINT.md`](../BLUEPRINT.md) · [`16-worldview-overview.md`](./16-worldview-overview.md)

---

## 1. 目的

为模组 **Remnant / Echo** 提供面向不同发布平台与受众的标准化介绍文案，包括：

1. **一句话简介**（用于 CurseForge / Modrinth 简介栏）
2. **段落式简介**（用于 Modrinth / CurseForge 详情页顶部）
3. **完整介绍**（用于模组主页、MC 百科条目、GitHub README 顶部）
4. **特性清单**（用于发布说明、宣传材料）
5. **常见问答（FAQ）**（用于 Modrinth / CurseForge 评论区置顶）
6. **媒体宣传文案**（用于 Twitter / Discord / 视频简介）

**核心约束**：
- 所有文案必须**准确反映模组实际内容**，不夸大、不营销话术
- 严格遵循 L1/L2/L3 原则——介绍文案属纯文本，不涉及任何机制实现
- 多语言版本与 [`11-localization-strategy.md`](./11-localization-strategy.md) 一致：首发 zh_cn + en_us，v1.0 前 8 语言

---

## 2. 模组基本信息

| 项目 | 内容 |
|------|------|
| **项目代号** | Remnant（暂定名）/ Echo（候选名） |
| **类型** | Minecraft 原版故事观叙事模组 |
| **目标版本** | Minecraft 1.21.11+（Java Edition） |
| **加载器** | Fabric（首选）/ NeoForge（计划支持） |
| **依赖** | Patchouli（软依赖，缺失时降级为 tellraw） |
| **发布平台** | CurseForge、Modrinth、MC 百科 |
| **首发语言** | zh_cn + en_us |
| **计划发布** | 2028 年 12 月预发布 Beta，2029 年 5 月正式发布 |
| **开源协议** | 代码 MIT/LGPL，叙事资产闭源 |
| **仓库地址** | https://github.com/qwq672/ancient-echo |

---

## 3. 一句话简介（25 字以内）

用于 CurseForge / Modrinth 简介栏、Discord 频道话题、Twitter 简介。

### 3.1 中文版（zh_cn）

> 通过原版碎片化线索，拼凑一支远古文明在三界兴衰的史诗。

### 3.2 英文版（en_us）

> Piece together the rise and fall of an ancient civilization across three dimensions, through vanilla's scattered clues.

### 3.3 日文版（ja_jp）

> 原版の断片的な手がかりを通じて、三界に興亡した古代文明の叙事詩を紡ぎ出す。

---

## 4. 段落式简介（100-200 字）

用于 Modrinth / CurseForge 详情页顶部、GitHub README 顶部。

### 4.1 中文版（zh_cn）

> **Remnant / Echo 是一个基于 Minecraft 原版碎片化线索构建的叙事模组。**
>
> 它不魔改原版交互，不脱离官方留白。只通过考古、线索、Boss 与叙事文本，拼凑一支远古先民文明在三界兴衰的史诗。
>
> 主世界、下界、末地的建筑与生物源自同一支远古先民文明——他们曾掌握维度穿行技术，研究灵魂能量与生命本源，最终因三大实验失控而崩解。今日的村民、猪灵、末影人，皆为其后裔。
>
> 你不是先民的后裔，你是局外人。但通过探索遗迹、收集残破笔记、解读原版唱片、击杀原版 Boss，你将逐步拼凑出整个真相——并最终听到先民领袖的遗言。

### 4.2 英文版（en_us）

> **Remnant / Echo is a narrative mod built upon Minecraft's vanilla scattered clues.**
>
> It does not modify vanilla interactions, nor does it depart from official blanks. It only uses archaeology, clues, bosses, and narrative text to piece together an epic of an ancient civilization's rise and fall across three dimensions.
>
> The Overworld, the Nether, and the End share the same origin—an ancient civilization that mastered dimensional traversal, studied soul energy and the source of life, and ultimately collapsed after three experiments spiraled out of control. Today's villagers, piglins, and endermen are all their descendants.
>
> You are not their heir. You are an outsider. But by exploring ruins, collecting tattered notes, interpreting vanilla music discs, and defeating vanilla bosses, you will gradually piece together the entire truth—and finally hear the last words of their leader.

### 4.3 日文版（ja_jp）

> **Remnant / Echo は、Minecraft 原版の断片的な手がかりに基づいて構築された叙事モッドです。**
>
> 原版のインタラクションを改変せず、公式の空白から逸脱しません。考叢、手がかり、ボス、そして叙事テキストを通じて、三界で興亡した古代文明の叙事詩を紡ぎ出します。
>
> 主世界、ネザー、ジ・エンドは同一の古代文明を起源とします。彼らはかつて次元間移動技術を掌握し、魂のエネルギーと生命の本源を研究していましたが、三大実験の暴発により崩壊しました。今日の村人、ピグリン、エンダーマンは全て彼らの子孫です。
>
> あなたは彼らの相続人ではありません。部外者です。しかし、遺跡を探索し、破れたノートを集め、原版のレコードを解釈し、原版のボスを倒すことで、あなたは次第に真相全体を紡ぎ出し、ついには彼らの指導者の遺言を聞くことになります。

---

## 5. 完整介绍（500-1000 字）

用于模组主页、MC 百科条目、详细 README。

### 5.1 中文版（zh_cn）

#### 关于本模组

**Remnant / Echo** 是一个 Minecraft 原版故事观叙事模组，旨在通过碎片化叙事手法，将 Mojang 在原版游戏中留下的零散线索合理串联，构建一支远古先民文明在三界兴衰的完整史诗。

#### 设计哲学

本模组的核心设计原则是 **「优先原版，实在没辙才自定义，且必须与原版有关」**。所有叙事内容必须基于原版已有设定（建筑、生物、物品、Boss），不引入官方未提及的新种族、新文明、新纪元名称（除非作为"对原版留白的解读"）。模组的设定本质是**对原版留白的合理串联**，而非**新世界观的创造**。

具体而言，模组采用三级优先级体系：

- **L1 优先原版**（~80%）：直接使用原版物品/方块/机制承载叙事，例如用 `written_book` 承载叙事文本
- **L2 原版组合**（~15%）：用多个原版物品/方块/机制组合实现，例如 `written_book` + `advancement` + `tellraw` 组合实现"线索书解锁"
- **L3 必要自定义**（~5%）：仅当 L1/L2 均不足且满足必要性+关联性时才允许，例如自定义"残破笔记"作为 `written_book` 的子类型

模组自定义内容累计仅 5 项（残破笔记、Patchouli 线索书、0 号唱片、先民储藏室、残破石碑），每项均通过严格的关联性论证与退化方案设计，确保模组卸载后存档仍可正常使用。

#### 世界观总览

主世界、下界、末地的建筑与生物源自同一支远古先民文明——他们曾掌握维度穿行技术，研究四大领域：

- **维度穿行**：要塞、传送门、末地城
- **红石机械**：废弃矿井、试炼密室
- **灵魂能量**：下界要塞、凋灵实验
- **生命本源**：苍白花园、树脂实验

文明鼎盛期并行研究，但三大实验先后失控：凋灵实验失控引发凋灵之灾，幽匿实验失控引发幽匿之厄，生命树脂实验失控引发苍白之悔。文明崩解后，三界据点荒废，族群各自演化——村民、猪灵、末影人、骷髅、恶魂、嘎枝，皆为后裔。

#### 玩家体验

你不是先民后裔，你是局外人。但通过探索遗迹、收集残破笔记、解读原版唱片、击杀原版 Boss，你将逐步拼凑出整个真相。

模组采用十阶段玩家体验路径，覆盖从出生到真结局的完整旅程：

1. 种子埋下 → 2. 主世界考古 → 3. 下界初探 → 4. 下界深处 → 5. 远古城市 → 6. 苍白花园 → 7. 进入末地 → 8. 末地城探索 → 9. 末影人的记忆 → 10. 真结局

每个阶段都通过原版 `advancement` 触发器自动解锁线索书章节，**不强制阻止玩家自由探索**。玩家可按任意顺序探索，但叙事文本会通过软引导（"认知锁"机制）建议玩家先体验叙事内容再挑战末地。

#### 真结局

收集全部 22 张原版唱片 + 模组合成的 0 号唱片，玩家将听到先民领袖 M. 的遗言：

> 「他们不是英雄，不是叛徒，不是怪物。他们只是一群完成任务的士兵，在任务完成后发现……总部已经不在了。」

这是模组叙事的最高潮，也是对原版末影人留白的最深刻解读——末影人不是怪物，是被遗忘的士兵。

#### 兼容性

- **不修改任何原版机制**（生物 AI、生成、掉落、合成、结构生成）
- **可选兼容**：Patchouli（线索书增强）、JEI（合成查询）
- **存档兼容**：升级 / 卸载 / 重装三种场景均保证存档可用
- **多人服务器**：可作为服务端模组运行，客户端无需安装
- **多语言**：首发 zh_cn + en_us，v1.0 前扩展至 8 语言

#### 发布计划

- **2028 年 12 月**：预发布 Beta（v0.9），完整主线 + zh_cn + en_us + ja_jp
- **2029 年 5 月**：正式发布（v1.0），8 语言全覆盖，CurseForge + Modrinth + MC 百科同步

---

## 6. 特性清单

用于发布说明、宣传材料、Modrinth 标签列表。

### 6.1 核心特性

- ✅ **三界同源叙事**：主世界、下界、末地的建筑与生物皆源自同一支远古先民文明
- ✅ **碎片化叙事**：通过残破笔记、铭文、唱片碎片，玩家自行拼凑真相
- ✅ **原版机制优先**：~80% 内容用纯原版机制承载，~15% 用原版组合，仅 ~5% 必要自定义
- ✅ **软引导而非强制**：认知锁机制仅提示，不阻止玩家自由探索
- ✅ **十阶段玩家路径**：从出生到真结局的完整叙事旅程
- ✅ **多角色叙事网络**：M.、H.、K.、T.、E. 五位角色的多视角拼图
- ✅ **真结局**：0 号唱片触发先民领袖遗言
- ✅ **多语言首发**：zh_cn + en_us，v1.0 前扩展至 8 语言

### 6.2 原版内容串联

- ✅ **遗迹串联**：要塞、远古城市、苍白花园、试炼密室、下界要塞、堡垒遗迹、末地城、末地船
- ✅ **种族串联**：村民、猪灵、末影人、骷髅、恶魂、嘎枝、灾厄村民
- ✅ **物品串联**：下界合金、附魔台、青金石、紫颂果、远古残骸、紫珀砖、试炼钥匙
- ✅ **Boss 串联**：凋灵、监守者、末影龙
- ✅ **唱片串联**：22 张原版唱片均赋予叙事解读

### 6.3 兼容性

- ✅ **加载器**：Fabric（首选）/ NeoForge（计划支持）
- ✅ **依赖**：Patchouli（软依赖）、JEI（可选兼容）
- ✅ **存档兼容**：升级 / 卸载 / 重装三场景保证
- ✅ **多人服务器**：可作为服务端模组运行
- ✅ **不修改任何原版机制**

### 6.4 模组标签（用于 Modrinth / CurseForge）

`fabric` `story` `lore` `narrative` `vanilla-friendly` `exploration` `quests` `books` `advancements` `chinese-translation` `english-translation`

---

## 7. 常见问答（FAQ）

用于 Modrinth / CurseForge 评论区置顶、Discord FAQ 频道。

### Q1：这个模组会改变原版游戏机制吗？

**A**：不会。模组严格遵循"不魔改原版交互"原则——不新增可驯服/骑乘机制，不改变生物 AI、生成、掉落，不修改合成、结构生成。所有叙事通过原版 `written_book`、`advancement` 触发器、`tellraw` 命令呈现。

### Q2：模组需要哪些前置模组？

**A**：无强制前置。Patchouli 是软依赖，缺失时降级为 `tellraw` 显示文本，仍可正常游玩。JEI 是可选兼容，仅用于合成查询。

### Q3：模组支持哪些 Minecraft 版本？

**A**：首发目标 Minecraft 1.21.11+（Java Edition）。后续随 Minecraft 版本更新扩展，不向下兼容 1.20 及更早版本。

### Q4：模组支持哪些语言？

**A**：首发 zh_cn（简体中文）+ en_us（英文）。v0.5 引入 ja_jp（日文）。v1.0 前扩展至 8 语言（含 ko_kr、de_de、fr_fr、ru_ru、es_es）。

### Q5：模组是开源的吗？

**A**：模组代码采用 MIT/LGPL 协议开源。叙事资产（文本、纹理、结构布局）闭源，正式开源预计 2029 年 5 月与模组正式发布同步。

### Q6：模组可以加入整合包吗？

**A**：可以，但建议作为"独立叙事模组"使用。与其他叙事模组（如 Twilight Forest）混用时可能存在叙事冲突。

### Q7：模组支持多人服务器吗？

**A**：支持。模组可作为服务端模组运行，客户端无需安装。每个玩家独立判定 advancement 与线索书进度。

### Q8：模组会导致存档损坏吗？

**A**：不会。所有自定义内容均设计有"退化方案"——模组卸载后，所有自定义物品退化为原版等价物（如残破笔记退化为 `written_book`），存档完全可用。详见 [`planning/13-save-compatibility.md`](./13-save-compatibility.md)。

### Q9：模组会引入新维度 / 新 Boss / 新生物吗？

**A**：不会。这是模组"永远禁止"清单的明确内容——不新增新维度、新 Boss（作为新实体）、新生物、新种族、新数值系统。所有叙事通过对原版内容的解读呈现，而非通过新增内容展示。

### Q10：模组的真结局是什么？

**A**：玩家收集全部 22 张原版唱片后，可通过合成获得模组的 0 号唱片。播放 0 号唱片将听到先民领袖 M. 的遗言，揭示末影人的真实身份——"他们不是英雄，不是叛徒，不是怪物。他们只是一群完成任务的士兵，在任务完成后发现……总部已经不在了。"

---

## 8. 媒体宣传文案

用于 Twitter / Discord / 视频简介。

### 8.1 Twitter 短文案（280 字符以内）

#### 中文版

> 📜 Remnant / Echo —— 一个 Minecraft 原版叙事模组
>
> 主世界、下界、末地，曾属于同一支远古先民文明。
> 他们崩解后，村民、猪灵、末影人，皆为其后裔。
>
> 你不是后裔。你是局外人。
> 但通过考古、线索、Boss 与叙事文本，你将拼凑出整个真相。
>
> 🌐 https://github.com/qwq672/ancient-echo
> 📅 预发布 2028-12 · 正式发布 2029-05

#### 英文版

> 📜 Remnant / Echo — A Minecraft vanilla narrative mod
>
> The Overworld, Nether, and End belonged to one ancient civilization.
> After their collapse, villagers, piglins, and endermen became their descendants.
>
> You are not their heir. You are an outsider.
> But through archaeology, clues, bosses, and narrative text, you'll piece together the whole truth.
>
> 🌐 https://github.com/qwq672/ancient-echo
> 📅 Beta Dec 2028 · Release May 2029

### 8.2 Discord 长文案

#### 中文版

> **📜 Remnant / Echo · Minecraft 原版叙事模组**
>
> 你是否曾想过，为什么主世界、下界、末地的石砖工艺如此相似？为什么凋灵骷髅只出现在下界要塞？为什么末地城空置、紫珀砖与主世界石砖工艺一致？为什么末影人怕水、怕光？
>
> **Remnant / Echo** 通过碎片化叙事，将原版这些零散线索合理串联，构建一支远古先民文明在三界兴衰的史诗。
>
> **三大原则**：
> - 不魔改原版交互——不改变生物 AI、生成、掉落
> - 不脱离官方留白——只做合理串联，不填补留白
> - 碎片化叙事——玩家在探索中自行拼凑真相
>
> **十阶段玩家路径**：种子埋下 → 主世界考古 → 下界初探 → 远古城市 → 苍白花园 → 进入末地 → 末影人的记忆 → 真结局
>
> **真结局**：收集全部 22 张原版唱片 + 合成 0 号唱片，听到先民领袖 M. 的遗言：
> > 「他们不是英雄，不是叛徒，不是怪物。他们只是一群完成任务的士兵，在任务完成后发现……总部已经不在了。」
>
> 🌐 https://github.com/qwq672/ancient-echo
> 📅 预发布 Beta：2028 年 12 月
> 📅 正式发布：2029 年 5 月（Minecraft 20 周年窗口）
> 🌍 首发 zh_cn + en_us，v1.0 前 8 语言

### 8.3 视频简介（YouTube / Bilibili）

#### 中文版

> **Remnant / Echo · Minecraft 原版叙事模组介绍**
>
> 一个不魔改原版、不脱离官方留白的叙事模组——通过考古、线索、Boss 与叙事文本，拼凑一支远古文明在三界兴衰的史诗。
>
> 主世界、下界、末地，曾属于同一支远古先民文明。他们崩解后，村民、猪灵、末影人，皆为其后裔。
>
> 你不是后裔。你是局外人。但通过探索，你将拼凑出整个真相——并最终听到先民领袖的遗言。
>
> **本视频将带你了解**：
> - 模组设计哲学：为什么"优先原版"是最高原则？
> - 十阶段玩家路径：从出生到真结局的完整旅程
> - 多角色叙事网络：M.、H.、K.、T.、E. 五位角色的拼图
> - 真结局：0 号唱片与末影人的真相
>
> 🌐 https://github.com/qwq672/ancient-echo
> 📅 预发布 Beta：2028 年 12 月
> 📅 正式发布：2029 年 5 月

---

## 9. 文案版本管理

### 9.1 多语言版本与同步

按 [`11-localization-strategy.md`](./11-localization-strategy.md)：

- **首发语言**（v0.1 ~ v0.6）：zh_cn + en_us，双源同步，互为校对
- **v0.5 扩展**：ja_jp，由项目方亲译，与 zh_cn / en_us 互校
- **v1.0 扩展**：8 语言，社区贡献 PR，项目方审核

### 9.2 文案与模组版本的同步

文案与模组版本同步更新：

- **v0.1 ~ v0.5**：文案为草稿状态，仅用于内部测试与开发交流
- **v0.6**：文案定稿，准备发布说明
- **v0.9**：文案公开发布，用于 Modrinth / CurseForge Beta 上线
- **v1.0**：文案最终修订，用于正式发布

### 9.3 文案与实际内容的一致性

每次文案更新前，必须核对：

- [ ] 模组实际功能与文案描述一致
- [ ] 兼容性声明与实际测试一致
- [ ] 发布日期与 [`12-release-roadmap.md`](./12-release-roadmap.md) 一致
- [ ] 多语言版本与 [`11-localization-strategy.md`](./11-localization-strategy.md) 一致
- [ ] 自定义内容清单与 [`10-custom-items-registry.md`](./10-custom-items-registry.md) 一致

---

## 10. 待讨论的设计问题

- [ ] 模组名最终确定：Remnant vs Echo vs Pale vs Sonder？（倾向：v0.5 前确定，v0.6 后所有文案采用最终名）
- [ ] 是否需要"宣传视频"脚本？（倾向：v0.9 前制作，发布在 YouTube / Bilibili）
- [ ] 是否需要"开发者日志"系列？（倾向：v0.1 后每月一篇，发布在 GitHub Blog / Bilibili 专栏）
- [ ] 是否需要"社区贡献指南"文案？（倾向：v0.6 后开放社区翻译，需配套指南）
- [ ] 是否需要"卸载指南"文案？（倾向：是，作为 [`13-save-compatibility.md`](./13-save-compatibility.md) 的玩家友好版）

---

## 11. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-18 | v0.1 | 初稿，提供 6 种文案形态（一句话/段落/完整/特性清单/FAQ/媒体宣传）的 zh_cn + en_us + ja_jp 多语言版本 | 项目方 |
