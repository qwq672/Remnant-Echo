# Remnant / Echo · Minecraft 原版故事观资料汇编

> 🌐 **仓库地址**：https://github.com/qwq672/ancient-echo
> **项目代号**：Remnant（暂定名）/ Echo（候选名）
> **类型**：基于 Minecraft 原版碎片化线索构建的叙事模组资料库
> **当前阶段**：蓝图 / 资料收集阶段（2026-09-18 启动）
> **目标版本**：Minecraft 1.21.11+（首个正式版）
> **计划正式发布**：2029 年 5 月（Minecraft 20 周年窗口）
> **版权状态**：项目计划中，仍在实验，暂不开源但允许展示，正式开源前请勿照搬，暂保留所有权利

---

## 📖 关于本仓库

本仓库为 Minecraft 原版故事观叙事模组 **Remnant / Echo** 的资料汇编。所有内容均为原文引用，不做任何改写或描述，每段引用后均标注来源链接。

引用来源按权威性排序：
1. **minecraft.net** — Mojang 官方发布（更新公告、Meet the Mob、Around the Block、Block of the Week/Month、Taking Inventory 等系列）
2. **minecraft.wiki** — 社区维护的权威 Wiki
3. **en.wikipedia.org / en.wikisource.org** — 维基百科与维基文库（End Poem 公共领域全文以 Wikisource 版本为准）
4. **matpat.fandom.com** — MatPat / Game Theory 社区理论，仅作参考

---

## 📚 目录结构

```
.
├── README.md                              ← 本文件（主索引）
├── BLUEPRINT.md                           ← 项目蓝图总览（整合版，五大原则 + 世界观 + 路线图）
├── 00-overview/                           ← 世界观与原版叙事总纲
│   ├── 01-end-poem.md                     ← End Poem 全文（公共领域）
│   ├── 02-end-poem-wikipedia.md           ← End Poem 维基百科背景
│   ├── 03-music-of-minecraft.md           ← Minecraft 音乐总览
│   └── 04-matpat-complete-lore.md         ← MatPat Game Theory 完整理论
├── 01-pale-garden/                        ← 苍白花园与嘎枝
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 02-happy-ghast/                        ← 快乐恶魂与恶魂家族
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 03-ancient-city-warden/                ← 远古城市 / 监守者 / 幽匿
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 04-trial-chambers/                     ← 试炼密室
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 05-villager-family/                    ← 村民系列
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 06-piglin-family/                      ← 猪灵与僵尸猪灵
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 07-ender-family/                       ← 末影人 / 末影龙 / 末地
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 08-illagers/                           ← 灾厄村民
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 09-wither-and-nether-fortress/         ← 凋灵 / 凋灵骷髅 / 下界要塞
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 10-other-hostile-mobs/                  ← 骷髅 / 苦力怕 / 其他敌对生物
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 11-overworld-structures/               ← 主世界关键遗迹
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 12-key-items/                          ← 关键物品（下界合金 / 附魔 / 紫颂果）
│   ├── 01-minecraft-net-articles.md
│   └── 02-minecraft-wiki.md
├── 13-music-discs/                        ← 唱片系统
│   ├── 01-minecraft-net-articles.md
│   ├── 02-minecraft-wiki.md
│   └── 03-wikipedia.md
├── 14-official-derivatives/               ← 官方衍生作品
│   ├── 01-minecraft-legends.md
│   └── 02-minecraft-dungeons.md
├── planning/                              ← 项目规划文档（设计决策与思考过程）
│   ├── 00-planning-index.md               ← 规划总索引 + 顶层设计原则（L1/L2/L3）
│   ├── 01-spawn-point-design.md           ← 玩家出生点叙事设计
│   ├── 02-story-timeline-plan.md          ← 故事时间线规划（六大纪元）
│   ├── 03-player-journey-map.md          ← 玩家体验路径图（十阶段）
│   ├── 04-auto-sync-strategy.md          ← 自动同步方案（GitHub Action）
│   ├── 05-clue-book-system.md            ← 线索书系统设计（Patchouli）
│   ├── 06-cognitive-lock-mechanism.md    ← 认知锁机制（advancement 配置）
│   ├── 07-boss-narrative-binding.md      ← Boss 叙事绑定
│   ├── 08-music-disc-unlock-order.md     ← 唱片解锁顺序与剧情对应
│   ├── 09-village-loot-extension.md      ← 5 个原版 loot 表详细配置
│   ├── 10-custom-items-registry.md       ← L3 自定义物品登记表
│   ├── 11-localization-strategy.md       ← 多语言支持策略
│   ├── 12-release-roadmap.md             ← 发布路线图（v0.1 ~ v1.0 里程碑）
│   ├── 13-save-compatibility.md         ← 存档兼容性策略
│   ├── 14-trial-chamber-narrative.md     ← 试炼密室叙事
│   ├── 15-netherite-enchantment-essence.md ← 下界合金 / 附魔本质叙事
│   ├── 16-worldview-overview.md         ← 面向读者的世界观总纲
│   └── 17-mod-introduction-copy.md       ← 对外模组介绍文案（多语言）
└── 99-source-index.md                     ← 完整来源索引（139 条 URL）
```

