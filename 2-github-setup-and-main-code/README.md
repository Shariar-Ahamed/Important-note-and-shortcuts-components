<h2 align="center">GitHub Setup & Main Code – Commands & Explanations</h2>

<p align="center">
This document contains <b>step-by-step Git & GitHub setup commands</b> for connecting local projects, pushing updates, and managing repositories.  
Left column = command / code, Right column = explanation.
</p>

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

| Command | Explanation |
|---------|-------------|
| `rm -rf .git` | Delete `.git` folder (removes Git history, remote, all tracking) |

---

## 13 Feature Branch Push Workflow (Active → Remote)

| Command                            | Explanation                                |
| ---------------------------------- | ------------------------------------------ |
| `git pull origin main`             | Get latest updates from GitHub main branch |
| `git checkout -b feature-yourName` | Create and switch to a new feature branch  |
| `git add .`                        | Stage all changes                          |
| `git commit -m "Your-commit"`      | Save changes with a message                |
| `git push origin feature-yourName` | Upload active feature branch to GitHub     |

---
## 14 Feature Branch Merge Workflow (Feature → Main)

| Command | Explanation |
|---------|-------------|
| `git checkout main` | Switch to main branch |
| `git pull origin main` | Get latest updates from GitHub main branch |
| `git fetch origin` | Fetch all latest branches and updates from remote |
| `git merge origin/feature-yourName` | Merge friend’s feature-yourName branch into main |
| `git push origin main` | Upload updated main branch to GitHub |
---

## 15 Branch Management

| Command | Explanation |
|---------|-------------|
| `git branch` | List all local branches |
| `git branch new-branch` | Create a new branch |
| `git checkout new-branch` | Switch to another branch |
| `git checkout -b new-branch` | Create & switch to new branch |
| `git merge new-branch` | Merge branch into current branch |
| `git branch -d new-branch` | Delete a branch |

---

## 16 Checking History & Logs

| Command | Explanation |
|---------|-------------|
| `git log` | View commit history |
| `git log --oneline` | Short commit history |
| `git diff` | Show changes between commits/files |
| `git show` | Show details of a commit |

---

## 17 Undo & Fix Mistakes

| Command | Explanation |
|---------|-------------|
| `git restore file.txt` | Restore file to last committed state |
| `git reset HEAD file.txt` | Unstage a file |
| `git commit --amend` | Edit last commit message |
| `git reset --soft HEAD~1` | Undo last commit but keep changes |
| `git reset --hard HEAD~1` | Undo last commit and delete changes |

---

## 18 Stash (Temporary Save)

| Command | Explanation |
|---------|-------------|
| `git stash` | Save current changes temporarily |
| `git stash pop` | Restore saved changes |
| `git stash list` | Show all saved stashes |

---

## 19 Clone Repository

| Command | Explanation |
|---------|-------------|
| `git clone https://github.com/username/repo.git` | Clone repository from GitHub |
| `git clone <repo-link> .` | Clone into current folder |

---

## 20 .gitignore Setup

| Command | Explanation |
|---------|-------------|
| Create `.gitignore` file | Used to ignore unnecessary files |
| Example: `.vscode/` | Ignore VS Code settings |
| Example: `node_modules/` | Ignore dependencies |

---

## 21 Remote Management

| Command | Explanation |
|---------|-------------|
| `git remote -v` | Show remote repository URLs |
| `git remote remove origin` | Remove remote connection |
| `git remote rename origin new-origin` | Rename remote repository |

---

## 22 Tagging (Version Control)

| Command | Explanation |
|---------|-------------|
| `git tag v1.0` | Create a version tag |
| `git tag` | List all tags |
| `git push origin v1.0` | Push tag to GitHub |

---

## 🚀 Pro Tips

- Always run `git pull` before starting new work  
- Use meaningful commit messages  
- Avoid pushing unnecessary files like `.vscode` and `node_modules`  
- Use branches for new features  
- Keep commit history clean using `--rebase`

---

## 📝 Short Description

This folder contains **GitHub setup and main project workflow commands**.  
It’s designed for **quick setup, push, pull, and repository management**, making it beginner-friendly and easy to follow for any project.
