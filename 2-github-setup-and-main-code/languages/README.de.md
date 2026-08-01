<h2 align="center">GitHub Setup & Hauptcode – Vollständiger Master-Leitfaden (Deutsch)</h2>

<p align="center">
Dieses Dokument ist ein <b>umfassendes Git & GitHub Referenzhandbuch</b> zum Verbinden lokaler Projekte, Veröffentlichen von Updates, Verwalten von Branches und Beheben von Konflikten.
</p>

<div align="center">

### 🌐 Select Language / Sprachen / भाषाएं / Idiomas / Langues / 语言 / اللغات:

<a href="../README.md"><img src="https://flagcdn.com/20x15/us.png" alt="USA" width="20" height="15"> <b>English</b></a> &nbsp;|&nbsp;
<a href="README.bn.md"><img src="https://flagcdn.com/20x15/bd.png" alt="Bangladesh" width="20" height="15"> <b>বাংলা (Bangla)</b></a> &nbsp;|&nbsp;
<a href="README.es.md"><img src="https://flagcdn.com/20x15/es.png" alt="Spain" width="20" height="15"> <b>Español</b></a> &nbsp;|&nbsp;
<a href="README.hi.md"><img src="https://flagcdn.com/20x15/in.png" alt="India" width="20" height="15"> <b>हिन्दी (Hindi)</b></a> &nbsp;|&nbsp;
<a href="README.fr.md"><img src="https://flagcdn.com/20x15/fr.png" alt="France" width="20" height="15"> <b>Français</b></a> &nbsp;|&nbsp;
<a href="README.de.md"><img src="https://flagcdn.com/20x15/de.png" alt="Germany" width="20" height="15"> <b>Deutsch</b></a> &nbsp;|&nbsp;
<a href="README.zh.md"><img src="https://flagcdn.com/20x15/cn.png" alt="China" width="20" height="15"> <b>中文</b></a> &nbsp;|&nbsp;
<a href="README.ar.md"><img src="https://flagcdn.com/20x15/sa.png" alt="Saudi Arabia" width="20" height="15"> <b>العربية</b></a>

</div>

---

## 📌 Inhaltsverzeichnis (Deutsch)

