<h2 align="center">GitHub Setup & Main Code – Complete Master Commands & Explanations</h2>

<p align="center">
This document is an <b>all-in-one comprehensive Git & GitHub command reference guide</b> for connecting local projects, pushing updates, managing branches, resolving conflicts, and mastering workflow operations.
</p>

<div align="center">

### 🌐 Select Page Language / ভাষা নির্বাচন করুন / Seleccionar idioma:
[**🇺🇸 English Version**](#-english-version) &nbsp;|&nbsp; [**🇧🇩 বাংলা সংস্করণ**](#-বাংলা-সংস্করণ) &nbsp;|&nbsp; [**🇪🇸 Versión en Español**](#-versión-en-español)

</div>

---

# 🇺🇸 English Version

<p align="right"><a href="#top">⬆ Back to Language Selection</a></p>

## 📌 Table of Contents (English)

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

<br/>
<hr/>
<br/>

# 🇧🇩 বাংলা সংস্করণ

<p align="right"><a href="#top">⬆ উপরে ভাষা নির্বাচনে ফিরে যান</a></p>

## 📌 সূচিপত্র (বাংলা)

1. [গিট কনফিগারেশন](#1-গিট-কনফিগারেশন)
2. [গিটহাব পার্সোনাল অ্যাক্সেস টোকেন (PAT)](#2-গিটহাব-পার্সোনাল-অ্যাক্সেস-টোকেন-pat)  
   2.1 [SSH Key অথেন্টিকেশন সেটআপ](#21-ssh-key-অথেন্টিকেশন-সেটআপ)
3. [লোকাল প্রজেক্টের সাথে রিমোট গিটহাব যুক্ত করা](#3-লোকাল-প্রজেক্টের-সাথে-রিমোট-গিটহাব-যুক্ত-করা)
4. [প্রাথমিক গিট ওয়ার্কফ্লো](#4-প্রাথমিক-গিট-ওয়ার্কফ্লো)
5. [এক ক্লিকে প্রজেক্ট পরিবর্তন গিটহাবে পাঠানো](#5-এক-ক্লিকে-প্রজেক্ট-পরিবর্তন-গিটহাবে-পাঠানো)
6. [মুছে ফেলা ফাইল সামলানো](#6-মুছে-ফেলা-ফাইল-সামলানো)
7. [রিপোজিটরির সর্বশেষ ভার্সন পুল করা](#7-রিপোজিটরির-সর্বশেষ-ভার্সন-পুল-করা)
8. [লোকাল কোড হুবহু গিটহাবের সাথে মিলাানো](#8-লোকাল-কোড-হুবহু-গিটহাবের-সাথে-মিলাানো)
9. [উইন্ডোজে লং ফাইল পাথ চালু করা](#9-উইন্ডোজে-লং-ফাইল-পাথ-চালু-করা)
10. [ফোল্ডার রিনেম ও ফাইল আপডেট করা](#10-ফোল্ডার-রিনেম-ও-ফাইল-আপডেট-করা)
11. [.vscode ফোল্ডার ট্র্যাকিং থেকে সরানো](#11-vscode-ফোল্ডার-ট্র্যাকিং-থেকে-সরানো)
12. [গিট রিপোজিটরি সম্পূর্ণ রিসেট করা](#12-গিট-রিপোজিটরি-সম্পূর্ণ-রিসেট-করা)
13. [ফিচার ব্রাঞ্চ পুশ করার নিয়ম](#13-ফিচার-ব্রাঞ্চ-পুশ-করার-নিয়ম)
14. [ফিচার ব্রাঞ্চ মেইন ব্রাঞ্চে মার্জ করা](#14-ফিচার-ব্রাঞ্চ-মেইন-ব্রাঞ্চে-মার্জ-করা)
15. [ব্রাঞ্চ পরিচালনা ও ম্যানেজমেন্ট](#15-ব্রাঞ্চ-পরিচালনা-ও-ম্যানেজমেন্ট)
16. [কোডের ইতিহাস ও লগ দেখা](#16-কোডের-ইতিহাস-ও-লগ-দেখা)
17. [ভুল শুধরানো ও কোড আগের অবস্থায় আনা](#17-ভুল-শুধরানো-ও-কোড-আগের-অবস্থায়-আনা)
18. [স্ট্যাশ - সাময়িকভাবে কোড সেভ রাখা](#18-স্ট্যাশ---সাময়িকভাবে-কোড-সেভ-রাখা)
19. [রিপোজিটরি ক্লোন করা](#19-রিপোজিটরি-ক্লোন-করা)
20. [.gitignore সেটআপ ও ব্যবহার](#20-gitignore-সেটআপ-ও-ব্যবহার)
21. [রিমোট ইউআরএল পরিচালনা](#21-রিমোট-ইউআরএল-পরিচালনা)
22. [ভার্সন ট্যাগিং (Software Release Tag)](#22-ভার্সন-ট্যাগিং-software-release-tag)
23. [আধুনিক গিট নেভিগেশন (git switch & restore)](#23-আধুনিক-গিট-নেভিগেশন-git-switch--restore)
24. [মার্জ কনফ্লিক্ট সমাধান করা](#24-মার্জ-কনফ্লিক্ট-সমাধান-করা)
25. [গিট রিফ্লগ - হারিয়ে যাওয়া কোড উদ্ধার করা](#25-গিট-রিফ্লগ---হারিয়ে-যাওয়া-কোড-উদ্ধার-করা)
26. [অ্যাডভান্সড লগ ও কার কোন লাইন তা দেখা](#26-অ্যাডভান্সড-লগ-ও-কার-কোন-লাইন-তা-দেখা)
27. [চেরি-পিক ও ইন্টারেক্টিভ রিবেস](#27-চেরি-পিক-ও-ইন্টারেক্টিভ-রিবেস)
28. [অপ্রয়োজনীয় ফাইল পরিষ্কার করা (git clean)](#28-অপ্রয়োজনীয়-ফাইল-পরিষ্কার-করা-git-clean)
29. [GitHub CLI (gh) দিয়ে টার্মিনাল কমান্ড](#29-github-cli-gh-দিয়ে-টার্মিনাল-কমান্ড)
30. [গিট সাবমডিউল ব্যবহার](#30-গিট-সাবমডিউল-ব্যবহার)
31. [গিট শর্টকাট (Aliases) তৈরি](#31-গিট-শর্টকাট-aliases-তৈরি)

---

## 1 গিট কনফিগারেশন

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git config --global user.name "your-username"` | গ্লোবাল গিট ইউজারনেম সেট করা |
| `git config --global user.email "abc@gmil.com"` | গ্লোবাল গিট ইমেইল অ্যাড্রেস সেট করা |
| `git config --list` | বর্তমান সকল গিট কনফিগারেশন তালিকা দেখা |

---

## 2 গিটহাব পার্সোনাল অ্যাক্সেস টোকেন (PAT)

| ধাপ | বাংলা ব্যাখ্যা |
|------|-------------|
| **Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token** | গিটহাবে পাসওয়ার্ডের বদলে ব্যবহারের জন্য টোকেন তৈরি করা |
| টোকেন স্কোপ সিলেক্ট করুন | সাধারণ কাজের জন্য repo, notes, admin:org অপশন টিক দিন |
| উদাহরণ টোকেন | `ghp_yourPersonalAccessTokenHere...` |

---

### 2.1 SSH Key অথেন্টিকেশন সেটআপ

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `ssh-keygen -t ed25519 -C "your_email@example.com"` | একটি নিরাপদ SSH Key পেয়ার তৈরি করা |
| `eval "$(ssh-agent -s)"` | টার্মিনালে SSH Agent ব্যাকগ্রাউন্ডে চালু করা |
| `ssh-add ~/.ssh/id_ed25519` | প্রাইভেট SSH Key টি এজেন্ট-এ যুক্ত করা |
| `cat ~/.ssh/id_ed25519.pub` | পাব্লিক কী প্রিন্ট করা (যা কপি করে GitHub Settings এ বসাতে হবে) |
| `ssh -T git@github.com` | গিটহাবের সাথে SSH সংযোগ সফল হয়েছে কিনা পরীক্ষা করা |
| `git remote set-url origin git@github.com:username/repo.git` | প্রজেক্টের ইউআরএল HTTPS থেকে SSH এ পরিবর্তন করা |

---

## 3 লোকাল প্রজেক্টের সাথে রিমোট গিটহাব যুক্ত করা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git remote add origin https://github.com/Shariar-Ahamed/<repo>` | গিটহাব রিপোজিটরিকে লোকাল প্রজেক্টের সাথে লিংক করা |
| `git remote set-url origin https://<token>@github.com/Shariar-Ahamed/<repo>` | PAT টোকেন সহ অটো অথেন্টিকেশন ইউআরএল সেট করা |

---

## 4 প্রাথমিক গিট ওয়ার্কফ্লো

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git init` | লোকাল ফোল্ডারে নতুন গিট রিপোজিটরি শুরু করা |
| `git status` | ফাইলের বর্তমান অবস্থা বা পরিবর্তন চেক করা |
| `git add .` | সমস্ত পরিবর্তিত ফাইল স্টেজিং এরিয়ায় যুক্ত করা |
| `git commit -m "New Commit"` | পরিবর্তনের বিবরণ লিখে সেভ বা কমিট করা |
| `git branch -M main` | ডিফল্ট ব্রাঞ্চের নাম পরিবর্তন করে main রাখা |
| `git push -u origin main` | লোকাল কোড গিটহাবে আপলোড/পুশ করা |

---

## 5 এক ক্লিকে প্রজেক্ট পরিবর্তন গিটহাবে পাঠানো

```bash
git add .
git commit -m "Update File"
git branch -M main
git push -u origin main
``` 
*বাংলা ব্যাখ্যা: সমস্ত ফাইল স্টেজ করুন, সুন্দর কমিট মেসেজ দিন, মেইন ব্রাঞ্চ নিশ্চিত করে গিটহাবে পুশ করে দিন।*

---

## 6 মুছে ফেলা ফাইল সামলানো

> [!WARNING]
> **ফোর্স পুশ (`git push -f`) খুব সাবধানে ব্যবহার করুন!** এটি রিমোটের পূর্বের ইতিহাস মুছে ফেলে এবং সহকর্মীদের কাজের ক্ষতি করতে পারে।

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git add -A` | ফাইল ডিলিট বা রিনেম সহ সমস্ত পরিবর্তন একসাথে স্টেজ করা |
| `git commit -m "Updated file structure and removed old files"` | ডিলিট করা ফাইলসহ নতুন কমিট তৈরি করা |
| `git push -f origin main` | জোরপূর্বক (Force Push) গিটহাবে কোড আপডেট করা |

---

## 7 রিপোজিটরির সর্বশেষ ভার্সন পুল করা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git pull origin main` | গিটহাবের main ব্রাঞ্চ থেকে সর্বশেষ কোড নামিয়ে আনা |
| `git pull` | কারেন্ট ট্র্যাক করা ব্রাঞ্চের আপডেট নামানো |
| `git pull origin main --rebase` | কমিট হিস্ট্রি পরিষ্কার রেখে সর্বশেষ কোড পুল করা |
| `git push origin main` | লোকাল কাজ গিটহাবে আপলোড করা |

---

## 8 লোকাল কোড হুবহু গিটহাবের সাথে মিলাানো

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git fetch origin` | রিমোটের সমস্ত সর্বশেষ ব্রাঞ্চ ও কমিট ডাটা আনা |
| `git reset --hard origin/main` | লোকাল সমস্ত পরিবর্তন ফেলে দিয়ে হুবহু গিটহাবের সাথে মিলিয়ে ফেলা |

---

## 9 উইন্ডোজে লং ফাইল পাথ চালু করা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git config --system core.longpaths true` | উইন্ডোজে দীর্ঘ ফোল্ডার পাথের গিট সমস্যা দূর করা |

---

## 10 ফোল্ডার রিনেম ও ফাইল আপডেট করা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| VS Code এ ফোল্ডার রিনেম ও নতুন ফাইল তৈরি | ম্যানুয়াল প্রজেক্ট পরিবর্তন |
| `git add -A` | ফাইল রিনেম ও নতুন ফাইলসহ সব স্টেজ করা |
| `git commit -m "Folder renamed and updated"` | নাম পরিবর্তন কমিট করা |
| `git push origin main` | গিটহাবে পরিবর্তন পাঠানো |

---

## 11 .vscode ফোল্ডার ট্র্যাকিং থেকে সরানো

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git rm -r --cached .vscode` | `.vscode` ফোল্ডারকে গিট ট্র্যাকিং থেকে বাদ দেওয়া |
| `git commit -m "Remove .vscode folder"` | বাদ দেওয়ার বিষয়টি কমিট করা |
| `git push` | পরিবর্তন গিটহাবে আপডেট করা |

---

## 12 গিট রিপোজিটরি সম্পূর্ণ রিসেট করা

| কমান্ড / শেল | বাংলা ব্যাখ্যা |
|---------|-------------|
| `rm -rf .git` (Git Bash / Linux / Mac) | প্রজেক্টের সমস্ত গিট হিস্ট্রি ও ট্র্যাকিং সম্পূর্ণ মুছে ফেলা |
| `Remove-Item -Recurse -Force .git` (PowerShell) | উইন্ডোজ পাওয়ারশেলে গিট ফোল্ডার মুছে ফেলা |

---

## 13 ফিচার ব্রাঞ্চ পুশ করার নিয়ম

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git pull origin main` | মেইন ব্রাঞ্চ থেকে লেটেস্ট আপডেট নেওয়া |
| `git checkout -b feature-yourName` | নতুন ব্রাঞ্চ তৈরি করে সেখানে সুইচ করা |
| `git add .` | সব কোড স্টেজ করা |
| `git commit -m "Your-commit"` | কাজের সুন্দর মেসেজ দিয়ে সেভ করা |
| `git push origin feature-yourName` | তৈরি করা নতুন ব্রাঞ্চটি গিটহাবে আপলোড করা |

---

## 14 ফিচার ব্রাঞ্চ মেইন ব্রাঞ্চে মার্জ করা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git checkout main` | মেইন ব্রাঞ্চে ফিরে আসা |
| `git pull origin main` | গিটহাব মেইন ব্রাঞ্চের লেটেস্ট কোড নামানো |
| `git fetch origin` | রিমোটের সব আপডেট রিলোড করা |
| `git merge origin/feature-yourName` | বন্ধুর ফিচার ব্রাঞ্চটিকে মেইন ব্রাঞ্চে যুক্ত (Merge) করা |
| `git push origin main` | মার্জ করা নতুন মেইন ব্রাঞ্চ গিটহাবে পুশ করা |

---

## 15 ব্রাঞ্চ পরিচালনা ও ম্যানেজমেন্ট

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git branch` | লোকাল সমস্ত ব্রাঞ্চের নাম দেখা |
| `git branch -a` | লোকাল ও গিটহাবের রিমোট সমস্ত ব্রাঞ্চ দেখা |
| `git branch new-branch` | নতুন একটি ব্রাঞ্চ তৈরি করা |
| `git checkout new-branch` | অন্য ব্রাঞ্চে চলে যাওয়া |
| `git checkout -b new-branch` | এক কমান্ডে ব্রাঞ্চ তৈরি ও সুইচ করা |
| `git merge new-branch` | বর্তমান ব্রাঞ্চে অন্য ব্রাঞ্চ মার্জ করা |
| `git branch -d new-branch` | লোকাল ব্রাঞ্চ নিরাপদে ডিলিট করা |
| `git branch -D new-branch` | আন-মার্জড ব্রাঞ্চ জোরপূর্বক ডিলিট করা |
| `git push origin --delete branch-name` | গিটহাব থেকে রিমোট ব্রাঞ্চ ডিলিট করা |

---

## 16 কোডের ইতিহাস ও লগ দেখা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git log` | আগের করা সমস্ত কমিট হিস্ট্রি দেখা |
| `git log --oneline` | এক লাইনে সংক্ষেপে হিস্ট্রি দেখা |
| `git diff` | আন-স্টেজড কোডের পরিবর্তন দেখা |
| `git diff --staged` | স্টেজিং এরিয়ায় থাকা সেভ করার জন্য প্রস্তুত কোডের পার্থক্য দেখা |
| `git show` | একদম শেষ কমিটে কি কি পরিবর্তন হয়েছিল দেখা |
| `git show <commit-hash>` | নির্দিষ্ট কোনো কমিটের বিস্তারিত পরিবর্তন দেখা |

---

## 17 ভুল শুধরানো ও কোড আগের অবস্থায় আনা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git restore file.txt` | ফাইলকে শেষ সেভ করা অবস্থায় ফিরিয়ে আনা |
| `git reset HEAD file.txt` | ফাইলকে স্টেজিং এলাকা থেকে বের করা |
| `git commit --amend` | শেষ কমিটের ভুল মেসেজ বা মিস যাওয়া ফাইল ঠিক করা |
| `git reset --soft HEAD~1` | শেষ কমিট বাতিল করা কিন্তু কোড স্টেজড রাখা |
| `git reset --mixed HEAD~1` | শেষ কমিট বাতিল করা ও ফাইল আন-স্টেজ করা |
| `git reset --hard HEAD~1` | শেষ কমিটসহ সমস্ত কোড পরিবর্তন একবারে মুছে ফেলা |
| `git revert <commit-hash>` | আগের কমিটের বিপরীত নতুন কমিট তৈরি করে ইতিহাস বজায় রাখা |

---

## 18 স্ট্যাশ - সাময়িকভাবে কোড সেভ রাখা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git stash` | বর্তমান কাজ শেষ না করেই সাময়িকভাবে লুকিয়ে রাখা |
| `git stash save "message"` | সুন্দর নাম দিয়ে স্ট্যাশ সেভ করা |
| `git stash pop` | লুকিয়ে রাখা শেষ কাজ ফিরিয়ে এনে স্ট্যাশ ডিলিট করা |
| `git stash apply` | স্ট্যাশ না মুছে লুকানো কোড প্রয়োগ করা |
| `git stash list` | সেভ করা সমস্ত স্ট্যাশের তালিকা দেখা |
| `git stash drop` | সেভ করা নির্দিষ্ট স্ট্যাশ মুছে ফেলা |
| `git stash clear` | সব স্ট্যাশ একসাথে সাফ করা |

---

## 19 রিপোজিটরি ক্লোন করা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git clone https://github.com/username/repo.git` | গিটহাব থেকে সম্পূর্ণ প্রজেক্টের কপি কম্পিউটারে নামানো |
| `git clone <repo-link> .` | বর্তমান খালি ফোল্ডারে প্রজেক্ট ক্লোন করা |
| `git clone -b <branch-name> <repo-link>` | নির্দিষ্ট একটি ব্রাঞ্চ সরাসরি ক্লোন করা |

---

## 20 .gitignore সেটআপ ও ব্যবহার

| ধাপ / প্যাটার্ন | বাংলা ব্যাখ্যা |
|---------|-------------|
| `.gitignore` ফাইল তৈরি | যে ফাইলগুলো গিটে আপলোড করা উচিত নয় তা তালিকাভুক্ত করা |
| `.vscode/` | VS Code সেটিং ইগনোর করা |
| `node_modules/` | NPM নির্ভরতা ফোল্ডার ইগনোর করা |
| `.env` | সিক্রেট চাবি ও পাসওয়ার্ড ইগনোর করা |
| `*.log` | সমস্ত লগ ফাইল ইগনোর করা |
| `dist/` অথবা `build/` | বিল্ড ফোল্ডার বাদ দেওয়া |

---

## 21 রিমোট ইউআরএল পরিচালনা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git remote -v` | কানেক্ট থাকা গিটহাব রিপোজিটরির লিংক দেখা |
| `git remote add origin <url>` | নতুন রিমোট যুক্ত করা |
| `git remote remove origin` | রিমোট কানেকশন রিমুভ করা |
| `git remote rename origin new-origin` | রিমোটের নাম পরিবর্তন করা |
| `git remote set-url origin <new-url>` | রিমোট ইউআরএল আপডেট বা পরিবর্তন করা |

---

## 22 ভার্সন ট্যাগিং (Software Release Tag)

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git tag v1.0` | লাইটওয়েট ভার্সন ট্যাগ তৈরি করা |
| `git tag -a v1.0 -m "Release v1.0"` | বিবরণসহ অফিসিয়াল রিলিজ ট্যাগ তৈরি করা |
| `git tag` | সমস্ত ট্যাগের তালিকা দেখা |
| `git push origin v1.0` | নির্দিষ্ট ট্যাগ গিটহাবে আপলোড করা |
| `git push origin --tags` | সব ট্যাগ গিটহাবে পাঠানো |
| `git tag -d v1.0` | লোকাল ট্যাগ ডিলিট করা |
| `git push origin --delete v1.0` | গিটহাবের রিমোট ট্যাগ ডিলিট করা |

---

## 23 আধুনিক গিট নেভিগেশন (git switch & restore)

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git switch <branch-name>` | এক ব্রাঞ্চ থেকে অন্য ব্রাঞ্চে যাওয়া (আধুনিক নিয়ম) |
| `git switch -c <new-branch>` | নতুন ব্রাঞ্চ বানিয়ে সেখানে যাওয়া |
| `git switch -` | ঠিক আগের ব্রাঞ্চে ফেরত যাওয়া |
| `git restore <file>` | ফাইলের শেষ সেভ করা অবস্থায় ফিরিয়ে আনা |
| `git restore --staged <file>` | ফাইল আন-স্টেজ করা |

---

## 24 মার্জ কনফ্লিক্ট সমাধান করা

| ধাপ / কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git status` | কনফ্লিক্ট হওয়া ফাইলের তালিকা দেখা |
| ম্যানুয়ালি ফাইল এডিট করা | কোডে `<<<<<<<`, `=======`, `>>>>>>>` চিহ্ন দেখে সঠিক কোড রাখা |
| `git add <resolved-file>` | সমাধান হওয়া ফাইল মার্ক করা |
| `git commit -m "Resolved merge conflict"` | কনফ্লিক্ট মার্জ সম্পন্ন করা |
| `git merge --abort` | আটকে যাওয়া মার্জ বাতিল করে আগের অবস্থায় ফেরত যাওয়া |
| `git rebase --abort` | আটকে যাওয়া রিবেস বাতিল করা |

---

## 25 গিট রিফ্লগ - হারিয়ে যাওয়া কোড উদ্ধার করা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git reflog` | গিট হেড পরিবর্তনের সমস্ত হিস্ট্রি ও কমিট হ্যাশ দেখা |
| `git checkout HEAD@{n}` | রিফ্লগের n নম্বর পয়েন্টে কি কোড ছিল দেখা |
| `git reset --hard HEAD@{n}` | হারিয়ে যাওয়া বা ডিলিট হওয়া কোড হুবহু ফেরত আনা |
| `git branch <recovered-branch> <commit-hash>` | মুছে যাওয়া ব্রাঞ্চ আবার বাঁচিয়ে তোলা |

---

## 26 অ্যাডভান্সড লগ ও কার কোন লাইন তা দেখা

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git log --graph --oneline --all` | চমৎকার ভিজুয়াল ট্রি দিয়ে সব ব্রাঞ্চের হিস্ট্রি দেখা |
| `git log -n 5` | শুধুমাত্র শেষ ৫টি কমিট দেখা |
| `git log --author="Name"` | নির্দিষ্ট ডেভেলপারের কমিট খোঁজা |
| `git log -p <file>` | একটি ফাইলের পুরো জীবনবৃত্তান্ত ও পরিবর্তন দেখা |
| `git blame <file>` | ফাইলের কোন লাইন কে কত তারিখে লিখেছে তা দেখা |

---

## 27 চেরি-পিক ও ইন্টারেক্টিভ রিবেস

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git cherry-pick <commit-hash>` | অন্য ব্রাঞ্চের নির্দিষ্ট একটি কমিট নিজের ব্রাঞ্চে নিয়ে আসা |
| `git rebase main` | কারেন্ট ব্রাঞ্চের বেসকে মেইন ব্রাঞ্চের সাথে রি-বেস করা |
| `git rebase -i HEAD~3` | শেষ ৩টি কমিট একসাথে জোড়া দেওয়া বা ইডিট করা |

---

## 28 অপ্রয়োজনীয় ফাইল পরিষ্কার করা (git clean)

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git clean -n` | ডিলিট করার আগে ড্রায়-রান করে দেখা কোনগুলো ডিলিট হবে |
| `git clean -f` | আন-ট্র্যাকড অপ্রয়োজনীয় ফাইল ডিলিট করা |
| `git clean -fd` | আন-ট্র্যাকড ফাইল ও ফোল্ডার সম্পূর্ণ সাফ করা |
| `git clean -fx` | ইগনোর করা ফাইলসহ সমস্ত ক্যাশ সাফ করা |

---

## 29 GitHub CLI (gh) দিয়ে টার্মিনাল কমান্ড

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `gh auth login` | টার্মিনালেই গিটহাব একাউন্ট লগইন করা |
| `gh repo create <name> --public` | টার্মিনাল থেকেই গিটহাবে নতুন পাবলিক রিপো তৈরি করা |
| `gh repo clone <owner/repo>` | গিটহাব সিএলআই দিয়ে ক্লোন করা |
| `gh pr create --title "Title" --body "Details"` | ব্রাউজার ছাড়াই সরাসরি Pull Request (PR) পাঠানো |
| `gh pr list` | ওপেন থাকা সমস্ত পিআর দেখা |
| `gh pr merge <pr-number>` | টার্মিনাল দিয়েই পিআর মার্জ করে ফেলা |
| `gh issue create --title "Bug title"` | গিটহাব ইস্যু সাবমিট করা |
| `gh release create v1.0` | অফিশিয়াল রিলিজ তৈরি করা |

---

## 30 গিট সাবমডিউল ব্যবহার

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git submodule add <repo-url> <path>` | প্রজেক্টের ভিতর অন্য একটি গিট প্রজেক্ট যোগ করা |
| `git submodule update --init --recursive` | প্রধান প্রজেক্ট ক্লোন করার পর সাবমডিউলগুলো লোড করা |
| `git submodule update --remote` | সাবমডিউল লেটেস্ট কোডে আপডেট করা |

---

## 31 গিট শর্টকাট (Aliases) তৈরি

| কমান্ড | বাংলা ব্যাখ্যা |
|---------|-------------|
| `git config --global alias.st status` | `git st` লিখলেই `git status` কাজ করবে |
| `git config --global alias.co checkout` | `git co` লিখলেই `git checkout` কাজ করবে |
| `git config --global alias.br branch` | `git br` লিখলেই `git branch` কাজ করবে |
| `git config --global alias.ci commit` | `git ci` লিখলেই `git commit` কাজ করবে |
| `git config --global alias.lg "log --graph --oneline --all"` | `git lg` দিয়ে ভিজুয়াল গাছ দেখা |

---

<br/>
<hr/>
<br/>

# 🇪🇸 Versión en Español

<p align="right"><a href="#top">⬆ Volver a la Selección de Idioma</a></p>

## 📌 Tabla de Contenidos (Español)

1. [Configuración de Git](#1-configuración-de-git)
2. [Token de Acceso Personal de GitHub (PAT)](#2-token-de-acceso-personal-de-github-pat)  
   2.1 [Configuración de Autenticación con Clave SSH](#21-configuración-de-autenticación-con-clave-ssh)
3. [Conectar Repositorio Local a Remoto](#3-conectar-repositorio-local-a-remoto)
4. [Flujo de Trabajo Básico de Git](#4-flujo-de-trabajo-básico-de-git)
5. [Publicar Cambios en Un Solo Clic](#5-publicar-cambios-en-un-solo-clic)
6. [Manejo de Archivos Eliminados](#6-manejo-de-archivos-eliminados)
7. [Actualizar y Clonar Versión del Repositorio](#7-actualizar-y-clonar-versión-del-repositorio)
8. [Sincronizar Última Versión de GitHub](#8-sincronizar-última-versión-de-github)
9. [Habilitar Rutas Largas en Git](#9-habilitar-rutas-largas-en-git)
10. [Renombrar Carpetas y Actualizar Archivos](#10-renombrar-carpetas-y-actualizar-archivos)
11. [Eliminar Carpeta .vscode del Seguimiento](#11-eliminar-carpeta-vscode-del-seguimiento)
12. [Restablecer Repositorio Git](#12-restablecer-repositorio-git)
13. [Flujo de Trabajo para Rama de Función (Feature Branch)](#13-flujo-de-trabajo-para-rama-de-función-feature-branch)
14. [Fusión de Rama de Función a Principal](#14-fusión-de-rama-de-función-a-principal)
15. [Gestión de Ramas](#15-gestión-de-ramas)
16. [Ver Historial y Registros (Logs)](#16-ver-historial-y-registros-logs)
17. [Deshacer y Corregir Errores](#17-deshacer-y-corregir-errores)
18. [Stash (Guardado Temporal)](#18-stash-guardado-temporal)
19. [Clonar Repositorio](#19-clonar-repositorio)
20. [Configuración de .gitignore](#20-configuración-de-gitignore)
21. [Gestión de Remotos](#21-gestión-de-remotos)
22. [Etiquetado (Control de Versiones)](#22-etiquetado-control-de-versiones)
23. [Navegación Moderna en Git (git switch y restore)](#23-navegación-moderna-en-git-git-switch-y-restore)
24. [Resolución de Conflictos de Fusión](#24-resolución-de-conflictos-de-fusión)
25. [Git Reflog – Recuperar Commits Perdidos](#25-git-reflog--recuperar-commits-perdidos)
26. [Historial Avanzado y Rastreo de Líneas](#26-historial-avanzado-y-rastreo-de-líneas)
27. [Cherry-Pick y Rebase Interactivo](#27-cherry-pick-y-rebase-interactivo)
28. [Limpieza de Archivos no Rastreados](#28-limpieza-de-archivos-no-rastreados)
29. [Comandos del CLI de GitHub (gh)](#29-comandos-del-cli-de-github-gh)
30. [Submódulos de Git](#30-submódulos-de-git)
31. [Alias y Accesos Directos de Git](#31-alias-y-accesos-directos-de-git)

---

## 1 Configuración de Git

| Comando | Explicación en Español |
|---------|-------------|
| `git config --global user.name "your-username"` | Establecer nombre de usuario global |
| `git config --global user.email "abc@gmil.com"` | Establecer correo electrónico global |
| `git config --list` | Ver toda la configuración de Git |

---

## 2 Token de Acceso Personal de GitHub (PAT)

| Paso | Explicación en Español |
|------|-------------|
| **Settings → Developer settings → Personal access tokens → Tokens (classic)** | Navegar para generar un token de acceso personal |
| Seleccionar permisos | Seleccionar scopes generales: repo, notes, admin:org |
| Token de ejemplo | `ghp_yourPersonalAccessTokenHere...` |

---

### 2.1 Configuración de Autenticación con Clave SSH

| Comando | Explicación en Español |
|---------|-------------|
| `ssh-keygen -t ed25519 -C "your_email@example.com"` | Generar un par de claves SSH seguras |
| `eval "$(ssh-agent -s)"` | Iniciar el agente SSH en la terminal |
| `ssh-add ~/.ssh/id_ed25519` | Añadir la clave privada SSH al agente |
| `cat ~/.ssh/id_ed25519.pub` | Mostrar clave pública (copiar y pegar en GitHub Settings) |
| `ssh -T git@github.com` | Probar conexión con GitHub mediante SSH |
| `git remote set-url origin git@github.com:username/repo.git` | Cambiar URL remota de HTTPS a SSH |

---

## 3 Conectar Repositorio Local a Remoto

| Comando | Explicación en Español |
|---------|-------------|
| `git remote add origin https://github.com/Shariar-Ahamed/<repo>` | Añadir repositorio de GitHub como remoto |
| `git remote set-url origin https://<token>@github.com/Shariar-Ahamed/<repo>` | Conectar usando PAT para autenticación |

---

## 4 Flujo de Trabajo Básico de Git

| Comando | Explicación en Español |
|---------|-------------|
| `git init` | Inicializar repositorio Git local |
| `git status` | Verificar estado del repositorio |
| `git add .` | Preparar (stage) todos los cambios |
| `git commit -m "New Commit"` | Guardar cambios en el repositorio local |
| `git branch -M main` | Renombrar rama predeterminada a main |
| `git push -u origin main` | Subir cambios a GitHub |

---

## 5 Publicar Cambios en Un Solo Clic

```bash
git add .
git commit -m "Update File"
git branch -M main
git push -u origin main
``` 
*Explicación: Preparar cambios, confirmar con mensaje descriptivo, asegurar rama main activa y subir a GitHub.*

---

## 6 Manejo de Archivos Eliminados

> [!WARNING]
> **¡Use Force Push (`git push -f`) con extrema precaución!** Sobrescribe el historial del repositorio remoto y puede borrar el trabajo de sus compañeros.

| Comando | Explicación en Español |
|---------|-------------|
| `git add -A` | Preparar todos los cambios incluyendo eliminaciones |
| `git commit -m "Updated file structure and removed old files"` | Confirmar cambios con eliminación |
| `git push -f origin main` | Forzar la subida de cambios a GitHub |

---

## 7 Actualizar y Clonar Versión del Repositorio

| Comando                         | Explicación en Español |
| ------------------------------- | ------------------------------------------ |
| `git pull origin main`          | Descargar último código de la rama `main` remota |
| `git pull`                      | Actualizar repositorio local desde rama rastreada |
| `git pull origin main --rebase` | Descargar y mantener historial limpio |
| `git push origin main`          | Subir cambios locales al repositorio remoto |

---

## 8 Sincronizar Última Versión de GitHub

| Comando | Explicación en Español |
|---------|-------------|
| `git fetch origin` | Obtener los últimos commits del servidor remoto |
| `git reset --hard origin/main` | Sincronizar repositorio local idéntico a GitHub |

---

## 9 Habilitar Rutas Largas en Git

| Comando | Explicación en Español |
|---------|-------------|
| `git config --system core.longpaths true` | Habilitar soporte para rutas largas en Windows |

---

## 10 Renombrar Carpetas y Actualizar Archivos

| Comando | Explicación en Español |
|---------|-------------|
| Renombrar carpeta en VS Code y actualizar archivos | Cambios manuales del proyecto |
| `git add -A` | Preparar todos los cambios (renombrados y eliminaciones) |
| `git commit -m "Folder renamed and updated"` | Confirmar actualización |
| `git push origin main` | Subir cambios a GitHub |

---

## 11 Eliminar Carpeta .vscode del Seguimiento

| Comando | Explicación en Español |
|---------|-------------|
| `git rm -r --cached .vscode` | Eliminar `.vscode` del rastreo de Git |
| `git commit -m "Remove .vscode folder"` | Confirmar eliminación del índice |
| `git push` | Subir actualización a GitHub |

---

## 12 Restablecer Repositorio Git

| Comando / Shell | Explicación en Español |
|---------|-------------|
| `rm -rf .git` (Git Bash / Linux / Mac) | Eliminar carpeta `.git` (elimina todo el historial y rastreo) |
| `Remove-Item -Recurse -Force .git` (PowerShell) | Eliminar carpeta `.git` en Windows PowerShell |

---

## 13 Flujo de Trabajo para Rama de Función (Feature Branch)

| Comando | Explicación en Español |
|---------|-------------|
| `git pull origin main` | Obtener últimas actualizaciones de la rama main |
| `git checkout -b feature-yourName` | Crear y cambiar a una nueva rama de función |
| `git add .` | Preparar todos los cambios |
| `git commit -m "Your-commit"` | Guardar cambios con un mensaje |
| `git push origin feature-yourName` | Subir la rama activa a GitHub |

---

## 14 Fusión de Rama de Función a Principal

| Comando | Explicación en Español |
|---------|-------------|
| `git checkout main` | Cambiar a la rama principal (main) |
| `git pull origin main` | Descargar últimas actualizaciones de main |
| `git fetch origin` | Obtener todas las ramas remotas |
| `git merge origin/feature-yourName` | Fusionar la rama de función en main |
| `git push origin main` | Subir la rama principal actualizada a GitHub |

---

## 15 Gestión de Ramas

| Comando | Explicación en Español |
|---------|-------------|
| `git branch` | Listar ramas locales |
| `git branch -a` | Listar ramas locales y remotas |
| `git branch new-branch` | Crear una nueva rama |
| `git checkout new-branch` | Cambiar a otra rama |
| `git checkout -b new-branch` | Crear y cambiar a la nueva rama |
| `git merge new-branch` | Fusionar rama en la rama actual |
| `git branch -d new-branch` | Eliminar una rama local de forma segura |
| `git branch -D new-branch` | Forzar eliminación de rama no fusionada |
| `git push origin --delete branch-name` | Eliminar una rama remota en GitHub |

---

## 16 Ver Historial y Registros (Logs)

| Comando | Explicación en Español |
|---------|-------------|
| `git log` | Ver historial de commits |
| `git log --oneline` | Historial de commits resumido en una línea |
| `git diff` | Mostrar cambios no preparados |
| `git diff --staged` | Mostrar cambios preparados para commit |
| `git show` | Mostrar detalles del último commit |
| `git show <commit-hash>` | Mostrar detalles de un commit específico |

---

## 17 Deshacer y Corregir Errores

| Comando | Explicación en Español |
|---------|-------------|
| `git restore file.txt` | Restaurar archivo al último estado confirmado |
| `git reset HEAD file.txt` | Quitar archivo del área de preparación (unstage) |
| `git commit --amend` | Modificar el último mensaje de commit |
| `git reset --soft HEAD~1` | Deshacer commit pero mantener cambios preparados |
| `git reset --mixed HEAD~1` | Deshacer commit y des-preparar cambios |
| `git reset --hard HEAD~1` | Deshacer commit y descartar todos los cambios |
| `git revert <commit-hash>` | Crear un nuevo commit que revierte uno anterior |

---

## 18 Stash (Guardado Temporal)

| Comando | Explicación en Español |
|---------|-------------|
| `git stash` | Guardar cambios no confirmados temporalmente |
| `git stash save "message"` | Guardar stash con un nombre descriptivo |
| `git stash pop` | Aplicar y eliminar el último stash guardado |
| `git stash apply` | Aplicar el último stash sin eliminarlo |
| `git stash list` | Mostrar todos los stashes guardados |
| `git stash drop` | Eliminar el último stash |
| `git stash clear` | Eliminar todos los stashes guardados |

---

## 19 Clonar Repositorio

| Comando | Explicación en Español |
|---------|-------------|
| `git clone https://github.com/username/repo.git` | Clonar repositorio de GitHub en una nueva carpeta |
| `git clone <repo-link> .` | Clonar repositorio en la carpeta actual |
| `git clone -b <branch-name> <repo-link>` | Clonar una rama específica directamente |

---

## 20 Configuración de .gitignore

| Paso / Patrón | Explicación en Español |
|---------|-------------|
| Crear archivo `.gitignore` | Archivo para ignorar archivos/carpetas en Git |
| `.vscode/` | Ignorar configuración de VS Code |
| `node_modules/` | Ignorar dependencias de NPM |
| `.env` | Ignorar claves de entorno y contraseñas |
| `*.log` | Ignorar archivos de registros |
| `dist/` o `build/` | Ignorar carpetas de compilación |

---

## 21 Gestión de Remotos

| Comando | Explicación en Español |
|---------|-------------|
| `git remote -v` | Mostrar URLs de repositorios remotos |
| `git remote add origin <url>` | Añadir nueva conexión remota |
| `git remote remove origin` | Eliminar conexión remota |
| `git remote rename origin new-origin` | Renombrar referencia remota |
| `git remote set-url origin <new-url>` | Actualizar URL del repositorio remoto |

---

## 22 Etiquetado (Control de Versiones)

| Comando | Explicación en Español |
|---------|-------------|
| `git tag v1.0` | Crear una etiqueta de versión ligera |
| `git tag -a v1.0 -m "Release v1.0"` | Crear etiqueta anotada con mensaje |
| `git tag` | Listar todas las etiquetas |
| `git push origin v1.0` | Subir etiqueta específica a GitHub |
| `git push origin --tags` | Subir todas las etiquetas a GitHub |
| `git tag -d v1.0` | Eliminar etiqueta local |
| `git push origin --delete v1.0` | Eliminar etiqueta remota en GitHub |

---

## 23 Navegación Moderna en Git (git switch y restore)

| Comando | Explicación en Español |
|---------|-------------|
| `git switch <branch-name>` | Cambiar a una rama existente |
| `git switch -c <new-branch>` | Crear y cambiar a una nueva rama |
| `git switch -` | Volver a la rama anterior |
| `git restore <file>` | Descartar cambios en el directorio de trabajo |
| `git restore --staged <file>` | Quitar archivo del área de preparación |

---

## 24 Resolución de Conflictos de Fusión

| Paso / Comando | Explicación en Español |
|---------|-------------|
| `git status` | Ver lista de archivos con conflictos de fusión |
| Editar archivos manualmente | Buscar marcas `<<<<<<<`, `=======`, `>>>>>>>` y conservar código deseado |
| `git add <resolved-file>` | Marcar conflicto como resuelto |
| `git commit -m "Resolved merge conflict"` | Completar el proceso de fusión |
| `git merge --abort` | Abortar fusión atascada y volver al estado anterior |
| `git rebase --abort` | Abortar operación de rebase atascada |

---

## 25 Git Reflog – Recuperar Commits Perdidos

| Comando | Explicación en Español |
|---------|-------------|
| `git reflog` | Ver historial de seguridad de todas las acciones con sus hashes |
| `git checkout HEAD@{n}` | Inspeccionar el estado en la entrada reflog `n` |
| `git reset --hard HEAD@{n}` | Restaurar repositorio al estado exacto del reflog `n` |
| `git branch <recovered-branch> <commit-hash>` | Recrear una rama eliminada desde un hash del reflog |

---

## 26 Historial Avanzado y Rastreo de Líneas

| Comando | Explicación en Español |
|---------|-------------|
| `git log --graph --oneline --all` | Mostrar representación visual del árbol de ramas |
| `git log -n 5` | Mostrar solo los últimos 5 commits |
| `git log --author="Name"` | Filtrar commits por autor |
| `git log -p <file>` | Mostrar historial de cambios detallado para un archivo |
| `git blame <file>` | Mostrar desglose línea por línea de quién modificó cada línea y cuándo |

---

## 27 Cherry-Pick y Rebase Interactivo

| Comando | Explicación en Español |
|---------|-------------|
| `git cherry-pick <commit-hash>` | Aplicar un commit específico de otra rama en la rama actual |
| `git rebase main` | Rebasar la rama actual sobre la rama main |
| `git rebase -i HEAD~3` | Abrir editor interactivo para combinar, editar o renombrar commits |

---

## 28 Limpieza de Archivos no Rastreados

| Comando | Explicación en Español |
|---------|-------------|
| `git clean -n` | Vista previa de los archivos no rastreados que se eliminarán |
| `git clean -f` | Forzar eliminación de archivos no rastreados |
| `git clean -fd` | Forzar eliminación de archivos y carpetas no rastreados |
| `git clean -fx` | Eliminar todos los archivos no rastreados incluidos los ignorados |

---

## 29 Comandos del CLI de GitHub (gh)

| Comando | Explicación en Español |
|---------|-------------|
| `gh auth login` | Autenticar la terminal con su cuenta de GitHub |
| `gh repo create <name> --public` | Crear un nuevo repositorio público desde la terminal |
| `gh repo clone <owner/repo>` | Clonar repositorio usando el CLI de GitHub |
| `gh pr create --title "Title" --body "Details"` | Crear una Pull Request en GitHub |
| `gh pr list` | Listar Pull Requests abiertas |
| `gh pr merge <pr-number>` | Fusionar una Pull Request directamente desde el CLI |
| `gh issue create --title "Bug title"` | Crear un Issue en GitHub |
| `gh release create v1.0` | Crear una versión oficial de Release en GitHub |

---

## 30 Submódulos de Git

| Comando | Explicación en Español |
|---------|-------------|
| `git submodule add <repo-url> <path>` | Añadir otro repositorio Git como submódulo dentro del proyecto |
| `git submodule update --init --recursive` | Inicializar y clonar todos los submódulos tras clonar el repositorio |
| `git submodule update --remote` | Actualizar submódulos a sus últimos commits remotos |

---

## 31 Alias y Accesos Directos de Git

| Comando | Explicación en Español |
|---------|-------------|
| `git config --global alias.st status` | Acceso directo: Escriba `git st` para `git status` |
| `git config --global alias.co checkout` | Acceso directo: Escriba `git co` para `git checkout` |
| `git config --global alias.br branch` | Acceso directo: Escriba `git br` para `git branch` |
| `git config --global alias.ci commit` | Acceso directo: Escriba `git ci` para `git commit` |
| `git config --global alias.lg "log --graph --oneline --all"` | Acceso directo: Escriba `git lg` para ver el árbol visual |

---

## 🚀 Pro Tips / Sugerencias Profesionales

- **Always run `git pull`** before starting new work to prevent merge conflicts.
- **Ejecute siempre `git pull`** antes de empezar a trabajar para evitar conflictos.
- **Escriba mensajes de commit descriptivos** (`fix: solve navbar toggle bug`).
- **Mantenga `.gitignore` actualizado** para no subir claves secretas o dependencias pesadas.
- **Utilice ramas de funciones** (`feature/navbar`) para trabajar en lugar de subir directo a `main`.
- **Use `git reflog`** si cree que perdió código: ¡Git casi nunca borra datos confirmados!
