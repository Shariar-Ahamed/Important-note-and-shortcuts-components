<h2 align="center">GitHub 设置与主要代码 – 完整主指南 (简体中文)</h2>

<p align="center">
本文档是一份<b>全方位的 Git 与 GitHub 命令参考指南</b>，涵盖连接本地项目、推送更新、分支管理、冲突解决及日常工作流操作。
</p>

<div align="center">

### 🌐 选择语言 / Select Language:
[**🇺🇸 English**](../README.md) &nbsp;|&nbsp; [**🇧🇩 বাংলা**](README.bn.md) &nbsp;|&nbsp; [**🇪🇸 Español**](README.es.md) &nbsp;|&nbsp; [**🇮🇳 हिन्दी**](README.hi.md) &nbsp;|&nbsp; [**🇫🇷 Français**](README.fr.md) &nbsp;|&nbsp; [**🇩🇪 Deutsch**](README.de.md) &nbsp;|&nbsp; [**🇨🇳 中文**](README.zh.md) &nbsp;|&nbsp; [**🇸🇦 العربية**](README.ar.md)

</div>

---

## 📌 目录 (简体中文)

1. [Git 配置](#1-git-配置)
2. [GitHub 个人访问令牌 (PAT)](#2-github-个人访问令牌-pat)  
   2.1 [SSH 密钥身份验证设置](#21-ssh-密钥身份验证设置)
3. [连接本地仓库至远程](#3-连接本地仓库至远程)
4. [基础 Git 工作流](#4-基础-git-工作流)
5. [一键推送项目更改](#5-一键推送项目更改)
6. [处理已删除的文件](#6-处理已删除的文件)
7. [拉取最新代码 (Pull)](#7-拉取最新代码-pull)
8. [同步至 GitHub 最新版本](#8-同步至-github-最新版本)
9. [在 Windows 中启用长路径支持](#9-在-windows-中启用长路径支持)
10. [重命名文件夹与更新文件](#10-重命名文件夹与更新文件)
11. [移除 .vscode 文件夹跟踪](#11-移除-vscode-文件夹跟踪)
12. [重置 Git 仓库](#12-重置-git-仓库)
13. [特性分支推送工作流](#13-特性分支推送工作流)
14. [合并特性分支至主分支](#14-合并特性分支至主分支)
15. [分支管理](#15-分支管理)
16. [查看历史与日志](#16-查看历史与日志)
17. [撤销与修复错误](#17-撤销与修复错误)
18. [Stash (暂存修改)](#18-stash-暂存修改)
19. [克隆仓库](#19-克隆仓库)
20. [.gitignore 配置](#20-gitignore-配置)
21. [远程仓库管理](#21-远程仓库管理)
22. [标签管理 (版本控制)](#22-标签管理-版本控制)
23. [现代 Git 导航 (switch & restore)](#23-现代-git-导航-switch--restore)
24. [解决合并冲突](#24-解决合并冲突)
25. [Git Reflog – 找回丢失的代码](#25-git-reflog--找回丢失的代码)
26. [高级历史与代码行追踪](#26-高级历史与代码行追踪)
27. [Cherry-Pick 与交互式 Rebase](#27-cherry-pick-与交互式-rebase)
28. [清理未跟踪的文件](#28-清理未跟踪的文件)
29. [GitHub CLI (gh) 命令行工具](#29-github-cli-gh-命令行工具)
30. [Git 子模块](#30-git-子模块)
31. [Git 快捷别名 (Aliases)](#31-git-快捷别名-aliases)

---

## 1 Git 配置

| 命令 | 说明 (中文) |
|---------|-------------|
| `git config --global user.name "your-username"` | 设置全局 Git 用户名 |
| `git config --global user.email "abc@gmil.com"` | 设置全局 Git 邮箱地址 |
| `git config --list` | 查看所有 Git 配置 |

---

## 2 GitHub 个人访问令牌 (PAT)

| 步骤 | 说明 (中文) |
|------|-------------|
| **Settings → Developer settings → Personal access tokens** | 导航生成个人访问令牌 |
| 选择权限范围 | 选择 repo, notes, admin:org 权限 |
| 示例令牌 | `ghp_yourPersonalAccessTokenHere...` |

---

### 2.1 SSH 密钥身份验证设置

| 命令 | 说明 (中文) |
|---------|-------------|
| `ssh-keygen -t ed25519 -C "your_email@example.com"` | 生成安全的 SSH 密钥对 |
| `eval "$(ssh-agent -s)"` | 在终端中启动 SSH 代理 |
| `ssh-add ~/.ssh/id_ed25519` | 将私钥添加到 SSH 代理 |
| `cat ~/.ssh/id_ed25519.pub` | 显示公钥（复制并添加到 GitHub 设置中） |
| `ssh -T git@github.com` | 测试与 GitHub 的 SSH 连接 |
| `git remote set-url origin git@github.com:username/repo.git` | 将远程 URL 切换为 SSH |

---

## 3 连接本地仓库至远程

| 命令 | 说明 (中文) |
|---------|-------------|
| `git remote add origin https://github.com/Shariar-Ahamed/<repo>` | 添加 GitHub 远程仓库 |
| `git remote set-url origin https://<token>@github.com/Shariar-Ahamed/<repo>` | 使用 PAT 令牌连接 |

---

## 4 基础 Git 工作流

| 命令 | 说明 (中文) |
|---------|-------------|
| `git init` | 初始化本地 Git 仓库 |
| `git status` | 检查仓库状态 |
| `git add .` | 暂存所有更改 |
| `git commit -m "New Commit"` | 提交更改至本地仓库 |
| `git branch -M main` | 将默认分支重命名为 main |
| `git push -u origin main` | 推送更改至 GitHub |

---

## 5 一键推送项目更改

```bash
git add .
git commit -m "Update File"
git branch -M main
git push -u origin main
```

---

## 6 处理已删除的文件

> [!WARNING]
> **请谨慎使用强制推送 (`git push -f`)！** 这会覆盖远程历史记录。

| 命令 | 说明 (中文) |
|---------|-------------|
| `git add -A` | 暂存所有更改（包含文件删除） |
| `git commit -m "Updated file structure"` | 提交删除的文件 |
| `git push -f origin main` | 强制推送更改至 GitHub |

---

## 7 拉取最新代码 (Pull)

| 命令 | 说明 (中文) |
|---------|-------------|
| `git pull origin main` | 从远程 main 分支拉取最新代码 |
| `git pull origin main --rebase` | 保持干净历史记录的同时拉取代码 |
| `git push origin main` | 推送本地更改 |

---

## 8 同步至 GitHub 最新版本

| 命令 | 说明 (中文) |
|---------|-------------|
| `git fetch origin` | 获取远程最新数据 |
| `git reset --hard origin/main` | 强行将本地代码重置为与 GitHub 完全一致 |

---

## 9 在 Windows 中启用长路径支持

| 命令 | 说明 (中文) |
|---------|-------------|
| `git config --system core.longpaths true` | 启用 Windows 中的长文件路径支持 |

---

## 10 重命名文件夹与更新文件

| 命令 | 说明 (中文) |
|---------|-------------|
| `git add -A` | 暂存重命名与修改 |
| `git commit -m "Folder renamed and updated"` | 提交重命名更改 |
| `git push origin main` | 推送至 GitHub |

---

## 11 移除 .vscode 文件夹跟踪

| 命令 | 说明 (中文) |
|---------|-------------|
| `git rm -r --cached .vscode` | 从 Git 跟踪中移除 `.vscode` 文件夹 |
| `git commit -m "Remove .vscode folder"` | 提交移除 |
| `git push` | 更新至 GitHub |

---

## 12 重置 Git 仓库

| 命令 / Shell | 说明 (中文) |
|---------|-------------|
| `rm -rf .git` (Git Bash / Linux / Mac) | 删除 `.git` 文件夹（清除所有 Git 历史与跟踪） |
| `Remove-Item -Recurse -Force .git` (PowerShell) | 在 Windows PowerShell 中删除 `.git` 文件夹 |

---

## 13 特性分支推送工作流

| 命令 | 说明 (中文) |
|---------|-------------|
| `git pull origin main` | 获取主分支最新代码 |
| `git checkout -b feature-yourName` | 创建并切换至新特性分支 |
| `git add .` | 暂存所有更改 |
| `git commit -m "Your-commit"` | 保存更改 |
| `git push origin feature-yourName` | 将特性分支推送至 GitHub |

---

## 14 合并特性分支至主分支

| 命令 | 说明 (中文) |
|---------|-------------|
| `git checkout main` | 切换回主分支 |
| `git pull origin main` | 更新主分支 |
| `git merge origin/feature-yourName` | 合并特性分支至主分支 |
| `git push origin main` | 推送更新后的主分支 |

---

## 15 分支管理

| 命令 | 说明 (中文) |
|---------|-------------|
| `git branch` | 列出本地分支 |
| `git branch -a` | 列出本地与远程所有分支 |
| `git branch new-branch` | 创建新分支 |
| `git checkout new-branch` | 切换分支 |
| `git checkout -b new-branch` | 创建并切换分支 |
| `git merge new-branch` | 合并分支 |
| `git branch -d new-branch` | 安全删除本地分支 |
| `git branch -D new-branch` | 强制删除未合并的分支 |
| `git push origin --delete branch-name` | 删除 GitHub 上的远程分支 |

---

## 16 查看历史与日志

| 命令 | 说明 (中文) |
|---------|-------------|
| `git log` | 查看提交历史记录 |
| `git log --oneline` | 精简单行查看历史 |
| `git diff` | 查看未暂存的更改 |
| `git diff --staged` | 查看已暂存的更改 |
| `git show` | 查看最新提交的详细信息 |

---

## 17 撤销与修复错误

| 命令 | 说明 (中文) |
|---------|-------------|
| `git restore file.txt` | 恢复文件至上次提交的状态 |
| `git reset HEAD file.txt` | 取消暂存文件 |
| `git commit --amend` | 修改上次提交信息 |
| `git reset --soft HEAD~1` | 撤销提交但保留暂存区更改 |
| `git reset --hard HEAD~1` | 撤销上次提交并彻底丢弃所有更改 |
| `git revert <commit-hash>` | 创建反向提交以撤销之前的提交 |

---

## 18 Stash (暂存修改)

| 命令 | 说明 (中文) |
|---------|-------------|
| `git stash` | 临时保存未提交的修改 |
| `git stash pop` | 恢复并删除最新暂存 |
| `git stash list` | 查看所有暂存 |

---

## 19 克隆仓库

| 命令 | 说明 (中文) |
|---------|-------------|
| `git clone https://github.com/username/repo.git` | 从 GitHub 克隆仓库 |
| `git clone <repo-link> .` | 克隆至当前空目录 |

---

## 20 .gitignore 配置

| 模式 | 说明 (中文) |
|---------|-------------|
| 创建 `.gitignore` 文件 | 排除不需要跟踪的文件/文件夹 |
| `node_modules/` | 忽略 NPM 依赖包 |
| `.env` | 忽略密钥与环境变量 |

---

## 21 远程仓库管理

| 命令 | 说明 (中文) |
|---------|-------------|
| `git remote -v` | 查看远程仓库 URL |
| `git remote add origin <url>` | 添加远程仓库 |
| `git remote set-url origin <new-url>` | 修改远程仓库 URL |

---

## 22 标签管理 (版本控制)

| 命令 | 说明 (中文) |
|---------|-------------|
| `git tag v1.0` | 创建轻量级版本标签 |
| `git push origin v1.0` | 将标签推送至 GitHub |

---

## 23 现代 Git 导航 (switch & restore)

| 命令 | 说明 (中文) |
|---------|-------------|
| `git switch <branch-name>` | 切换分支 |
| `git restore <file>` | 恢复工作区文件 |

---

## 24 解决合并冲突

| 命令 | 说明 (中文) |
|---------|-------------|
| `git status` | 查看冲突文件 |
| 手动编辑文件 | 保留 `<<<<<<<` 与 `>>>>>>>` 之间所需代码 |
| `git add <resolved-file>` | 标记冲突已解决 |
| `git merge --abort` | 中止卡住的合并 |

---

## 25 Git Reflog – 找回丢失的代码

| 命令 | 说明 (中文) |
|---------|-------------|
| `git reflog` | 查看所有 HEAD 操作的日志 |
| `git reset --hard HEAD@{n}` | 恢复至第 n 条日志记录的状态 |

---

## 26 高级历史与代码行追踪

| 命令 | 说明 (中文) |
|---------|-------------|
| `git log --graph --oneline --all` | 图形化显示分支树 |
| `git blame <file>` | 逐行查看每一行代码是谁在何时修改的 |

---

## 27 Cherry-Pick 与交互式 Rebase

| 命令 | 说明 (中文) |
|---------|-------------|
| `git cherry-pick <commit-hash>` | 应用其他分支的特定提交 |

---

## 28 清理未跟踪的文件

| 命令 | 说明 (中文) |
|---------|-------------|
| `git clean -fd` | 强制清理未跟踪的文件和文件夹 |

---

## 29 GitHub CLI (gh) 命令行工具

| 命令 | 说明 (中文) |
|---------|-------------|
| `gh auth login` | 在终端中登录 GitHub |
| `gh pr create` | 创建 Pull Request |

---

## 30 Git 子模块

| 命令 | 说明 (中文) |
|---------|-------------|
| `git submodule add <repo-url> <path>` | 添加子模块 |

---

## 31 Git 快捷别名 (Aliases)

| 命令 | 说明 (中文) |
|---------|-------------|
| `git config --global alias.st status` | 创建 `git st` 快捷命令 |

---

## 🚀 专家建议 (Pro Tips)

- **开始新工作前务必运行 `git pull`**。
- **如果不慎丢失代码，请使用 `git reflog`**！
