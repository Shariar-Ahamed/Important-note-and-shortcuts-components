# 🚀 Vite Project Deploy Using Surge
Deploy your Vite / React production build easily using Surge.sh — a super simple static hosting platform.

---

### 📌 Official Links
- 🔗 Vite Static Deploy Guide: https://vite.dev/guide/static-deploy#surge
- 🔗 Surge NPM Package: https://www.npmjs.com/package/surge

---

## ⚙️ Step-by-Step Deployment Process

---

### 🥇 Step 1: Install Surge Globally
```bash
npm install -g surge
```
> Install once globally. No need to install again for future projects.

### ❌🚨 Fix: `npm error code ENOENT`
If you see this error:
```bash
npm ERR! code ENOENT
npm ERR! syscall open
npm ERR! path package.json
```
### 📌 Reason
**You are not inside the project root folder.**

### ✅ 🛠 Solution:
Go to the folder where `package.json` exists:
```bash
cd my-vue-app
```
Then run the command again.

---

### 🥈 Step 2: Build the Project (Production Build)
```bash
npm run build
```
#### 📂 What Happens?
- Vite creates a `dist` folder
- This folder contains optimized production files
- This `dist` folder will be deployed

---

### 🥉 Step 3: Deploy to Surge
```bash
surge dist
```
#### 📝 During Deployment
You will be asked for:
- Email
- Password
- Domain name (auto-generated or custom)

Surge will generate something like:
```bash
random-name.surge.sh
```

---

### ❌ Error: Domain Permission Issue
```bash
Aborted - you do not have permission to publish to parsimonious-floor.surge.sh
```
#### 📌 Reason
**That domain is already taken.**

---

### ✅ Fix
Run again:
```bash
surge dist
```
> Surge will generate a new available domain.

---

### ✅ Successful Deployment Example
```bash
surge dist
```
Output:

- Project: dist
- Domain: zesty-pen.surge.sh
- Upload: 100%
- CDN: 100%
- Encryption: 100%


### 🎉 Final Live URLs:

```bash
https://zesty-pen.surge.sh
```
Now your Vite/React app is live 🚀

---

## 🌐 Custom Domain Setup (Using CNAME)

### 📁 Create This File:
```bash
my-vue-app/public/CNAME
```

### 📄 Inside CNAME File:
```bash
zesty-pen.surge.sh
```
Now Surge will use this domain during deployment.

---

### 🔁 Updating an Existing Deployment
**After making changes:**

```bash
npm run build
surge dist
```

*It will overwrite the existing deployed version.*

---