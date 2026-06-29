---
name: sync-notes
description: 同步学习笔记到 GitHub（上传/下载）。用法 — /sync-notes push 或 /sync-notes pull
---

# 学习笔记 GitHub 同步

将本地学习笔记与 GitHub 仓库同步。

## 仓库信息
- 远程: `https://github.com/arkemahootnu61-sys/-.git`
- 本地: `C:\Users\feng\Desktop\学习笔记`
- 分支: `main`
- gh 路径: `C:\Program Files\GitHub CLI\gh.exe`

## 前置环境

执行 git push/pull 前，确保 PATH 包含 gh：
```
export PATH="$PATH:/c/Program Files/GitHub CLI"
```

如果 `gh auth status` 显示未登录，提示用户先在终端运行 `gh auth login`。

---

## 操作

### push（上传笔记到 GitHub）
用户说 `/sync-notes push` 或 `/sync-notes upload` 时执行：

```bash
cd "C:\Users\feng\Desktop\学习笔记" && \
export PATH="$PATH:/c/Program Files/GitHub CLI" && \
git status && \
git add -A && \
git commit -m "更新笔记 $(date '+%Y-%m-%d %H:%M')" && \
git push origin main
```

- 如果没有变更，跳过 commit 和 push
- 如果 push 失败提示认证问题，提醒用户运行 `gh auth login && gh auth setup-git`

### pull（从 GitHub 下载笔记）
用户说 `/sync-notes pull` 或 `/sync-notes download` 时执行：

```bash
cd "C:\Users\feng\Desktop\学习笔记" && \
export PATH="$PATH:/c/Program Files/GitHub CLI" && \
git pull origin main
```

- 如果有冲突，列出冲突文件，让用户手动解决

### status（查看同步状态）
用户说 `/sync-notes status` 时执行：

```bash
cd "C:\Users\feng\Desktop\学习笔记" && \
git status && \
echo "--- 最近提交 ---" && \
git log --oneline -5
```
