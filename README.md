# MyTrade — US Stock Fair Value Analysis

## Deploy to Vercel (recommended)

1. Push this repo to GitHub
2. Go to [vercel.com](https://vercel.com) → Import your repo
3. Click **Deploy** — no env variables needed, Yahoo Finance is free
4. Done! Your app will be live at `https://your-project.vercel.app`

---

## Run locally

```bash
npm install
node server.js
```

Then open: `http://localhost:3000`

No API key needed — uses Yahoo Finance for free.

---

## Project structure

```
mytrade/
├── api/
│   └── fmp.js        ← Vercel serverless function (Yahoo Finance)
├── index.html        ← Frontend app
├── server.js         ← Local dev server (Yahoo Finance)
├── vercel.json       ← Routes /fmp → /api/fmp
├── package.json
└── .gitignore
```

## How it works

- **Locally**: `server.js` runs an Express server on port 3000
- **On Vercel**: `api/fmp.js` runs as a serverless function, same Yahoo Finance logic
- `vercel.json` rewrites `/fmp` → `/api/fmp` so the frontend code works identically in both environments — no changes needed to `index.html`
