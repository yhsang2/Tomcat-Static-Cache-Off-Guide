🚫 Tomcat Static Cache OFF Guide

Disable all browser caching for HTML, CSS, JS, and images using only web.xml.

📌 Overview

If your HTML or static files (JS, CSS, images) aren’t updating after deployment, the browser is likely serving old cached content.
This guide shows you how to completely disable caching in Tomcat using the built-in ExpiresFilter—no Java code required.

🚨 Problem

Even after updating static files, the website still shows old content because the user’s browser retains cached files.

✅ Solution

Use Tomcat’s built-in ExpiresFilter to force the browser to always fetch fresh files from the server.

✔ Works for HTML, JS, CSS, images
✔ Requires no Java code
✔ Requires only web.xml
✔ No need for versioned URLs
✔ <meta> tags not required

🛠 Configuration (web.xml)
<filter>
    <filter-name>ExpiresFilter</filter-name>
    <filter-class>org.apache.catalina.filters.ExpiresFilter</filter-class>
</filter>

<filter-mapping>
    <filter-name>ExpiresFilter</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>

<context-param>
    <param-name>ExpiresFilter.DisableCache</param-name>
    <param-value>true</param-value>
</context-param>

<filter>
    <filter-name>NoCacheFilter</filter-name>
    <filter-class>org.apache.catalina.filters.AddDefaultCharsetFilter</filter-class>
</filter>

<filter-mapping>
    <filter-name>NoCacheFilter</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>

📦 What This Configuration Does

Forces the browser to never cache any file

Ensures HTML, JS, CSS, images are always fetched from the server

Blocks cache even without <meta> tags

Ensures the latest version of every file is delivered

Prevents old content issues after deployment

🚀 How to Test After Deployment
Chrome DevTools

Press F12

Go to Network tab

Check Disable cache

Refresh (F5)

You should now see these headers:

Cache-Control: no-cache, no-store, must-revalidate
Pragma: no-cache
Expires: 0


If these appear → Caching is fully disabled 🎉

📄 License

MIT License (or specify your own)

🙌 Contributing

Pull requests are welcome!
If you'd like to improve this guide or add examples, feel free to open an issue.

💬 Need Help?

If you'd like help customizing this configuration for your environment, feel free to ask!
