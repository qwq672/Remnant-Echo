# 贡献指南

欢迎为本资料汇编提交补充！为保证引用质量，请遵循以下规则。

---

## 📋 接受的资料类型

✅ **接受**：
- minecraft.net 官方文章（Meet the Mob、Around the Block、Block of the Week/Month、Taking Inventory、Snapshot/Preview 公告等）
- minecraft.wiki 条目
- en.wikipedia.org / en.wikisource.org 内容
- MatPat / Game Theory 社区理论（需明确标注为社区理论）
- Minecraft Wiki 上记录的开发者访谈、Minecraft Live 演讲原文

❌ **不接受**：
- 任何改写、摘要、二创内容
- 缺少原始 URL 的引用
- 中文社区翻译（除非是官方中文版）
- 个人推测或未经验证的理论

---

## 🛠 提交方式

### 1. 直接提交 Pull Request

1. Fork 本仓库
2. 在合适的章节目录下新建 Markdown 文件，或在已有文件追加引用
3. 引用格式：

   ```markdown
   ### 来源标题
   - **来源类型**：minecraft.net / minecraft.wiki / wikipedia / wikisource / matpat.fandom
   - **原文链接**：<https://...>
   - **发布时间**：YYYY-MM-DD（可选）
   - **页面摘要**：简短摘要（可选）

   **原文引用：**

   > 原文第一段

   > 原文第二段
   ```

4. 提交 PR，说明补充内容

### 2. 通过 Issue 推荐

如果不方便直接提交，欢迎在 [Issues](../../issues) 中提交：
- 标题：`[资料补充] 主题名`
- 内容：附上原文 URL 与建议归入的章节

---

## 📐 格式规范

### 引用块

- 所有引用必须使用 Markdown 引用块语法：`> `
- **保留原文措辞**，不修正错别字、不调整语序
- 段落分隔与原文一致

### 链接

- 使用 `<URL>` 形式（自动可点击），不用 `[text](url)` 形式，便于核对
- 不修改原始 URL（包括 query string）

### 段落限制

- 单个来源页面最多引用 8-15 段（避免大量复制）
- 超长段落（>3000 字符）应截断并标注：`[…]（段落过长已截断，完整内容请查阅原文链接）`

### 文件命名

- minecraft.net 文章合集：`01-minecraft-net-articles.md`
- minecraft.wiki 条目合集：`02-minecraft-wiki.md`
- 维基百科：`03-wikipedia.md`
- 单独主题文件：`01-{主题名}.md`

---

## 🗂 章节归档原则

| 主题 | 归入章节 |
|------|---------|
| 苍白花园 / 嘎枝 / 苍白橡树 | `01-pale-garden/` |
| 快乐恶魂 / 恶魂 / 恶魂之泪 / 干涸恶魂 / 善魂 | `02-happy-ghast/` |
| 远古城市 / 监守者 / 幽匿 / 深暗之域 | `03-ancient-city-warden/` |
| 试炼密室 / 不祥试炼 / 铜灯 / 试炼钥匙 | `04-trial-chambers/` |
| 村民 / 流浪商人 / 铁傀儡 / 傻瓜村民 | `05-villager-family/` |
| 猪灵 / 僵尸猪灵 / 猪灵蛮兵 / 堡垒遗迹 | `06-piglin-family/` |
| 末影人 / 末影龙 / 末地城 / 末地船 / 紫珀块 / 紫颂果 / 末影珍珠 / 末影之眼 / 潜影贝 | `07-ender-family/` |
| 灾厄村民 / 掠夺者 / 卫道士 / 唤魔者 / 劫掠兽 / 恼鬼 / 林地府邸 / 掠夺者前哨站 | `08-illagers/` |
| 凋灵 / 凋灵骷髅 / 下界要塞 | `09-wither-and-nether-fortress/` |
| 苦力怕 / 骷髅 / 流髑 / 尸壳 / 烈焰人 / 幻翼 / 蝙蝠 / 蜘蛛 / 洞穴蜘蛛 / 守卫者 / 远古守卫者 / 女巫 / 银鱼 | `10-other-hostile-mobs/` |
| 要塞 / 末地传送门 / 废弃传送门 / 沙漠神殿 / 丛林神庙 / 废弃矿井 / 考古 / 陶罐 / 陶片 / 哭泣黑曜石 / 重生锚 | `11-overworld-structures/` |
| 下界合金 / 远古残骸 / 附魔台 / 紫颂果 | `12-key-items/` |
| 唱片 13/cat/blocks/chirp/far/mall/mellohi/stal/strad/ward/11/wait/Pigstep/otherside/5/Relic/Creator/Creator (Music Box)/Precipice/Tears | `13-music-discs/` |
| Minecraft Legends / Minecraft Dungeons | `14-official-derivatives/` |

---

## ✅ PR 审核标准

- [ ] 引用段落使用正确的 Markdown 引用块语法
- [ ] 每个引用都标注了原始 URL
- [ ] 引用内容未做任何改写
- [ ] 文件归入正确的章节目录
- [ ] 文件命名符合规范
- [ ] 不包含个人推测或社区理论的二创内容
