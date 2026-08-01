<h2 align="center">Configuración de GitHub y Código Principal – Guía Maestra Completa</h2>

<p align="center">
Este documento es una <b>guía de referencia completa de comandos de Git y GitHub</b> para conectar proyectos locales, publicar actualizaciones, gestionar ramas, resolver conflictos y dominar el flujo de trabajo.
</p>

<div align="center">

### 🌐 Seleccionar idioma / Select Language / ভাষা পরিবর্তন করুন:
[**🇺🇸 English**](../README.md) &nbsp;|&nbsp; [**🇧🇩 বাংলা (Bangla)**](README.bn.md) &nbsp;|&nbsp; [**🇪🇸 Español (Spanish)**](README.es.md)

</div>

---

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
13. [Flujo de Trabajo para Rama de Función](#13-flujo-de-trabajo-para-rama-de-función)
14. [Fusión de Rama de Función a Principal](#14-fusión-de-rama-de-función-a-principal)
15. [Gestión de Ramas](#15-gestión-de-ramas)
16. [Ver Historial y Registros (Logs)](#16-ver-historial-y-registros-logs)
17. [Deshacer y Corregir Errores](#17-deshacer-y-corregir-errores)
18. [Stash (Guardado Temporal)](#18-stash-guardado-temporal)
19. [Clonar Repositorio](#19-clonar-repositorio)
20. [Configuración de .gitignore](#20-configuración-de-gitignore)
21. [Gestión de Remotos](#21-gestión-de-remotos)
22. [Etiquetado (Control de Versiones)](#22-etiquetado-control-de-versiones)
23. [Navegación Moderna en Git](#23-navegación-moderna-en-git)
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

## 13 Flujo de Trabajo para Rama de Función

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

## 23 Navegación Moderna en Git

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

## 🚀 Consejos Profesionales (Pro Tips)

- **Ejecute siempre `git pull`** antes de empezar a trabajar para evitar conflictos.
- **Escriba mensajes de commit descriptivos** (ej. `fix: solve navbar toggle bug`).
- **Mantenga `.gitignore` actualizado** para no subir claves secretas o dependencias pesadas.
- **Utilice ramas de funciones** (`feature/navbar`) para trabajar en lugar de subir directo a `main`.
- **Use `git reflog`** si cree que perdió código: ¡Git casi nunca borra datos confirmados!