---

## 📊 统计信息

- **主题章节数**：15（`00-overview/` ~ `14-official-derivatives/`）
- **规划文档数**：18（`planning/00-planning-index.md` ~ `planning/17-mod-introduction-copy.md`）
- **来源页面总数**：133
- **Markdown 文件总数**：53（含 18 个规划文档 + 根目录 BLUEPRINT.md + 主索引 README.md + 99-source-index.md + CONTRIBUTING.md + PUSH_TO_GITHUB.md + CHANGELOG.md）
- **原文引用段落数**：约 1,400+ 条
- **总大小**：约 1.1 MB

---

## 📌 资料权威性分级

| 级别 | 来源 | 说明 |
|------|------|------|
| ★★★★★ | minecraft.net | Mojang 官方发布，包括更新公告、Meet the Mob、Around the Block、Block of the Week/Month、Taking Inventory 等系列 |
| ★★★★ | minecraft.wiki | 社区维护的权威 Wiki，内容由玩家协作维护 |
| ★★★ | en.wikipedia.org / en.wikisource.org | 维基百科与维基文库，End Poem 公共领域全文以 Wikisource 版本为准 |
| ★★ | matpat.fandom.com | MatPat / Game Theory 社区理论，仅作参考 |

---

## 📖 使用建议

1. **叙事素材引用**：所有原文段落均使用 Markdown 引用块（`> ...`）格式，可直接复制到模组文档或线索书中作为素材。
2. **链接校验**：每个来源都标注了原始 URL，可点击直接访问。
3. **版权说明**：
   - minecraft.net 文章版权归 Mojang / Microsoft 所有，本仓库仅作研究引用。
   - minecraft.wiki 内容采用 CC BY-NC-SA 3.0 协议。
   - End Poem 由 Julian Gough 于 2022 年释出至公共领域（CC0），可自由使用。
   - 维基百科内容采用 CC BY-SA 协议。
4. **更新策略**：本仓库与 Minecraft 版本更新同步，新版本发布后会追加对应章节。

---

## 🔗 模组项目信息

> 模组项目 **Remnant / Echo** 当前处于蓝图阶段，预计 2028 年 12 月预发布，2029 年 5 月正式发布。

- 模组代码开源协议：MIT / LGPL
- 叙事资产（文本、纹理、结构布局）：闭源
- 发布平台：CurseForge、Modrinth、MC 百科

### 项目原则

1. 不魔改原版交互逻辑
2. 贴合原版留白逻辑
3. 碎片化叙事
4. 三界同源
5. 基于官方衍生作品可参考，但以原版为准

---

## 📝 文档协议与版权状态

> ⚠️ **当前阶段：项目计划中，仍在实验，暂不开源但允许展示，正式开源前请勿照搬，暂保留所有权利。**

- 本汇编文档当前为 **Remnant / Echo 模组项目内部资料**，与项目主体一同暂保留所有权利。
- 引用的原文版权归原作者所有：
  - minecraft.net 文章版权归 Mojang / Microsoft 所有，本仓库仅作研究引用。
  - minecraft.wiki 内容采用 CC BY-NC-SA 3.0 协议。
  - End Poem 由 Julian Gough 于 2022 年释出至公共领域（CC0），可自由使用。
  - 维基百科内容采用 CC BY-SA 协议。
- **正式开源后**（预计 2029 年 5 月与模组正式发布同步），本汇编文档将以 CC BY 4.0 协议发布。
- 欢迎通过 Issue 反馈遗漏或错误，但**不接受外部 Pull Request 直接修改引用原文**（保持原文不可改写原则）。

---

## 🤝 贡献与协作

- **欢迎提交 Issue**：报告断链、过时信息、新资料建议、章节归档错误等
- **暂不接受 Pull Request**：当前阶段为项目内部资料管理，所有引用与归档由项目方统一维护，确保原文不可改写原则
- 若你发现遗漏的官方原文，欢迎在 Issue 中提供 URL，项目方会审核后纳入对应章节

---

## 📅 更新历史

- **2026-09-18**：初始版本，启动资料收集阶段。覆盖 15 个主题章节，133 个来源页面。推送到 `qwq672/ancient-echo` 仓库。
- **2026-09-18（v0.2 资料完善）**：新增 `BLUEPRINT.md` 项目蓝图总览；新增 7 份规划文档（11-localization-strategy / 12-release-roadmap / 13-save-compatibility / 14-trial-chamber-narrative / 15-netherite-enchantment-essence / 16-worldview-overview / 17-mod-introduction-copy）；规划文档总数从 11 增至 18。
