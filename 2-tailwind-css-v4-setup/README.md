# Tailwind CSS v4 Setup – Using PostCSS & Vite

This guide explains how to **set up Tailwind CSS Version 4 from scratch** using **PostCSS and Vite**.  
Left column = command / file, Right column = explanation.

---

## 01 Prerequisites

| Requirement | Explanation |
|------------|-------------|
| **Node.js** | Required to run Tailwind, npm, and Vite |
| Download Link | https://nodejs.org/en |
| `node -v` | Check Node.js version |
| Example Version | v22.14.0 |

---

## 02 PowerShell Execution Policy

| Command | Explanation |
|--------|-------------|
| `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser -Force` | Allows npm scripts to run properly in PowerShell |

---

## 03 Initialize npm Project

| Command | Explanation |
|--------|-------------|
| `npm init -y` | Automatically creates `package.json` file |

---

## 04 Install Tailwind CSS v4 & PostCSS

| Command | Explanation |
|--------|-------------|
| `npm install tailwindcss @tailwindcss/postcss postcss` | Installs Tailwind CSS v4 with PostCSS support |

Official Docs:  
https://tailwindcss.com/docs/installation/using-postcss

---

## 05 PostCSS Configuration

📄 **Create file:** `postcss.config.mjs`

```besh
export default {
  plugins: {
    "@tailwindcss/postcss": {},
  }
}
```
| Purpose        | Explanation                      |
| -------------- | -------------------------------- |
| PostCSS config | Enables Tailwind CSS via PostCSS |

---

## 06 Style CSS Setup: 
📄 **Create file:** `style.css`

`@import "tailwindcss";`

| Purpose         | Explanation               |
| --------------- | ------------------------- |
| Import Tailwind | Loads Tailwind CSS styles |

---

## 07 Vite Installation & Check
| Command            | Explanation                        |
| ------------------ | ---------------------------------- |
| `npm list vite`    | Check if Vite is already installed |
| `npm install vite` | Install Vite locally               |
| `npx vite`         | Run Vite once without installing   |

---

## 08 Update package.json
📄 **Modify file:** `package.json`
```besh
"scripts": {
  "dev": "vite",
  "test": "echo \"Error: no test specified\" && exit 1"
},
```
| Purpose    | Explanation                   |
| ---------- | ----------------------------- |
| dev script | Runs local development server |


---

## 09 HTML Setup
📄 **Create file:** `index.html`
```bash
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <!-- Using PostCSS -->
    <link href="styles.css" rel="stylesheet" />

    <!-- Tailwind Play CDN (Optional) -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>

    <!-- Local Tailwind CSS -->
    <link rel="stylesheet" href="style.css" />
  </head>

  <body>
    <h1 class="text-3xl font-bold underline">Hello world!</h1>
  </body>
</html>
```
| Purpose   | Explanation                     |
| --------- | ------------------------------- |
| HTML base | Entry file for Tailwind testing |
| CDN       | Optional quick Tailwind testing |
| style.css | Loads Tailwind styles           |


---

## 10 Run Development Server
| Command       | Explanation                         |
| ------------- | ----------------------------------- |
| `npm run dev` | Start Vite local development server |


---

## 11 Clear Cache & Quick Check
| Command               | Explanation                  |
| --------------------- | ---------------------------- |
| `npx clear-npx-cache` | Clear cached npx data        |
| `dir`                 | Show current directory files |


---

## 📚 Reference
- Tailwind CSS Docs: https://tailwindcss.com/docs/installation/using-postcss
- Node.js: https://nodejs.org/en


---