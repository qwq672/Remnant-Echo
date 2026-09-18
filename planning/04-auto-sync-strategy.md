# 04 · 自动同步方案

> **状态**：🟢 计划中（v0.5 之后实施）
> **对应模组版本**：v0.5+
> **创建日期**：2026-09-18
> **最后更新**：2026-09-18

---

## 1. 目的

建立自动追踪 Minecraft 官方更新的机制，确保本资料库与原版同步，不遗漏新内容。

**核心原则**：仅做**变更检测**，不做内容判断。AI 不决定新资料如何归档，由项目方人工审核。

---

## 2. 三种自动同步方案对比

### 方案 A：GitHub Action 定时任务（推荐 ✅）

| 维度 | 评价 |
|------|------|
| 自动化程度 | ★★★★★ 完全自动，定时执行 |
| 实现复杂度 | ★★★☆☆ 需编写 Python 脚本 |
| 人工介入 | 仅审核新文章归档建议 |
| 资源消耗 | GitHub Action 免费额度足够 |
| **结论** | ✅ 采用为主方案 |

**实现思路**：
1. GitHub Action 每周定时运行
2. 抓取 `minecraft.net/en-us/sitemap.xml`
3. 与仓库内已有的 URL 列表（`99-source-index.md`）对比
4. 发现新文章 → 自动创建 Issue 提示「建议归入 XX 章节」
5. 项目方审核后人工补充

### 方案 B：RSS / Atom 订阅

| 维度 | 评价 |
|------|------|
| 自动化程度 | ★★★★☆ 需要订阅工具 |
| 实现复杂度 | ★★☆☆☆ 配置 RSS 阅读器 |
| 人工介入 | 完全人工 |
| 资源消耗 | 无 |
| **结论** | 🟡 备选方案，适合个人订阅 |

**实现思路**：
1. 订阅 minecraft.net 的 RSS（如有）
2. 新文章通知到邮箱 / Telegram
3. 人工判断是否纳入资料库
4. 手动执行抓取脚本

### 方案 C：Mojang 官方 API

| 维度 | 评价 |
|------|------|
| 自动化程度 | ★★★★★ |
| 实现复杂度 | ★★★★★ Mojang 无公开内容 API |
| 人工介入 | 无 |
| 资源消耗 | 无 |
| **结论** | ❌ 不可行，Mojang 未提供内容 API |

---

## 3. 推荐方案：GitHub Action 定时任务

### 3.1 工作流设计

```
每周一 09:00 UTC 触发
        ↓
Action 启动
        ↓
拉取 minecraft.net/en-us/sitemap.xml
        ↓
解析所有 /en-us/article/ URL
        ↓
读取本仓库 99-source-index.md 中已有的 URL
        ↓
计算差集：新 URL 列表
        ↓
对每个新 URL：
    ├─ 抓取页面标题、发布时间
    ├─ 根据标题关键词初步归档（如下界、末地、村民等）
    └─ 生成 Issue 描述
        ↓
创建 GitHub Issue：「发现 N 篇新官方文章，建议归入对应章节」
        ↓
项目方人工审核 Issue
        ↓
项目方决定：
    ├─ 纳入 → 手动执行抓取脚本补充到对应章节
    └─ 不纳入 → 关闭 Issue
```

### 3.2 关键词归档建议表

Action 根据标题关键词初步判断归档建议：

| 关键词 | 建议归入章节 |
|--------|-------------|
| pale garden, creaking, pale oak | `01-pale-garden/` |
| happy ghast, ghastling, dried ghast | `02-happy-ghast/` |
| ancient city, warden, sculk, deep dark | `03-ancient-city-warden/` |
| trial chamber, vault, trial key | `04-trial-chambers/` |
| villager, wandering trader, nitwit, iron golem | `05-villager-family/` |
| piglin, zombified piglin, bastion | `06-piglin-family/` |
| enderman, ender dragon, end city, shulker, chorus | `07-ender-family/` |
| illager, pillager, vindicator, evoker, ravager, vex, woodland mansion | `08-illagers/` |
| wither, wither skeleton, nether fortress | `09-wither-and-nether-fortress/` |
| creeper, skeleton, husk, stray, blaze, phantom, silverfish, witch | `10-other-hostile-mobs/` |
| stronghold, end portal, ruined portal, desert temple, jungle temple, mineshaft, trail ruins, suspicious sand, archaeology, brush | `11-overworld-structures/` |
| netherite, ancient debris, enchanting table, chorus fruit | `12-key-items/` |
| music disc, disc 11, disc 5, pigstep, otherside, relic, creator, precipice | `13-music-discs/` |
| minecraft legends, minecraft dungeons | `14-official-derivatives/` |

### 3.3 示例 Action 配置

```yaml
# .github/workflows/sync-minecraft-news.yml
name: Sync Minecraft News

on:
  schedule:
    # 每周一 09:00 UTC（北京 17:00）
    - cron: '0 9 * * 1'
  workflow_dispatch: # 允许手动触发

jobs:
  sync:
    runs-on: ubuntu-latest
    permissions:
      issues: write
      contents: read
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      
      - name: Install dependencies
        run: pip install requests beautifulsoup4 pyyaml
      
      - name: Run sync script
        env:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        run: python scripts/sync_official_news.py
```

