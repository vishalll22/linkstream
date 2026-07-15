# Linkstream Frontend

The sleek, responsive frontend web application for **Linkstream** — Download any video, any quality.

## 📁 Project Overview
- `index.html`: Main application interface, design system, and client-side logic.
- `icons/`: PWA app icons.
- `manifest.json`: Web App Manifest for progressive web app (PWA) installation.
- `sw.js`: Service worker for offline caching and PWA support.

---

## 🚀 How to Connect with Your Render Backend

When running locally (`http://localhost:XXXX` or opening `index.html` directly), the app automatically connects to `http://localhost:8000`.

When deployed online (e.g., GitHub Pages, Vercel, Netlify), it defaults to `https://linkstream-backend.onrender.com`.

### To point the frontend to your own exact Render URL:
You have two simple options:

**Option 1: Edit `index.html` directly before deploying**
In `index.html` around line 493, replace `'https://linkstream-backend.onrender.com'` with your exact Render backend service URL:
```javascript
const API_BASE = localStorage.getItem('LINKSTREAM_API_BASE') || (
  window.location.hostname === 'localhost' || window.location.hostname === '127.0.0.1' || window.location.protocol === 'file:'
    ? 'http://localhost:8000'
    : 'https://YOUR-EXACT-RENDER-SERVICE.onrender.com'
);
```

**Option 2: Set dynamically via browser console**
If you or a tester wants to connect any deployed instance to a custom backend without modifying code, open the browser developer tools (F12) → Console and run:
```javascript
localStorage.setItem('LINKSTREAM_API_BASE', 'https://YOUR-EXACT-RENDER-SERVICE.onrender.com')
location.reload()
```

---

## 🌐 Deploying Frontend to GitHub Pages

1. Push this `linkstream` folder to your GitHub repository.
2. In your GitHub repository, go to **Settings** → **Pages**.
3. Under **Branch**, select `main` (and root `/` folder), then click **Save**.
4. Your site will be live within a minute!
