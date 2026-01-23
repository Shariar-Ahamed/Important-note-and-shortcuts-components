# GitHub Setup & Main Code – Commands & Explanations

This document contains **step-by-step Git & GitHub setup commands** for connecting local projects, pushing updates, and managing repositories.  
Left column = command / code, Right column = explanation.

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
| Example token | `ghp_g6n3SBvMRDEs7moKcbIE3W42hhlnz017IaHZ` |

---

## 3 Connect Local Repository to Remote

> **Optional remote setup:**  
> - `git remote add origin https://github.com/username/<repo>`  
> - `git remote set-url origin https://<token>@github.com/username/<repo>`

### Example:

| Command | Explanation |
|---------|-------------|
| `git remote add origin https://github.com/Shariar-Ahamed/<--*your site-link*-->` | Add GitHub repo as remote |
| `git remote set-url origin https://<--*your token--*>@github.com/Shariar-Ahamed/<--*your site-link*-->` | Connect using PAT for authentication |

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

### Command
```bash
git add .
git commit -m "Update File"
git branch -M main
git push -u origin main
``` 
### Explanation:
Stage all project changes, Commit with descriptive message, Ensure main branch is active, Push commit to GitHub

---

## 6 Handling Deleted Files

| Command | Explanation |
|---------|-------------|
| `git add -A` | Stage all changes including deletions |
| `git commit -m "Updated file structure and removed old files"` | Commit updates with deletion |
| `git push -f origin main` | Force push changes to GitHub |

---

## 7 README.md Updates

| Command | Explanation |
|---------|-------------|
| `git pull origin main --rebase` | Pull latest changes before editing README |
| `git push origin main` | Push updated README to GitHub |

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

## 11 Reset Git Repository

| Command | Explanation |
|---------|-------------|
| `rm -rf .git` | Delete `.git` folder (removes Git history, remote, all tracking) |

---

## 📝 Short Description

This folder contains **GitHub setup and main project workflow commands**.  
It’s designed for **quick setup, push, pull, and repository management**, making it beginner-friendly and easy to follow for any project.
