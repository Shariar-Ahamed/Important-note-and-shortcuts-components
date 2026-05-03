# React Installation with Vite (Windows)

This guide explains how to **install React using Vite** on Windows using  
**VS Code Terminal (PowerShell)** and **Command Prompt (CMD)**.  
It covers **default selection**, **manual selection**, and common warnings.

---

## 01 Prerequisites

| Requirement | Description |
|------------|-------------|
| Node.js | Required to run npm and Vite |
| Check Version | `node -v` |
| Package Manager | npm (comes with Node.js) |

---

## 02 React Install (VS Code Terminal – PowerShell)

### ▶️ Default Selection
```bash
npm create vite@latest my-vue-app -- --template react
```
### ▶️ Interactive Steps (Default Selection)
| Prompt                            | Selected Option |
| --------------------------------- | --------------- |
| Use rolldown-vite (Experimental)? | Yes             |
| Install with npm and start now?   | Yes             |

### ▶️ Output Summary
| Info               | Details                                        |
| ------------------ | ---------------------------------------------- |
| Packages Installed | ~160                                           |
| Dev Server         | Started automatically                          |
| Local URL          | [http://localhost:5173](http://localhost:5173) |

---

### ▶️ Manual Framework Selection (Recommended – New Way)
```bash
npm create vite@latest my-vue-app -- -- --template react
```
| Step          | Selection               |
| ------------- | ----------------------- |
| Framework     | React                   |
| Variant       | JavaScript / TypeScript |
| Rolldown Vite | Yes                     |
| Install now   | Yes                     |

✔ Cleaner and future-proof method  
✔ Avoids npm warning  

---

## 03 React Install (CMD)
### ▶️ Default Selection
```bash
npm create vite@latest my-vue-app -- --template react
```
| Step                   | Result                                         |
| ---------------------- | ---------------------------------------------- |
| Project Created        | Yes                                            |
| Dependencies Installed | Yes                                            |
| Dev Server             | Auto started                                   |
| URL                    | [http://localhost:5173](http://localhost:5173) |

---

### ▶️ Manual Selection (No Auto Start)
```bash
npm create vite@latest my-vue-app -- --template react 
```
When prompted:
- Rolldown-vite → **No**
- Install now → **No**

#### ▶️ Run Manually
```bash
cd my-vue-app
npm install
npm run dev
```
✔ Full control  
✔ Best for beginners to understand workflow  

---

## 04 Default vs Manual Selection
| Mode              | Best For            |
| ----------------- | ------------------- |
| Default Selection | Quick setup         |
| Manual Selection  | Learning & control  |
| Auto Install      | Fast start          |
| Manual Install    | Clean understanding |

---

## 05 Common Warnings Explained
### ⚠️ npm Warning
```bash
npm warn Unknown cli config "--template"
```

| Meaning          | Solution                 |
| ---------------- | ------------------------ |
| Old syntax used  | Use interactive mode     |
| Not breaking now | May break in future      |
| Safe fix         | `npm create vite@latest` |

✔ Recommended command going forward:  
```bash
npm create vite@latest
```

---

## 📝 Short Description
This folder documents **React installation using Vite on Windows**, covering
**VS Code Terminal and CMD**, with **default and manual setup flows.**
Ideal for beginners and for quick future reference

---