### 3.4 同步脚本框架（伪代码）

```python
# scripts/sync_official_news.py

import requests
import re
import yaml
from datetime import datetime
from pathlib import Path

SITEMAP_URL = "https://www.minecraft.net/en-us/sitemap.xml"
SOURCE_INDEX_PATH = "99-source-index.md"

# 关键词归档表
KEYWORD_MAP = {
    "pale garden": "01-pale-garden/",
    "creaking": "01-pale-garden/",
    # ... (完整映射见 3.2 节)
}

def fetch_sitemap_urls():
    """抓取 sitemap 中所有 article URL"""
    resp = requests.get(SITEMAP_URL, timeout=30)
    urls = re.findall(r'(/en-us/article/[a-z0-9\-]+)', resp.text)
    return sorted(set(urls))

def load_existing_urls():
    """从 99-source-index.md 读取已有的 URL"""
    content = Path(SOURCE_INDEX_PATH).read_text(encoding='utf-8')
    return set(re.findall(r'<(https://[^>]+)>', content))

def fetch_article_meta(url):
    """抓取文章标题、发布时间、描述"""
    resp = requests.get(url, timeout=30)
    title = re.search(r'<title>(.*?)</title>', resp.text)
    desc = re.search(r'<meta name="description" content="([^"]+)"', resp.text)
    return {
        'url': url,
        'title': title.group(1) if title else 'Unknown',
        'description': desc.group(1) if desc else '',
    }

def suggest_section(title, description):
    """根据标题与描述关键词建议归档章节"""
    text = (title + ' ' + description).lower()
    for keyword, section in KEYWORD_MAP.items():
        if keyword in text:
            return section
    return '(未匹配，需人工判断)'

def main():
    sitemap_urls = fetch_sitemap_urls()
    existing_urls = load_existing_urls()
    
    new_articles = []
    for path in sitemap_urls:
        full_url = 'https://www.minecraft.net' + path
        if full_url not in existing_urls:
            meta = fetch_article_meta(full_url)
            meta['suggested_section'] = suggest_section(meta['title'], meta['description'])
            new_articles.append(meta)
    
    if not new_articles:
        print("No new articles found.")
        return
    
    # 创建 GitHub Issue
    issue_body = format_issue_body(new_articles)
    create_github_issue(issue_body, new_articles_count=len(new_articles))

def format_issue_body(articles):
    body = ["发现 %d 篇新官方文章，建议归档如下：\n" % len(articles)]
    for i, a in enumerate(articles, 1):
        body.append(f"### {i}. {a['title']}")
        body.append(f"- URL: {a['url']}")
        body.append(f"- 描述: {a['description']}")
        body.append(f"- 建议归档: `{a['suggested_section']}`")
        body.append("")
    body.append("---")
    body.append("请项目方审核后，手动执行 `python scripts/fetch_lore_pages.py` 抓取页面，")
    body.append("再执行 `python scripts/split_lore_files.py` 拆分到对应章节。")
    return '\n'.join(body)

def create_github_issue(body, new_articles_count):
    """通过 GitHub API 创建 Issue"""
    # 使用环境变量 GH_TOKEN
    # POST https://api.github.com/repos/qwq672/ancient-echo/issues
    # 详细实现略
    pass

if __name__ == '__main__':
    main()
```

---

## 4. 实施时间表

| 模组版本 | 实施内容 |
|----------|----------|
| v0.1 ~ v0.4 | 不实施，依赖人工追踪 |
| v0.5 | 实施 GitHub Action，每周自动检测新文章 |
| v0.6 | 完善 Action：加入 minecraft.wiki 条目变更检测 |
| v0.9 | 完善 Action：加入发布前最终复核报告 |
| v1.0 | 稳定运行，与模组正式发布同步 |

---

## 5. 备选方案：SyntaxMine 社区文章同步

SyntaxMine 是 SPA，URL 不可被搜索引擎直接抓取。可考虑：

1. **手动订阅**：项目方关注 SyntaxMine 的 Twitter / RSS（如有）
2. **截图归档**：发现新文章后截图存入 `15-community-lore/` 目录
3. **可选抓取**：通过 Playwright 等 headless browser 抓取 SPA 渲染后的内容

**实施优先级**：低，v1.0 之后考虑。

---

## 6. 待讨论的设计问题

- [ ] Action 触发频率：每周一次 vs 每天一次？建议每周，避免告警疲劳
- [ ] 是否同步抓取 minecraft.wiki 的条目更新？建议是，但 wiki 变更频繁，可能产生大量 Issue
- [ ] 新文章抓取后是否自动创建 Pull Request？建议否，保持人工审核
- [ ] 是否同步追踪 Mojang 官方博客、Twitter 等非 minecraft.net 渠道？建议 v1.0 后考虑

---

## 7. 修订历史

| 日期 | 版本 | 修订内容 | 修订者 |
|------|------|----------|--------|
| 2026-09-18 | v0.1 | 初稿，提出 GitHub Action 定时任务方案 | 项目方 |
