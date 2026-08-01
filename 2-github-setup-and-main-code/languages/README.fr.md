<h2 align="center">Configuration GitHub & Code Principal – Guide Maître Complet (Français)</h2>

<p align="center">
Ce document est un <b>guide de référence complet sur les commandes Git et GitHub</b> pour connecter vos projets locaux, pousser les mises à jour, gérer les branches et résoudre les conflits.
</p>

<div align="center">

### 🌐 Sélectionner la langue / Select Language:
[**🇺🇸 English**](../README.md) &nbsp;|&nbsp; [**🇧🇩 বাংলা**](README.bn.md) &nbsp;|&nbsp; [**🇪🇸 Español**](README.es.md) &nbsp;|&nbsp; [**🇮🇳 हिन्दी**](README.hi.md) &nbsp;|&nbsp; [**🇫🇷 Français**](README.fr.md) &nbsp;|&nbsp; [**🇩🇪 Deutsch**](README.de.md) &nbsp;|&nbsp; [**🇨🇳 中文**](README.zh.md) &nbsp;|&nbsp; [**🇸🇦 العربية**](README.ar.md)

</div>

---

## 📌 Table des Matières (Français)

1. [Configuration de Git](#1-configuration-de-git)
2. [Jeton d'Accès Personnel GitHub (PAT)](#2-jeton-daccès-personnel-github-pat)  
   2.1 [Authentification par Clé SSH](#21-authentification-par-clé-ssh)
3. [Connecter le Dépôt Local à un Dépôt Distant](#3-connecter-le-dépôt-local-à-un-dépôt-distant)
4. [Flux de Travail Git de Base](#4-flux-de-travail-git-de-base)
5. [Publier les Modifications en un Clic](#5-publier-les-modifications-en-un-clic)
6. [Gérer les Fichiers Supprimés](#6-gérer-les-fichiers-supprimés)
7. [Mettre à Jour et Récupérer la Dernière Version](#7-mettre-à-jour-et-récupérer-la-dernière-version)
8. [Synchroniser avec GitHub](#8-synchroniser-avec-github)
9. [Activer les Chemins Longs dans Git](#9-activer-les-chemins-longs-dans-git)
10. [Renommer les Dossiers et Mettre à Jour les Fichiers](#10-renommer-les-dossiers-et-mettre-à-jour-les-fichiers)
11. [Retirer le Dossier .vscode du Suivi](#11-retirer-le-dossier-vscode-du-suivi)
12. [Réinitialiser le Dépôt Git](#12-réinitialiser-le-dépôt-git)
13. [Flux de Travail pour Branche de Fonctionnalité](#13-flux-de-travail-pour-branche-de-fonctionnalité)
14. [Fusionner une Branche dans la Branche Principale](#14-fusionner-une-branche-dans-la-branche-principale)
15. [Gestion des Branches](#15-gestion-des-branches)
16. [Consulter l'Historique et les Logs](#16-consulter-lhistorique-et-les-logs)
17. [Annuler et Corriger les Erreurs](#17-annuler-et-corriger-les-erreurs)
18. [Stash (Sauvegarde Temporaire)](#18-stash-sauvegarde-temporaire)
19. [Cloner un Dépôt](#19-cloner-un-dépôt)
20. [Configuration de .gitignore](#20-configuration-de-gitignore)
21. [Gestion des Dépôts Distants](#21-gestion-des-dépôts-distants)
22. [Gestion des Versions par Tags](#22-gestion-des-versions-par-tags)
23. [Navigation Moderne avec Git (switch & restore)](#23-navigation-moderne-avec-git-switch--restore)
24. [Résolution des Conflits de Fusion](#24-résolution-des-conflits-de-fusion)
25. [Git Reflog – Récupérer du Code Perdu](#25-git-reflog--récupérer-du-code-perdu)
26. [Historique Avancé et Suivi des Lignes](#26-historique-avancé-et-suivi-des-lignes)
27. [Cherry-Pick et Rebase Interactif](#27-cherry-pick-et-rebase-interactif)
28. [Nettoyer les Fichiers Non Suivis](#28-nettoyer-les-fichiers-non-suivis)
29. [Commandes GitHub CLI (gh)](#29-commandes-github-cli-gh)
30. [Sous-modules Git](#30-sous-modules-git)
31. [Raccourcis Git (Aliases)](#31-raccourcis-git-aliases)

---

## 1 Configuration de Git

| Commande | Explication en Français |
|---------|-------------|
| `git config --global user.name "your-username"` | Définir le nom d'utilisateur global |
| `git config --global user.email "abc@gmil.com"` | Définir l'adresse email globale |
| `git config --list` | Afficher toute la configuration Git |

---

## 2 Jeton d'Accès Personnel GitHub (PAT)

| Étape | Explication en Français |
|------|-------------|
| **Settings → Developer settings → Personal access tokens** | Naviguer pour générer un jeton d'accès |
| Permissions | Sélectionner repo, notes, admin:org |
| Exemple de jeton | `ghp_yourPersonalAccessTokenHere...` |

---

### 2.1 Authentification par Clé SSH

| Commande | Explication en Français |
|---------|-------------|
| `ssh-keygen -t ed25519 -C "your_email@example.com"` | Générer une paire de clés SSH sécurisées |
| `eval "$(ssh-agent -s)"` | Démarrer l'agent SSH dans le terminal |
| `ssh-add ~/.ssh/id_ed25519` | Ajouter la clé privée à l'agent |
| `cat ~/.ssh/id_ed25519.pub` | Afficher la clé publique (à copier sur GitHub) |
| `ssh -T git@github.com` | Tester la connexion avec GitHub |
| `git remote set-url origin git@github.com:username/repo.git` | Passer de HTTPS à SSH pour le dépôt distant |

---

## 3 Connecter le Dépôt Local à un Dépôt Distant

| Commande | Explication en Français |
|---------|-------------|
| `git remote add origin https://github.com/Shariar-Ahamed/<repo>` | Ajouter le dépôt distant GitHub |
| `git remote set-url origin https://<token>@github.com/Shariar-Ahamed/<repo>` | Définir l'URL avec le jeton PAT |

---

## 4 Flux de Travail Git de Base

| Commande | Explication en Français |
|---------|-------------|
| `git init` | Initialiser un nouveau dépôt Git local |
| `git status` | Vérifier l'état des fichiers |
| `git add .` | Indexer tous les fichiers modifiés |
| `git commit -m "New Commit"` | Enregistrer les modifications avec un message |
| `git branch -M main` | Nommer la branche principale "main" |
| `git push -u origin main` | Envoyer le code vers GitHub |

---

## 5 Publier les Modifications en un Clic

```bash
git add .
git commit -m "Update File"
git branch -M main
git push -u origin main
```

---

## 6 Gérer les Fichiers Supprimés

> [!WARNING]
> **Utilisez le Force Push (`git push -f`) avec précaution !** Cela écrase l'historique distant.

| Commande | Explication en Français |
|---------|-------------|
| `git add -A` | Indexer tous les changements (y compris les suppressions) |
| `git commit -m "Updated file structure"` | Valider la suppression des fichiers |
| `git push -f origin main` | Forcer la mise à jour sur GitHub |

---

## 7 Mettre à Jour et Récupérer la Dernière Version

| Commande | Explication en Français |
|---------|-------------|
| `git pull origin main` | Récupérer le dernier code depuis la branche main distante |
| `git pull` | Mettre à jour depuis la branche suivie |
| `git pull origin main --rebase` | Récupérer les modifications en gardant un historique propre |
| `git push origin main` | Envoyer les modifications locales |

---

## 8 Synchroniser avec GitHub

| Commande | Explication en Français |
|---------|-------------|
| `git fetch origin` | Récupérer les données du dépôt distant |
| `git reset --hard origin/main` | Aligner exactement le dépôt local sur GitHub |

---

## 9 Activer les Chemins Longs dans Git

| Commande | Explication en Français |
|---------|-------------|
| `git config --system core.longpaths true` | Activer le support des chemins longs sous Windows |

---

## 10 Renombrar Carpetas y Actualizar Archivos

| Commande | Explication en Français |
|---------|-------------|
| Renommer les dossiers et fichiers | Modifications manuelles du projet |
| `git add -A` | Indexer tous les remplacements et ajouts |
| `git commit -m "Folder renamed and updated"` | Valider les changements |
| `git push origin main` | Envoyer vers GitHub |

---

## 11 Retirer le Dossier .vscode du Suivi

| Commande | Explication en Français |
|---------|-------------|
| `git rm -r --cached .vscode` | Retirer `.vscode` de l'index de suivi |
| `git commit -m "Remove .vscode folder"` | Valider la suppression |
| `git push` | Mettre à jour GitHub |

---

## 12 Réinitialiser le Dépôt Git

| Commande / Shell | Explication en Français |
|---------|-------------|
| `rm -rf .git` (Git Bash / Linux / Mac) | Supprimer le dossier `.git` et tout l'historique |
| `Remove-Item -Recurse -Force .git` (PowerShell) | Supprimer le dossier sous Windows PowerShell |

---

## 13 Flux de Travail pour Branche de Fonctionnalité

| Commande | Explication en Français |
|---------|-------------|
| `git pull origin main` | Récupérer les dernières mises à jour |
| `git checkout -b feature-yourName` | Créer et basculer sur une nouvelle branche |
| `git add .` | Indexer les modifications |
| `git commit -m "Your-commit"` | Enregistrer les changements |
| `git push origin feature-yourName` | Envoyer la branche sur GitHub |

---

## 14 Fusionner une Branche dans la Branche Principale

| Commande | Explication en Français |
|---------|-------------|
| `git checkout main` | Revenir sur la branche principale |
| `git pull origin main` | Mettre à jour la branche principale |
| `git fetch origin` | Récupérer toutes les branches |
| `git merge origin/feature-yourName` | Fusionner la branche de fonctionnalité |
| `git push origin main` | Envoyer la branche principale mise à jour |

---

## 15 Gestion des Branches

| Commande | Explication en Français |
|---------|-------------|
| `git branch` | Lister les branches locales |
| `git branch -a` | Lister toutes les branches (locales et distantes) |
| `git branch new-branch` | Créer une nouvelle branche |
| `git checkout new-branch` | Basculer sur une autre branche |
| `git checkout -b new-branch` | Créer et basculer sur la nouvelle branche |
| `git merge new-branch` | Fusionner une branche dans la branche courante |
| `git branch -d new-branch` | Supprimer une branche locale en toute sécurité |
| `git branch -D new-branch` | Forcer la suppression d'une branche non fusionnée |
| `git push origin --delete branch-name` | Supprimer une branche distante sur GitHub |

---

## 16 Consulter l'Historique et les Logs

| Commande | Explication en Français |
|---------|-------------|
| `git log` | Afficher l'historique des commits |
| `git log --oneline` | Afficher l'historique de manière condensée |
| `git diff` | Afficher les modifications non indexées |
| `git diff --staged` | Afficher les modifications indexées |
| `git show` | Afficher les détails du dernier commit |
| `git show <commit-hash>` | Afficher les détails d'un commit spécifique |

---

## 17 Annuler et Corriger les Erreurs

| Commande | Explication en Français |
|---------|-------------|
| `git restore file.txt` | Annuler les modifications d'un fichier |
| `git reset HEAD file.txt` | Désindexer un fichier |
| `git commit --amend` | Modifier le dernier message de commit |
| `git reset --soft HEAD~1` | Annuler le commit mais garder les fichiers indexés |
| `git reset --mixed HEAD~1` | Annuler le commit et désindexer les fichiers |
| `git reset --hard HEAD~1` | Annuler le dernier commit et supprimer tous les changements |
| `git revert <commit-hash>` | Inverser un commit en créant un nouveau commit |

---

## 18 Stash (Sauvegarde Temporaire)

| Commande | Explication en Français |
|---------|-------------|
| `git stash` | Sauvegarder temporairement les modifications en cours |
| `git stash save "message"` | Sauvegarder avec un message descriptif |
| `git stash pop` | Appliquer et supprimer la dernière sauvegarde |
| `git stash apply` | Appliquer la sauvegarde sans la supprimer |
| `git stash list` | Lister toutes les sauvegardes |
| `git stash drop` | Supprimer une sauvegarde |
| `git stash clear` | Effacer toutes les sauvegardes |

---

## 19 Cloner un Dépôt

| Commande | Explication en Français |
|---------|-------------|
| `git clone https://github.com/username/repo.git` | Cloner un dépôt depuis GitHub |
| `git clone <repo-link> .` | Cloner dans le dossier courant |
| `git clone -b <branch-name> <repo-link>` | Cloner une branche spécifique |

---

## 20 Configuration de .gitignore

| Mot-clé | Explication en Français |
|---------|-------------|
| Fichier `.gitignore` | Fichier spécifiant les éléments à ignorer par Git |
| `.vscode/` | Ignorer la configuration de VS Code |
| `node_modules/` | Ignorer le dossier des dépendances NPM |
| `.env` | Ignorer les variables d'environnement confidentielles |
| `*.log` | Ignorer tous les fichiers de journal (logs) |

---

## 21 Gestion des Dépôts Distants

| Commande | Explication en Français |
|---------|-------------|
| `git remote -v` | Afficher les URL des dépôts distants |
| `git remote add origin <url>` | Ajouter un nouveau dépôt distant |
| `git remote remove origin` | Supprimer le dépôt distant |
| `git remote set-url origin <new-url>` | Modifier l'URL du dépôt distant |

---

## 22 Gestion des Versions par Tags

| Commande | Explication en Français |
|---------|-------------|
| `git tag v1.0` | Créer un tag de version léger |
| `git tag -a v1.0 -m "Release v1.0"` | Créer un tag annoté avec un message |
| `git tag` | Lister tous les tags |
| `git push origin v1.0` | Envoyer un tag sur GitHub |
| `git push origin --tags` | Envoyer tous les tags |

---

## 23 Navigation Moderne avec Git (switch & restore)

| Commande | Explication en Français |
|---------|-------------|
| `git switch <branch-name>` | Basculer vers une autre branche |
| `git switch -c <new-branch>` | Créer et basculer vers la nouvelle branche |
| `git restore <file>` | Annuler les modifications de la copie de travail |
| `git restore --staged <file>` | Désindexer un fichier |

---

## 24 Résolution des Conflits de Fusion

| Commande | Explication en Français |
|---------|-------------|
| `git status` | Voir la liste des fichiers en conflit |
| Éditer les fichiers | Conserver le code souhaité entre `<<<<<<<` et `>>>>>>>` |
| `git add <resolved-file>` | Marquer le conflit comme résolu |
| `git commit -m "Resolved merge conflict"` | Finaliser la fusion |
| `git merge --abort` | Annuler la fusion bloquée |

---

## 25 Git Reflog – Récupérer du Code Perdu

| Commande | Explication en Français |
|---------|-------------|
| `git reflog` | Consulter l'historique complet des actions HEAD |
| `git reset --hard HEAD@{n}` | Restaurer l'état exact au point n du reflog |
| `git branch <recovered-branch> <commit-hash>` | Recréer une branche supprimée |

---

## 26 Historique Avancé et Suivi des Lignes

| Commande | Explication en Français |
|---------|-------------|
| `git log --graph --oneline --all` | Afficher un arbre visuel des branches |
| `git blame <file>` | Voir qui a modifié chaque ligne d'un fichier et quand |

---

## 27 Cherry-Pick et Rebase Interactif

| Commande | Explication en Français |
|---------|-------------|
| `git cherry-pick <commit-hash>` | Appliquer un commit spécifique d'une autre branche |
| `git rebase main` | Rebaser la branche courante sur main |

---

## 28 Nettoyer les Fichiers Non Suivis

| Commande | Explication en Français |
|---------|-------------|
| `git clean -fd` | Supprimer les fichiers et dossiers non suivis |

---

## 29 Commandes GitHub CLI (gh)

| Commande | Explication en Français |
|---------|-------------|
| `gh auth login` | S'authentifier auprès de GitHub |
| `gh repo create <name> --public` | Créer un dépôt public depuis le terminal |
| `gh pr create` | Créer une Pull Request |
| `gh pr merge <pr-number>` | Fusionner une Pull Request |

---

## 30 Sous-modules Git

| Commande | Explication en Français |
|---------|-------------|
| `git submodule add <repo-url> <path>` | Ajouter un sous-module au projet |
| `git submodule update --init --recursive` | Initialiser et mettre à jour les sous-modules |

---

## 31 Raccourcis Git (Aliases)

| Commande | Explication en Français |
|---------|-------------|
| `git config --global alias.st status` | Créer le raccourci `git st` |
| `git config --global alias.co checkout` | Créer le raccourci `git co` |

---

## 🚀 Conseils de Pro (Pro Tips)

- **Exécutez toujours `git pull`** avant de commencer une nouvelle tâche.
- **Rédigez des messages de commit clairs** (`fix: navbar bug`).
- **Utilisez `git reflog`** si vous pensez avoir perdu du code !
