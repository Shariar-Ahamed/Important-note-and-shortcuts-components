# GitHub All Code – Commands & Explanations

This document contains **commonly used Git and GitHub commands** in table format.  
Left column = command / code, Right column = explanation.  
Quick reference for beginners and daily practice.

---

## 📑 Table of Contents
- [1️⃣ Git Installation & GitHub Account Setup](#1️⃣-git-installation--github-account-setup)
- [2️⃣ Git Configuration (First-Time Setup)](#2️⃣-git-configuration-first-time-setup)
- [3️⃣ Working Directory & Repository Setup](#3️⃣-working-directory--repository-setup)
- [4️⃣ Working Directory → Staging Area](#4️⃣-working-directory-→-staging-area)
- [5️⃣ Staging Area → Local Repository (Commit)](#5️⃣-staging-area-→-local-repository-commit)
- [6️⃣ Commit, HEAD & Undo Operations](#6️⃣-commit-head--undo-operations)
- [7️⃣ GitHub Profile & README](#7️⃣-github-profile--readme)
- [8️⃣ Local Repository → Remote Repository](#8️⃣-local-repository-→-remote-repository)
- [9️⃣ Push Project to GitHub](#9️⃣-push-project-to-github)
- [🔟 Git Pull (Online → Offline)](#🔟-git-pull-online-→-offline)
- [1️⃣1️⃣ Branching & Merging](#1️⃣1️⃣-branching--merging)
- [1️⃣2️⃣ Merge Concepts](#1️⃣2️⃣-merge-concepts)
- [📝 Short Description](#📝-short-description)
- [📚 Reference](#📚-reference)

---

## 1️⃣ Git Installation & GitHub Account Setup

| Command / Step | Explanation |
|----------------|-------------|
| **Install Git** | Download Git from https://git-scm.com/downloads |
| **`git --version`** | Check Git installation and version |
| **Create GitHub account** | https://github.com/ |

---

## 2️⃣ Git Configuration (First-Time Setup)

| Command / Step | Explanation |
|----------------|-------------|
| **`Ctrl + L`** | Clear terminal screen |
| **`git config --global user.name "your-username"`** | Set global Git username |
| **`git config --global user.email "abc@gmail.com"`** | Set global Git email |
| **`git config --global user.name`** | Show configured username |
| **`git config --list`** | Show all Git configurations |

---

## 3️⃣ Working Directory & Repository Setup

| Command / Step | Explanation |
|----------------|-------------|
| **`mkdir first-repo`** | Create a new folder called `first-repo` |
| **`cd first-repo`** | Move into the folder |
| **`git init`** | Initialize Git repository |
| **`ls -a`** | Show all files including hidden `.git` folder |
| **`ls`** | Show all visible files and folders |
| **`touch one.html`** | Create a new file `one.html` |
| **`git status`** | Check repository status |
| **`D:`** | Go fixed D drive (TAB key suggest) |
| **`cd ../`** | Go back to previous folder |
| **`pwd`** | Show current directory |
| **`rm -rf folder_name`** | Delete a folder permanently |

---

## 4️⃣ Working Directory → Staging Area

| Command / Step | Explanation |
|----------------|-------------|
| **`git add file_name`** | Move a specific file to the staging area |
| **`git add .`** | Move all modified files to staging area |
| **`git diff`** | Show changes before staging |
| **`git restore file_name`** | Restore file to previous state |
| **`git rm --cached file_name`** | Remove file from staging back to working directory |

---

## 5️⃣ Staging Area → Local Repository (Commit)

| Command / Step | Explanation |
|----------------|-------------|
| **`git commit -m "message"`** | Commit staged changes to local repository |
| **`git log`** | View full commit history |
| **`git add . && git commit -m "message"`** | Stage & commit changes in one step |
| **`git reset --soft HEAD^`** | Undo last commit → move changes to staging |
| **`git reset HEAD^`** | Undo last commit → move changes to working directory |
| **`git reset --hard HEAD^`** | Undo last commit → delete changes |

---

## 6️⃣ Commit, HEAD & Undo Operations

| Command / Step | Explanation |
|----------------|-------------|
| **`git log --oneline`** | View compact commit history |
| **`git show`** | Show latest commit details |
| **`git show commit_id`** | Show specific commit details |
| **`git show HEAD~number`** | Show previous commit |
| **`git checkout one.txt`** | Undo changes in a file |
| **`git checkout commit_id`** | Move project to specific commit state |
| **`git checkout master`** | Move back to latest commit (HEAD) |

---

## 7️⃣ GitHub Profile & README

| Command / Step | Explanation |
|----------------|-------------|
| **GitHub Profile README Generators** | <https://rahuldkjain.github.io/gh-profile-readme-generator/> <br> <https://arturssmirnovs.github.io/github-profile-readme-generator/> |

---

## 8️⃣ Local Repository → Remote Repository

| Command / Step | Explanation |
|----------------|-------------|
| **`git remote`** | Show connected remote repositories |
| **`git remote add origin repo_url`** | Connect local repo to GitHub repo |
| **`git remote -v`** | Show remote URLs |
| **`git clone repo_url`** | Copy GitHub repo to local machine |

---

## 9️⃣ Push Project to GitHub

| Command / Step | Explanation |
|----------------|-------------|
| **`git branch -M main`** | Rename branch to main |
| **`git push -u origin main`** | Push local commits to GitHub |

---

## 🔟 Git Pull (Online → Offline)

| Command / Step | Explanation |
|----------------|-------------|
| **`git pull`** | Update local repository with GitHub changes |

---

## 1️⃣1️⃣ Branching & Merging

| Command / Step | Explanation |
|----------------|-------------|
| **`git branch`** | List all branches |
| **`git branch feature-1`** | Create a new branch called feature-1 |
| **`git checkout feature-1`** | Switch to branch feature-1 |
| **`git branch -d feature-1`** | Delete branch feature-1 |
| **`git push -u origin feature-2`** | Push a branch to GitHub |
| **`git merge feature-10`** | Merge a feature branch into main |

---

## 1️⃣2️⃣ Merge Concepts

- Fast-forward merge (2-way)  
- Three-way merge  
- Merge conflict handling  

🔗 Visual Git learning: <https://git-school.github.io/visualizing-git/>

---

## 📝 Short Description

This repository is a **complete Git & GitHub command cheat sheet**.  
It is designed for **quick reference, learning, and daily development use**.  
All commands are organized **with explanation**, making it beginner-friendly and easy to follow.

---

## 📚 Reference
- 
- YouTube Playlist: [Go Playlist](https://www.youtube.com/playlist?list=PLerpoOYRrjUy2ja0tTHexJq7iwYaL4obp)