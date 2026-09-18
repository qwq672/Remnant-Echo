# 推送到 GitHub 的操作指南

本仓库已初始化为本地 Git 仓库，可直接推送到 GitHub。

## 🚀 快速推送步骤

### 1. 在 GitHub 上创建空仓库

在 GitHub 上创建一个新的空仓库（**不要**勾选 Initialize with README，避免冲突）：

- 建议仓库名：`remnant-mc-lore` 或 `echo-mc-lore`
- 可见性：建议 `Public`（资料库性质，方便社区贡献）
- 不勾选任何初始化选项

### 2. 获取仓库 URL

GitHub 仓库创建后会显示 HTTPS 或 SSH URL，例如：
- HTTPS: `https://github.com/your-username/remnant-mc-lore.git`
- SSH: `git@github.com:your-username/remnant-mc-lore.git`

### 3. 添加远程并推送

```bash
cd /home/z/my-project/download/lore

# 添加远程仓库（替换为你的实际 URL）
git remote add origin https://github.com/<your-username>/remnant-mc-lore.git

# 推送到 GitHub
git push -u origin main
```

### 4. 验证推送

打开 GitHub 仓库页面，应该能看到所有 35 个 Markdown 文件已上传。

---

## 🔐 认证方式

### 方式一：Personal Access Token（HTTPS 推荐）

1. GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. 生成新 token，勾选 `repo` 权限
3. 推送时输入用户名 + token 作为密码

### 方式二：SSH Key

```bash
# 生成 SSH key（如果还没有）
ssh-keygen -t ed25519 -C "your-email@example.com"

# 复制公钥
cat ~/.ssh/id_ed25519.pub

# 添加到 GitHub → Settings → SSH and GPG keys → New SSH key
```

### 方式三：GitHub CLI

```bash
# 安装 gh CLI
sudo apt install gh  # 或 brew install gh

# 登录
gh auth login

# 推送
git push -u origin main
```

---

## 🔄 日常同步

### 拉取最新更新

```bash
git pull origin main
```

### 提交新资料

```bash
# 添加新文件或修改
git add -A

# 提交
git commit -m "Add: <新资料主题>"

# 推送
git push origin main
```

---

## 📦 推送后建议的仓库设置

1. **About**：在仓库主页右侧点击 ⚙️ 设置：
   - Description: `Minecraft 原版故事观叙事模组 Remnant / Echo 的资料汇编`
   - Website: 可填你的项目主页
   - Topics: `minecraft`, `minecraft-lore`, `modding`, `reference`, `documentation`

2. **GitHub Pages**（可选）：
   - Settings → Pages → Source: `main` branch
   - 选择主题（建议 `jekyll-theme-cayman` 或 `minimal`）
   - 等待几分钟后，可通过 `https://<username>.github.io/remnant-mc-lore/` 访问 README

3. **默认分支**：保持 `main`

4. **分支保护**（可选）：
   - Settings → Branches → Add rule
   - Branch name pattern: `main`
   - 勾选 "Require pull request reviews before merging"

---

## 🌐 作为子模块调用

如果模组主仓库希望引用本资料库作为子模块：

```bash
cd /path/to/remnant-mod-repo
git submodule add https://github.com/<your-username>/remnant-mc-lore.git docs/lore
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

## 📋 推送前的检查清单

- [ ] 已阅读 `CONTRIBUTING.md`
- [ ] 所有引用均使用 Markdown 引用块语法
- [ ] 每段引用都标注了原始 URL
- [ ] 文件归入正确的章节目录
- [ ] 文件命名符合规范
- [ ] `git status` 显示 working tree clean
- [ ] `git log` 显示最新 commit

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