1. [Git-Konfiguration](#1-git-konfiguration)
2. [GitHub Personal Access Token (PAT)](#2-github-personal-access-token-pat)  
   2.1 [SSH-Schlüssel Authentifizierung](#21-ssh-schlüssel-authentifizierung)
3. [Lokales Repository mit Remote verbinden](#3-lokales-repository-mit-remote-verbinden)
4. [Grundlegender Git-Workflow](#4-grundlegender-git-workflow)
5. [Änderungen mit einem Klick pushen](#5-änderungen-mit-einem-klick-pushen)
6. [Gelöschte Dateien verwalten](#6-gelöschte-dateien-verwalten)
7. [Neuesten Code abrufen (Pull)](#7-neuesten-code-abrufen-pull)
8. [Lokalen Code auf GitHub-Stand zurücksetzen](#8-lokalen-code-auf-github-stand-zurücksetzen)
9. [Lange Dateipfade in Windows aktivieren](#9-lange-dateipfade-in-windows-aktivieren)
10. [Ordner umbenennen und Dateien aktualisieren](#10-ordner-umbenennen-und-dateien-aktualisieren)
11. [.vscode Ordner aus dem Tracking entfernen](#11-vscode-ordner-aus-dem-tracking-entfernen)
12. [Git-Repository zurücksetzen](#12-git-repository-zurücksetzen)
13. [Feature-Branch Push Workflow](#13-feature-branch-push-workflow)
14. [Feature-Branch in Main mergen](#14-feature-branch-in-main-mergen)
15. [Branch-Verwaltung](#15-branch-verwaltung)
16. [Historie und Logs prüfen](#16-historie-und-logs-prüfen)
17. [Fehler rückgängig machen und korrigieren](#17-fehler-rückgängig-machen-und-korrigieren)
18. [Stash (Temporäres Speichern)](#18-stash-temporäres-speichern)
19. [Repository klonen](#19-repository-klonen)
20. [.gitignore Einrichten](#20-gitignore-einrichten)
21. [Remote-Verwaltung](#21-remote-verwaltung)
22. [Tagging (Versionskontrolle)](#22-tagging-versionskontrolle)
23. [Moderne Git-Navigation (switch & restore)](#23-moderne-git-navigation-switch--restore)
24. [Merge-Konflikte lösen](#24-merge-konflikte-lösen)
25. [Git Reflog – Verlorenen Code wiederherstellen](#25-git-reflog--verlorenen-code-wiederherstellen)
26. [Erweiterte Historie und Zeilen-Tracking](#26-erweiterte-historie-und-zeilen-tracking)
27. [Cherry-Pick und Interaktives Rebase](#27-cherry-pick-und-interaktives-rebase)
28. [Unverfolgte Dateien bereinigen](#28-unverfolgte-dateien-bereinigen)
29. [GitHub CLI (gh) Befehle](#29-github-cli-gh-befehle)
30. [Git Submodule](#30-git-submodule)
31. [Git Shortcuts (Aliases)](#31-git-shortcuts-aliases)

---

## 1 Git-Konfiguration

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git config --global user.name "your-username"` | Globalen Git-Benutzernamen festlegen |
| `git config --global user.email "abc@gmil.com"` | Globale Git-E-Mail-Adresse festlegen |
| `git config --list` | Gesamte Git-Konfiguration anzeigen |

---

## 2 GitHub Personal Access Token (PAT)

| Schritt | Erklärung auf Deutsch |
|------|-------------|
| **Settings → Developer settings → Personal access tokens** | Token generieren |
| Berechtigungen wählen | repo, notes, admin:org auswählen |
| Beispiel-Token | `ghp_yourPersonalAccessTokenHere...` |

---

### 2.1 SSH-Schlüssel Authentifizierung

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `ssh-keygen -t ed25519 -C "your_email@example.com"` | Sicheres SSH-Schlüsselpaar erzeugen |
| `eval "$(ssh-agent -s)"` | SSH-Agent im Terminal starten |
| `ssh-add ~/.ssh/id_ed25519` | Privaten Schlüssel zum Agenten hinzufügen |
| `cat ~/.ssh/id_ed25519.pub` | Öffentlichen Schlüssel anzeigen (für GitHub) |
| `ssh -T git@github.com` | Verbindung zu GitHub testen |
| `git remote set-url origin git@github.com:username/repo.git` | Von HTTPS zu SSH wechseln |

---

## 3 Lokales Repository mit Remote verbinden

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git remote add origin https://github.com/Shariar-Ahamed/<repo>` | Remote-Repository hinzufügen |
| `git remote set-url origin https://<token>@github.com/Shariar-Ahamed/<repo>` | URL mit PAT-Token festlegen |

---

## 4 Grundlegender Git-Workflow

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git init` | Neues lokales Git-Repository initialisieren |
| `git status` | Status der Dateien prüfen |
| `git add .` | Alle geänderten Dateien stagen |
| `git commit -m "New Commit"` | Änderungen mit Nachricht speichern |
| `git branch -M main` | Hauptbranch in main umbenennen |
| `git push -u origin main` | Code auf GitHub hochladen |

---

## 5 Änderungen mit einem Klick pushen

```bash
git add .
git commit -m "Update File"
git branch -M main
git push -u origin main
```

---

## 6 Gelöschte Dateien verwalten

> [!WARNING]
> **Nutzen Sie Force Push (`git push -f`) mit Vorsicht!**

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git add -A` | Alle Änderungen inklusive Löschungen stagen |
| `git commit -m "Updated file structure"` | Löschung committen |
| `git push -f origin main` | Aktualisierung erzwingen |

---

## 7 Neuesten Code abrufen (Pull)

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git pull origin main` | Neuesten Code vom main-Branch abrufen |
| `git pull` | Vom verfolgten Branch aktualisieren |
| `git pull origin main --rebase` | Saubere Historie beim Pull behalten |
| `git push origin main` | Lokale Änderungen hochladen |

---

## 8 Lokalen Code auf GitHub-Stand zurücksetzen

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git fetch origin` | Neueste Daten vom Server abrufen |
| `git reset --hard origin/main` | Lokalen Stand exakt an GitHub angleichen |

---

## 9 Lange Dateipfade in Windows aktivieren

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git config --system core.longpaths true` | Lange Pfade unter Windows aktivieren |

---

## 10 Ordner umbenennen und Dateien aktualisieren

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git add -A` | Umbenennungen stagen |
| `git commit -m "Folder renamed and updated"` | Änderungen committen |
| `git push origin main` | Hochladen |

---

## 11 .vscode Ordner aus dem Tracking entfernen

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git rm -r --cached .vscode` | `.vscode` aus dem Tracking entfernen |
| `git commit -m "Remove .vscode folder"` | Löschung committen |
| `git push` | Auf GitHub aktualisieren |

---

## 12 Git-Repository zurücksetzen

| Befehl / Shell | Erklärung auf Deutsch |
|---------|-------------|
| `rm -rf .git` (Git Bash / Linux / Mac) | Ordner `.git` vollständig löschen |
| `Remove-Item -Recurse -Force .git` (PowerShell) | Ordner in PowerShell löschen |

---

## 13 Feature-Branch Push Workflow

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git pull origin main` | Neueste Updates abrufen |
| `git checkout -b feature-yourName` | Neuen Branch erstellen und wechseln |
| `git add .` | Änderungen stagen |
| `git commit -m "Your-commit"` | Committen |
| `git push origin feature-yourName` | Branch auf GitHub pushen |

---

## 14 Feature-Branch in Main mergen

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git checkout main` | Zum Hauptbranch wechseln |
| `git pull origin main` | Hauptbranch aktualisieren |
| `git fetch origin` | Alle Branches abrufen |
| `git merge origin/feature-yourName` | Feature-Branch zusammenführen |
| `git push origin main` | Aktualisierten Main-Branch pushen |

---

## 15 Branch-Verwaltung

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git branch` | Lokale Branches auflisten |
| `git branch -a` | Alle Branches (lokal & remote) auflisten |
| `git branch new-branch` | Neuen Branch erstellen |
| `git checkout new-branch` | Branch wechseln |
| `git checkout -b new-branch` | Erstellen und wechseln |
| `git merge new-branch` | Branch zusammenführen |
| `git branch -d new-branch` | Lokalen Branch sicher löschen |
| `git branch -D new-branch` | Erzwungen löschen |
| `git push origin --delete branch-name` | Remote-Branch auf GitHub löschen |

---

## 16 Historie und Logs prüfen

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git log` | Commit-Historie anzeigen |
| `git log --oneline` | Kompakte Historie in einer Zeile |
| `git diff` | Nicht gestagte Änderungen anzeigen |
| `git diff --staged` | Gestagte Änderungen anzeigen |
| `git show` | Details des letzten Commits anzeigen |

---

## 17 Fehler rückgängig machen und korrigieren

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git restore file.txt` | Datei auf letzten Stand zurücksetzen |
| `git reset HEAD file.txt` | Datei entstagen |
| `git commit --amend` | Letzte Commit-Nachricht ändern |
| `git reset --soft HEAD~1` | Commit rückgängig machen, Dateien gestagt lassen |
| `git reset --mixed HEAD~1` | Commit rückgängig machen und entstagen |
| `git reset --hard HEAD~1` | Letzten Commit und alle Änderungen verwürfen |
| `git revert <commit-hash>` | Commit durch Gegen-Commit rückgängig machen |

---

## 18 Stash (Temporäres Speichern)

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git stash` | Unfertige Arbeiten temporär speichern |
| `git stash save "message"` | Mit Nachricht speichern |
| `git stash pop` | Letzten Stash anwenden und löschen |
| `git stash apply` | Stash anwenden ohne zu löschen |
| `git stash list` | Alle Stashes auflisten |

---

## 19 Repository klonen

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git clone https://github.com/username/repo.git` | Repository herunterladen |
| `git clone <repo-link> .` | In aktuellen Ordner klonen |

---

## 20 .gitignore Einrichten

| Beispiel | Erklärung auf Deutsch |
|---------|-------------|
| `.gitignore` erstellen | Dateien vom Git-Tracking ausschließen |
| `.vscode/` | VS Code Einstellungen ignorieren |
| `node_modules/` | NPM-Pakete ignorieren |
| `.env` | Passwörter und Keys ignorieren |

---

## 21 Remote-Verwaltung

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git remote -v` | Remote-URLs anzeigen |
| `git remote add origin <url>` | Remote hinzufügen |
| `git remote set-url origin <new-url>` | Remote-URL ändern |

---

## 22 Tagging (Versionskontrolle)

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git tag v1.0` | Leichtgewichtigen Tag erstellen |
| `git tag -a v1.0 -m "Release v1.0"` | Tag mit Nachricht erstellen |
| `git push origin v1.0` | Tag auf GitHub pushen |

---

## 23 Moderne Git-Navigation (switch & restore)

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git switch <branch-name>` | Branch wechseln |
| `git switch -c <new-branch>` | Branch erstellen und wechseln |
| `git restore <file>` | Änderungen in Arbeitsverzeichnis verwerfen |

---

## 24 Merge-Konflikte lösen

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git status` | Konfliktbehaftete Dateien sehen |
| Dateien bearbeiten | Gewünschten Code zwischen `<<<<<<<` und `>>>>>>>` behalten |
| `git add <resolved-file>` | Konflikt als gelöst markieren |
| `git merge --abort` | Abgebrochenen Merge abbrechen |

---

## 25 Git Reflog – Verlorenen Code wiederherstellen

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git reflog` | Sicherheits-Logbuch aller Aktionen sehen |
| `git reset --hard HEAD@{n}` | Exakt zum Stand n zurückkehren |

---

## 26 Erweiterte Historie und Zeilen-Tracking

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git log --graph --oneline --all` | Visuellen Branch-Baum anzeigen |
| `git blame <file>` | Zeige wer wann welche Zeile geändert hat |

---

## 27 Cherry-Pick und Interaktives Rebase

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git cherry-pick <commit-hash>` | Einzelnen Commit übernehmen |

---

## 28 Unverfolgte Dateien bereinigen

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git clean -fd` | Nicht verfolgte Dateien und Ordner löschen |

---

## 29 GitHub CLI (gh) Befehle

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `gh auth login` | Im Terminal einloggen |
| `gh repo create` | Repository im Terminal erstellen |
| `gh pr create` | Pull Request erstellen |

---

## 30 Git Submodule

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git submodule add <repo-url> <path>` | Submodul hinzufügen |

---

## 31 Git Shortcuts (Aliases)

| Befehl | Erklärung auf Deutsch |
|---------|-------------|
| `git config --global alias.st status` | Shortcut `git st` erstellen |

---

## 🚀 Pro-Tipps

- **Führen Sie immer `git pull` aus**, bevor Sie neuen Code schreiben.
- **Verwenden Sie `git reflog`**, wenn Sie glauben, Code verloren zu haben!
