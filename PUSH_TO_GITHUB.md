# 推送与同步指南（qwq672/ancient-echo）

本仓库已配置远程 `origin` 指向 GitHub 仓库：

```
https://github.com/qwq672/ancient-echo
```

---

## 🔄 日常同步操作

### 拉取最新更新

```bash
cd /home/z/my-project/download/lore
git pull origin main
```

### 提交并推送新资料

```bash
# 添加新文件或修改
git add -A

# 提交（建议使用规范的 commit message）
git commit -m "Add: <新资料主题>"     # 新增资料
git commit -m "Fix: <修正内容>"       # 修正错误
git commit -m "Docs: <文档变更>"      # 文档调整
git commit -m "Chore: <杂项>"         # 杂项维护

# 推送
git push origin main
```

---

## 🔐 认证方式

### 方式一：Personal Access Token（HTTPS · 推荐）

1. GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens
2. 生成新 token，仅授权 `qwq672/ancient-echo` 仓库的 `Contents: Read and write` 权限
3. 推送时输入用户名 `qwq672` + token 作为密码
4. 可选：使用 git credential helper 缓存 token
   ```bash
   git config --global credential.helper store
   # 第一次推送时输入 token，之后自动使用
   ```

### 方式二：SSH Key

```bash
# 生成 SSH key（如果还没有）
ssh-keygen -t ed25519 -C "167963232@qq.com"

# 复制公钥
cat ~/.ssh/id_ed25519.pub

# 添加到 GitHub → Settings → SSH and GPG keys → New SSH key

# 修改 remote 为 SSH URL
git remote set-url origin git@github.com:qwq672/ancient-echo.git
```

### 方式三：GitHub CLI

```bash
# 安装 gh CLI
sudo apt install gh

# 登录（浏览器授权）
gh auth login

# 推送
git push origin main
```

---

## 📦 仓库设置（已完成）

- **Owner**: `qwq672`
- **Repo**: `ancient-echo`
- **Visibility**: Public（允许展示，但暂保留所有权利）
- **Default branch**: `main`
- **Description**: 项目计划中，仍在实验，暂不开源但允许展示，正式开源前请勿照搬，暂保留所有权利

### 可选的后续设置

1. **Topics**：通过 API 或仓库主页设置标签
   - `minecraft` · `minecraft-lore` · `modding-reference` · `narrative-design`
2. **GitHub Pages**（可选）：
   - Settings → Pages → Source: `main` branch
   - 等待几分钟后，可通过 `https://qwq672.github.io/ancient-echo/` 访问 README
3. **Releases**：
   - 每个里程碑（如 v0.1.0、v0.2.0）可打 tag 发布
   - `git tag -a v0.1.0 -m "Initial lore collection"; git push origin v0.1.0`

---

## 🌐 作为子模块调用

如果模组主仓库希望引用本资料库作为子模块：

```bash
cd /path/to/remnant-mod-repo
git submodule add https://github.com/qwq672/ancient-echo.git docs/lore
git commit -m "Add lore reference as submodule"
```

后续更新：

```bash
cd docs/lore
git pull origin main
cd ../..
git add docs/lore
git commit -m "Update lore submodule"
```

---

## 🌐 通过 Raw URL 直接读取原文

推送到 GitHub 后，可通过 raw URL 直接读取任何 Markdown 文件原文：

```
https://raw.githubusercontent.com/qwq672/ancient-echo/main/<path-to-file>
```

例如读取 End Poem 全文：

```
https://raw.githubusercontent.com/qwq672/ancient-echo/main/00-overview/01-end-poem.md
```

### 通过 GitHub API 程序化读取

```bash
# 列出所有文件
curl -s -H "Accept: application/vnd.github+json" \
  https://api.github.com/repos/qwq672/ancient-echo/contents/ | jq -r '.[].path'

# 读取单个文件内容
curl -s -H "Accept: application/vnd.github.raw" \
  https://api.github.com/repos/qwq672/ancient-echo/contents/00-overview/01-end-poem.md
```

---

## 📋 提交前的检查清单

- [ ] 所有引用均使用 Markdown 引用块语法（`> `）
- [ ] 每段引用都标注了原始 URL
- [ ] 引用内容未做任何改写
- [ ] 文件归入正确的章节目录
- [ ] 文件命名符合规范（见 CONTRIBUTING.md）
- [ ] `git status` 显示 working tree clean（提交后）
- [ ] `git log --oneline` 显示最新 commit

---

## ❓ 常见问题

### Q: 推送时提示 "rejected - non-fast-forward"

```bash
git pull origin main --rebase
git push origin main
```

### Q: 想修改已提交的 commit message

```bash
git commit --amend -m "新的 commit message"
git push origin main --force-with-lease
```

### Q: 不小心提交了大文件

```bash
git rm --cached <文件路径>
git commit -m "Remove large file"
git push origin main
```

### Q: 想撤销最近的提交（保留改动）

```bash
git reset --soft HEAD~1
```

### Q: PAT 过期或失效

1. 在 GitHub 重新生成 PAT
2. 推送时输入新 token（如果用 credential helper store，需要先清除旧凭据）
   ```bash
   # 清除旧凭据
   git credential-store --file ~/.git-credentials erase
   # 输入：host=github.com\nprotocol=https\n
   ```
3. 或者直接使用 PAT 推送一次：
   ```bash
   git push https://<PAT>@github.com/qwq672/ancient-echo.git main
   ```
