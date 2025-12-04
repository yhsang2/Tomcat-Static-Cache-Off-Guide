# 🚫 Tomcat Static Cache OFF Guide  
**Disable all browser caching for HTML, CSS, JS, and images using only `web.xml`.**

---

## 📌 Overview  
If your HTML or static files (JS, CSS, images) aren’t updating after deployment, the browser is likely serving old cached content.  
This guide shows you how to **completely disable caching in Tomcat** using the built-in `ExpiresFilter`—no Java code required.

---

## 🚨 Problem  
Even after updating static files, the website still shows old content because the user’s browser retains cached files.

---

## ✅ Solution  
Use Tomcat’s built-in `ExpiresFilter` to force the browser to always fetch fresh files from the server.

✔ Works for HTML, JS, CSS, images  
✔ Requires **no Java code**  
✔ Requires only `web.xml`  
✔ No need for versioned URLs  
✔ `<meta>` tags not required  
