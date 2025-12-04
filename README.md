How to Completely Disable Tomcat Caching

Are your static files (HTML, JS, images) not updating even after deployment?
This often happens because the user's browser still holds cached files — but don't worry, Tomcat can fix that.

🔥 Problem

You're working on an HTML-based project, but updates to your HTML or static assets (HTML, JS, image files) are not reflected.
The culprit: client-side browser cache.

🔥 Solution

Use Tomcat’s built-in ExpiresFilter to force-disable all caching.
With just a web.xml configuration (no Java code needed), you can disable caching for all static resources — HTML, CSS, JS, and images — instantly.

🔥 What This web.xml Configuration Does

✔ Forces the browser to re-fetch every file from the server
✔ Blocks caching entirely — even without <meta> cache tags
✔ Works with zero Java code (uses Tomcat’s native filter)
✔ Always delivers the latest files — no need to append version strings to URLs

🚀 How to Test After Deployment

Open Chrome DevTools (F12)

Go to the Network tab

Check Disable cache

Reload the page (F5)

If you see headers like these, the configuration is working:

Cache-Control: no-cache, no-store, must-revalidate
Pragma: no-cache
Expires: 0
