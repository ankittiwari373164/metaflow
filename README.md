# MetaFlow — Social Scheduler

A single-file Meta Business Suite scheduler with Groq AI caption generation.

## Deploy to Vercel (via GitHub)

### Step 1 — Push to GitHub

1. Go to [github.com](https://github.com) → click **New repository**
2. Name it `metaflow` (or anything you like)
3. Set it to **Public** or **Private** — both work
4. Click **Create repository**
5. Upload these two files:
   - `index.html`
   - `vercel.json`

   **Easiest way:** On the new repo page, click **"uploading an existing file"** → drag both files in → click **Commit changes**

### Step 2 — Deploy on Vercel

1. Go to [vercel.com](https://vercel.com) → sign up / log in with GitHub
2. Click **Add New → Project**
3. Find and click **Import** next to your `metaflow` repo
4. Leave all settings as default (Framework = Other, Root directory = /)
5. Click **Deploy**
6. Wait ~30 seconds → your app is live at `https://metaflow-xxxx.vercel.app`

### Step 3 — Add your Vercel URL to Meta App

This is required for Meta OAuth to work on your live domain.

1. Go to [developers.facebook.com/apps](https://developers.facebook.com/apps) → click your app **"my ads"**
2. Go to **Facebook Login → Settings** (in the left sidebar)
3. Under **Valid OAuth Redirect URIs** → add your Vercel URL:
   ```
   https://your-project-name.vercel.app
   ```
4. Click **Save Changes**

### Step 4 — Use the live app

1. Open your Vercel URL
2. Go to **Settings → Groq AI** → paste your Groq API key → Save
3. Go to **Settings → Meta Business Suite** → paste your token → Fetch All My Pages
4. Start scheduling!

> **Note:** All your data (tokens, clients, posts) is saved in your browser's `localStorage`. It stays on your device and is not sent to any server.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The complete MetaFlow app (single file) |
| `vercel.json` | Vercel deployment configuration |

## Tech Stack

- Pure HTML/CSS/JS — no build step, no dependencies
- Groq API — AI caption generation (llama-3.1-8b-instant)
- Meta Graph API v19.0 — Facebook & Instagram scheduling
- localStorage — client-side data persistence
