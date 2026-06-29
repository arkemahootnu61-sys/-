# -
这是我的学习笔记，记录一下我的学习过程中的笔记还有理解，以便及时的学习和巩固

## 两台电脑同步方法

### 首次设置（新电脑）

```bash
# 1. 克隆仓库
git clone https://github.com/arkemahootnu61-sys/-.git ~/Documents/my-notes-repo

# 2. 安装 GitHub CLI（如果没有）
brew install gh

# 3. 登录 GitHub
gh auth login

# 4. 配置 git 使用 gh 认证
gh auth setup-git
```

### 日常同步

**上传笔记（当前电脑 → GitHub）：**
```bash
cd ~/Documents/my-notes-repo
git add -A
git commit -m "更新笔记 $(date +%Y-%m-%d)"
git push
```

**下载笔记（GitHub → 当前电脑）：**
```bash
cd ~/Documents/my-notes-repo
git pull
```

### 添加快捷命令（可选）

在 `~/.zshrc` 中添加：

```bash
alias push-notes='cd ~/Documents/my-notes-repo && git add -A && git commit -m "更新笔记 $(date +%Y-%m-%d)" && git push'
alias pull-notes='cd ~/Documents/my-notes-repo && git pull'
```

之后直接在终端用 `push-notes` 上传、`pull-notes` 下载。
