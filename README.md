# 🚫 Tomcat Static Cache OFF Guide
**Disable all browser caching for HTML, CSS, JS, and images using only `web.xml`.**

---

## 📌 Overview
If your HTML or static files (JS, CSS, images) aren’t updating after deployment, the browser is likely serving old cached content. This guide shows you how to **completely disable caching in Tomcat** using the built-in `ExpiresFilter`—no Java code required.


## 🚨 Problem  
Even after updating static files, the website still shows old content because the user’s browser retains cached files.


## ✅ Solution  
Use Tomcat’s built-in `ExpiresFilter` to force the browser to always fetch fresh files from the server.

✔ Works for HTML, JS, CSS, images  
✔ Requires **no Java code**  
✔ Requires only `web.xml`  
✔ No need for versioned URLs  
✔ `<meta>` tags not required  


## 📦 What This Configuration Does
- 🚫 Forces the browser to **never cache any file**
- 🔄 Ensures **HTML, JS, CSS, images** are always fetched from the server
- 🧹 Disables caching **even without `<meta>` tags**
- 🆕 Guarantees that the **latest version** of every file is delivered
- 🛠 Prevents outdated content from appearing after deployment


## 🚀 How to Test After Deployment
🔍 Chrome DevTools  
1. Press **F12**
2. Open the **Network** tab  
3. Check **Disable cache**
4. Refresh the page (**F5**)

If these headers appear, caching is **fully disabled** 🎉

```yaml
Cache-Control: no-cache, no-store, must-revalidate
Pragma: no-cache
Expires: 0
```

---

## 📄 License

This project is licensed under the **MIT License**. @yhsang2
