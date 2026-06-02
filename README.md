# Lock In — Your Personal Version

A free, self-hosted habit tracker / OVR leveling system. Inspired by Lock In but with zero subscription, zero ads, zero data collection. All data stays on your device (localStorage).

## What it does
- **Habits + XP/OVR** — Tick off daily habits, earn XP, level up your OVR (60 → 99) through Bronze → Silver → Gold → Platinum → Diamond → Opal → Legend
- **Goals** — Track progress toward big targets (e.g. M4 deposit fund). Hitting target = +100 XP
- **Streaks + heatmap** — 14-week activity grid like GitHub contributions
- **Journal** — Daily entries (+15 XP each)
- **Breathing** — 4-7-8 breathing tool (tap circle)
- **Daily quote** — Rotates through 10 motivational quotes
- **Tag filters** — Gym / Health / Focus / Mind / Money
- **PWA** — Install to home screen, works offline

## Run locally on your phone (testing)
1. Open Terminal on Mac (or any computer on same WiFi)
2. `cd` into this folder
3. Run: `python3 -m http.server 8080`
4. On your phone, open `http://YOUR_COMPUTER_IP:8080`
5. Safari → Share → Add to Home Screen

## Deploy to web (free, like Simply Fit AI)

### Option A: Vercel (you already use this — easiest)
1. Push this folder to a new GitHub repo (e.g. `lockin-personal`)
2. Go to vercel.com → New Project → Import the repo
3. Framework: "Other" (it's just static HTML)
4. Deploy — done in 30 seconds. Free domain like `lockin-xyz.vercel.app`
5. Want a custom domain? Buy from Namecheap (~$10/yr), point to Vercel

### Option B: Netlify drag-and-drop
1. Go to app.netlify.com/drop
2. Drag this entire folder onto the page
3. Done — instant URL

### Option C: GitHub Pages (100% free, no signup beyond GitHub)
1. Push to GitHub repo
2. Settings → Pages → Source: main branch
3. Live at `yourusername.github.io/reponame`

## After deploying
On your phone:
1. Open the URL in Safari
2. Share button → **Add to Home Screen**
3. Now it looks and feels like a real app — fullscreen, no browser bars, offline-ready

## Customise it
Open `index.html` — everything is one file:
- **Default habits**: Search for `name: "Gym session"` → edit the starter habits
- **XP values**: Search for `xp: 20` → change reward sizes
- **Tier names**: Search for `const TIERS` → rename Bronze/Silver/etc. to whatever
- **Quotes**: Search for `const QUOTES` → add your own
- **Tag categories**: Search for `data-tag="gym"` → add/rename tags
- **Colours**: All gradients use `#6366f1` (indigo) and `#a855f7` (purple) — find/replace to your brand

## Why this saves you $40-50/year
The original Lock In is a static-data app — all the "AI coach" stuff aside, the core (habits, XP, streaks, goals, journal) is just localStorage + a leveling formula. No backend needed. Hosting is free on Vercel/Netlify forever.

## Data
Everything is stored in your browser's localStorage. To back up:
- Open browser DevTools → Application → Local Storage → copy `lockin_state` value
- To migrate to a new phone, paste it back into the same key

## Want the AI coach feature?
You already have a Claude API key (from Simply Fit AI). Add a button that pings the API with the user's recent journal entries + habit completions and asks for personalised feedback. Same architecture as Simply Fit AI — should take ~30 min to add.
