<h2 align="center">GitHub Setup & Main Code – Complete Master Commands & Explanations</h2>

<p align="center">
This document is an <b>all-in-one comprehensive Git & GitHub command reference guide</b> for connecting local projects, pushing updates, managing branches, resolving conflicts, and mastering workflow operations.
</p>

<div align="center">

### 🌐 Select Language / ভাষা পরিবর্তন করুন / Seleccionar idioma:
[**🇺🇸 English**](README.md) &nbsp;|&nbsp; [**🇧🇩 বাংলা (Bangla)**](languages/README.bn.md) &nbsp;|&nbsp; [**🇪🇸 Español (Spanish)**](languages/README.es.md)

</div>

---

## 📌 Table of Contents

1. [Git Configuration](#1-git-configuration)
2. [GitHub Personal Access Token (PAT)](#2-github-personal-access-token-pat)  
   2.1 [SSH Key Authentication Setup](#21-ssh-key-authentication-setup)
3. [Connect Local Repository to Remote](#3-connect-local-repository-to-remote)
4. [Basic Git Workflow](#4-basic-git-workflow)
5. [Push Project Changes Just One Click](#5-push-project-changes-just-one-click)
6. [Handling Deleted Files](#6-handling-deleted-files)
7. [Repo and README.md Updates version clone](#7-repo-and-readmemd-updates-version-clone)
8. [Sync Latest GitHub Version](#8-sync-latest-github-version)
9. [Enable Long Paths in Git](#9-enable-long-paths-in-git)
10. [Folder Rename & File Updates](#10-folder-rename--file-updates)
11. [.vscode Folder Remove](#11-vscode-folder-remove)
12. [Reset Git Repository](#12-reset-git-repository)
13. [Feature Branch Push Workflow](#13-feature-branch-push-workflow)
14. [Feature Branch Merge Workflow](#14-feature-branch-merge-workflow)
15. [Branch Management](#15-branch-management)
16. [Checking History & Logs](#16-checking-history--logs)
17. [Undo & Fix Mistakes](#17-undo--fix-mistakes)
18. [Stash (Temporary Save)](#18-stash-temporary-save)
19. [Clone Repository](#19-clone-repository)
20. [.gitignore Setup](#20-gitignore-setup)
21. [Remote Management](#21-remote-management)
22. [Tagging (Version Control)](#22-tagging-version-control)
23. [Modern Git Navigation & Restoration](#23-modern-git-navigation--restoration)
24. [Handling Merge Conflicts](#24-handling-merge-conflicts)
25. [Git Reflog – Recover Lost Commits](#25-git-reflog--recover-lost-commits)
26. [Advanced History & Line Tracking](#26-advanced-history--line-tracking)
27. [Cherry-Pick & Interactive Rebase](#27-cherry-pick--interactive-rebase)
28. [Cleaning Untracked Files](#28-cleaning-untracked-files)
29. [GitHub CLI (gh) Commands](#29-github-cli-gh-commands)
30. [Git Submodules](#30-git-submodules)
31. [Git Aliases & Shortcuts](#31-git-aliases--shortcuts)

---

## 1 Git Configuration

| Command | Explanation |
|---------|-------------|
| `git config --global user.name "your-username"` | Set global Git username |
| `git config --global user.email "abc@gmil.com"` | Set global Git email |
| `git config --list` | View all Git configuration |

---

## 2 GitHub Personal Access Token (PAT)

| Step | Explanation |
|------|-------------|
| Go to **Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token (classic)**  | Navigate to generate a token |
| Generate a new token (classic) | Select scopes for general use: repo, notes, admin:org, admin:public_key |
| Example token | `ghp_yourPersonalAccessTokenHere...` |

---

### 2.1 SSH Key Authentication Setup

| Command | Explanation |
|---------|-------------|
| `ssh-keygen -t ed25519 -C "your_email@example.com"` | Generate a secure SSH key pair |
| `eval "$(ssh-agent -s)"` | Start the SSH agent in terminal |
| `ssh-add ~/.ssh/id_ed25519` | Add private SSH key to ssh-agent |
| `cat ~/.ssh/id_ed25519.pub` | Display public key (Copy and paste to GitHub Settings → SSH and GPG keys) |
| `ssh -T git@github.com` | Test connection to GitHub via SSH |
| `git remote set-url origin git@github.com:username/repo.git` | Switch existing remote URL from HTTPS to SSH |

---

## 3 Connect Local Repository to Remote

| Command | Explanation |
|---------|-------------|
| `git remote add origin https://github.com/Shariar-Ahamed/<repo>` | Add GitHub repo as remote |
| `git remote set-url origin https://<token>@github.com/Shariar-Ahamed/<repo>` | Connect using PAT for authentication |

---

## 4 Basic Git Workflow

| Command | Explanation |
|---------|-------------|
| `git init` | Initialize local repository |
| `git status` | Check repository status |
| `git add .` | Stage all changes |
| `git commit -m "New Commit"` | Commit changes to local repository |
| `git branch -M main` | Rename default branch to main |
| `git push -u origin main` | Push changes to GitHub |

---

## 5 Push Project Changes Just One Click

```bash
git add .
git commit -m "Update File"
git branch -M main
git push -u origin main
``` 
*Explanation: Stage all project changes, commit with descriptive message, ensure main branch is active, push commit to GitHub.*

---

## 6 Handling Deleted Files

> [!WARNING]
> **Use Force Push (`git push -f`) with extreme caution!** It overwrites remote repository history and can overwrite teammates' work if used on a shared branch.

| Command | Explanation |
|---------|-------------|
| `git add -A` | Stage all changes including deletions |
| `git commit -m "Updated file structure and removed old files"` | Commit updates with deletion |
| `git push -f origin main` | Force push changes to GitHub |

---

## 7 Repo and README.md Updates version clone

| Command                         | Explanation                                |
| ------------------------------- | ------------------------------------------ |
| `git pull origin main`          | Pull latest code from remote `main` branch |
| `git pull`                      | Update local repo from tracked branch      |
| `git pull origin main --rebase` | Pull and keep commit history clean         |
| `git push origin main`          | Push local changes to remote repo          |

---

## 8 Sync Latest GitHub Version

| Command | Explanation |
|---------|-------------|
| `git fetch origin` | Fetch latest commits from remote |
| `git reset --hard origin/main` | Sync local repository to match GitHub exactly |

---

## 9 Enable Long Paths in Git

| Command | Explanation |
|---------|-------------|
| `git config --system core.longpaths true` | Enable support for long file paths in Windows Git |

---

## 10 Folder Rename & File Updates

| Command | Explanation |
|---------|-------------|
| Rename folder in VS Code & add 2 new `.js` files, delete old `.txt` file | Manual project changes |
| `git add -A` | Stage all changes including renames and deletions |
| `git commit -m "Folder renamed, new files added, old files deleted"` | Commit updates |
| `git push origin main` | Push all changes to GitHub |

---

## 11 .vscode Folder Remove

| Command | Explanation |
|---------|-------------|
| `git rm -r --cached .vscode` | Select `.vscode` for remove |
| `git commit -m "Remove .vscode folder"` | Commit updates |
| `git push` | Push all changes to GitHub |

---

## 12 Reset Git Repository

| Command / Shell | Explanation |
|---------|-------------|
| `rm -rf .git` (Git Bash / Linux / Mac) | Delete `.git` folder (removes Git history, remote, all tracking) |
| `Remove-Item -Recurse -Force .git` (PowerShell) | Delete `.git` folder in Windows PowerShell |

---

## 13 Feature Branch Push Workflow

| Command                            | Explanation                                |
| ---------------------------------- | ------------------------------------------ |
| `git pull origin main`             | Get latest updates from GitHub main branch |
| `git checkout -b feature-yourName` | Create and switch to a new feature branch  |
| `git add .`                        | Stage all changes                          |
| `git commit -m "Your-commit"`      | Save changes with a message                |
| `git push origin feature-yourName` | Upload active feature branch to GitHub     |

---

## 14 Feature Branch Merge Workflow

| Command | Explanation |
|---------|-------------|
| `git checkout main` | Switch to main branch |
| `git pull origin main` | Get latest updates from GitHub main branch |
| `git fetch origin` | Fetch all latest branches and updates from remote |
| `git merge origin/feature-yourName` | Merge feature branch into main |
| `git push origin main` | Upload updated main branch to GitHub |

---

## 15 Branch Management

| Command | Explanation |
|---------|-------------|
| `git branch` | List all local branches |
| `git branch -a` | List all local & remote branches |
| `git branch new-branch` | Create a new branch |
| `git checkout new-branch` | Switch to another branch |
| `git checkout -b new-branch` | Create & switch to new branch |
| `git merge new-branch` | Merge branch into current branch |
| `git branch -d new-branch` | Delete a local branch (safe) |
| `git branch -D new-branch` | Force delete an unmerged local branch |
| `git push origin --delete branch-name` | Delete a remote branch on GitHub |

---

## 16 Checking History & Logs

| Command | Explanation |
|---------|-------------|
| `git log` | View commit history |
| `git log --oneline` | Short commit history |
| `git diff` | Show unstaged changes |
| `git diff --staged` | Show staged changes ready to be committed |
| `git show` | Show details of the latest commit |
| `git show <commit-hash>` | Show details of a specific commit |

---

## 17 Undo & Fix Mistakes

| Command | Explanation |
|---------|-------------|
| `git restore file.txt` | Restore file to last committed state |
| `git reset HEAD file.txt` | Unstage a file |
| `git commit --amend` | Edit last commit message |
| `git reset --soft HEAD~1` | Undo last commit but keep changes staged |
| `git reset --mixed HEAD~1` | Undo last commit and unstage changes |
| `git reset --hard HEAD~1` | Undo last commit and completely discard changes |
| `git revert <commit-hash>` | Create a new commit that reverts previous commit |

---

## 18 Stash (Temporary Save)

| Command | Explanation |
|---------|-------------|
| `git stash` | Save current uncommitted changes temporarily |
| `git stash save "message"` | Save stash with a descriptive name |
| `git stash pop` | Restore and remove the latest saved stash |
| `git stash apply` | Apply the latest stash without deleting it |
| `git stash list` | Show all saved stashes |
| `git stash drop` | Delete the latest stash |
| `git stash clear` | Delete all saved stashes |

---

## 19 Clone Repository

| Command | Explanation |
|---------|-------------|
| `git clone https://github.com/username/repo.git` | Clone repository from GitHub into a new folder |
| `git clone <repo-link> .` | Clone repository into current empty folder |
| `git clone -b <branch-name> <repo-link>` | Clone a specific branch directly |

---

## 20 .gitignore Setup

| Step / Pattern | Explanation |
|---------|-------------|
| Create `.gitignore` file | File used to exclude files/folders from Git tracking |
| `.vscode/` | Ignore VS Code settings folder |
| `node_modules/` | Ignore NPM dependencies folder |
| `.env` | Ignore environment variables & API keys |
| `*.log` | Ignore all log files |
| `dist/` or `build/` | Ignore build output directories |

---

## 21 Remote Management

| Command | Explanation |
|---------|-------------|
| `git remote -v` | Show remote repository URLs (fetch & push) |
| `git remote add origin <url>` | Add new remote connection |
| `git remote remove origin` | Remove current remote connection |
| `git remote rename origin new-origin` | Rename remote repository reference |
| `git remote set-url origin <new-url>` | Update URL of existing remote repository |

---

## 22 Tagging (Version Control)

| Command | Explanation |
|---------|-------------|
| `git tag v1.0` | Create a lightweight version tag |
| `git tag -a v1.0 -m "Release v1.0"` | Create an annotated version tag with a message |
| `git tag` | List all tags |
| `git push origin v1.0` | Push specific tag to GitHub |
| `git push origin --tags` | Push all local tags to GitHub |
| `git tag -d v1.0` | Delete a local tag |
| `git push origin --delete v1.0` | Delete a remote tag on GitHub |

---

## 23 Modern Git Navigation & Restoration

| Command | Explanation |
|---------|-------------|
| `git switch <branch-name>` | Switch to an existing branch |
| `git switch -c <new-branch>` | Create and switch to a new branch |
| `git switch -` | Switch back to the previous branch |
| `git restore <file>` | Discard changes in working directory |
| `git restore --staged <file>` | Unstage a staged file |

---

## 24 Handling Merge Conflicts

| Step / Command | Explanation |
|---------|-------------|
| `git status` | View list of unmerged files with conflicts |
| Edit conflict files manually | Look for `<<<<<<<`, `=======`, `>>>>>>>` markers, keep desired code |
| `git add <resolved-file>` | Mark conflict as resolved |
| `git commit -m "Resolved merge conflict"` | Complete the merge process |
| `git merge --abort` | Abort a stuck merge and return to pre-merge state |
| `git rebase --abort` | Abort a stuck rebase operation |

---

## 25 Git Reflog – Recover Lost Commits

| Command | Explanation |
|---------|-------------|
| `git reflog` | View safety log of all recent actions with commit hashes |
| `git checkout HEAD@{n}` | Inspect state at reflog entry `n` |
| `git reset --hard HEAD@{n}` | Restore repository to exact state at reflog entry `n` |
| `git branch <recovered-branch> <commit-hash>` | Recreate a deleted branch from reflog hash |

---

## 26 Advanced History & Line Tracking

| Command | Explanation |
|---------|-------------|
| `git log --graph --oneline --all` | Show visual ASCII tree representation of all branches |
| `git log -n 5` | Show only the last 5 commits |
| `git log --author="Name"` | Filter commits by author |
| `git log -p <file>` | Show detailed diff history for a specific file |
| `git blame <file>` | Show line-by-line breakdown of who modified each line and when |

---

## 27 Cherry-Pick & Interactive Rebase

| Command | Explanation |
|---------|-------------|
| `git cherry-pick <commit-hash>` | Apply a specific commit from another branch into current branch |
| `git rebase main` | Rebase current feature branch onto main branch |
| `git rebase -i HEAD~3` | Open interactive editor to squash, reword, drop, or edit last 3 commits |

---

## 28 Cleaning Untracked Files

| Command | Explanation |
|---------|-------------|
| `git clean -n` | Dry run – preview untracked files that will be deleted |
| `git clean -f` | Force delete untracked files |
| `git clean -fd` | Force delete untracked files and directories |
| `git clean -fx` | Force delete all untracked files including ignored files |

---

## 29 GitHub CLI (gh) Commands

| Command | Explanation |
|---------|-------------|
| `gh auth login` | Authenticate terminal with GitHub account |
| `gh repo create <name> --public` | Create a new GitHub repository from terminal |
| `gh repo clone <owner/repo>` | Clone repository using GitHub CLI |
| `gh pr create --title "Title" --body "Details"` | Create a Pull Request on GitHub |
| `gh pr list` | List open Pull Requests |
| `gh pr merge <pr-number>` | Merge a Pull Request directly from CLI |
| `gh issue create --title "Bug title"` | Create a GitHub Issue |
| `gh release create v1.0` | Create an official GitHub release with assets |

---

## 30 Git Submodules

| Command | Explanation |
|---------|-------------|
| `git submodule add <repo-url> <path>` | Add another git repo as a submodule inside project |
| `git submodule update --init --recursive` | Initialize and clone all submodules after cloning main repo |
| `git submodule update --remote` | Update submodules to their latest remote commits |

---

## 31 Git Aliases & Shortcuts

| Command | Explanation |
|---------|-------------|
| `git config --global alias.st status` | Shortcut: Type `git st` for `git status` |
| `git config --global alias.co checkout` | Shortcut: Type `git co` for `git checkout` |
| `git config --global alias.br branch` | Shortcut: Type `git br` for `git branch` |
| `git config --global alias.ci commit` | Shortcut: Type `git ci` for `git commit` |
| `git config --global alias.lg "log --graph --oneline --all"` | Shortcut: Type `git lg` for pretty branch graph |

---

## 🚀 Pro Tips

- **Always run `git pull`** before starting new work to prevent merge conflicts.
- **Write descriptive commit messages** (e.g., `fix: solve navbar toggle bug` instead of `fixed`).
- **Always maintain `.gitignore`** to avoid committing sensitive keys (`.env`), `.vscode`, or heavy folders (`node_modules`).
- **Use feature branches** (`feature/header`, `bugfix/login`) for new work rather than committing directly to `main`.
- **Use `git reflog`** if you think you lost code—Git rarely deletes committed data!
- **Use GitHub CLI (`gh`)** for super fast PR creation and repo management directly from terminal.

---

## 📝 Short Description

This document contains **the ultimate master guide for Git setup, commands, workflows, GitHub CLI tools, and troubleshooting**.  
It is designed for **quick reference, daily productivity, team collaboration, and complete repository management**, making it invaluable for beginners and seasoned developers alike.
