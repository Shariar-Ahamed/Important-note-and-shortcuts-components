# 🚀 Vite Project Deploy Using Surge

### 📌 Official Links
- 🔗 Vite Static Deploy Guide: https://vite.dev/guide/static-deploy#surge
- 🔗 Surge NPM Package: https://www.npmjs.com/package/surge

---

## ⚙️ Step-by-Step Deployment Process

### 🥇 Step 1: Install Surge Globally
```bash
npm install -g surge
```
> Surge CLI global install করতে হবে (একবারই যথেষ্ট)

### ❌🚨 Fixed `npm error code ENOENT` Error:
যদি এমন error দেখো:
```bash
npm ERR! code ENOENT
npm ERR! syscall open
npm ERR! path package.json
```
👉 এর মানে তুমি project root folder এ নেই  
👉 যেখানে package.json আছে সেখানে যেতে হবে  

### ✅ 🛠 Solution:

```bash
cd my-vue-app
```

---

### 🥈 Step 2: Build the Project
```bash
npm run build
```
> Vite project build করলে `dist` folder তৈরি হবে 
> এই folder-টাই deploy করতে হবে

---

### 🥉 Step 3: Deploy to Surge
```bash
surge dist
```
তারপর:
- Email দিতে হবে
- Password দিতে হবে
- Domain auto generate হবে (বা তুমি চাইলে custom দিতে পারো)

---

### ❌ যদি এমন Error আসে:
```bash
Aborted - you do not have permission to publish to parsimonious-floor.surge.sh
```
👉 মানে ঐ domain আগে কেউ use করেছে
👉 আবার `surge dist` চালাও
👉 নতুন domain auto-generate হবে

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


🎉 Final Live URLs:

- 🔍 Live Preview: 1770867316874-zesty-pen.surge.sh
- 🌍 Production: zesty-pen.surge.sh

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
> এতে custom domain bind করা যাবে
> অথবা existing surge domain fixed রাখা যাবে

---