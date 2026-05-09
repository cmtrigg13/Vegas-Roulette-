# Vegas Roulette — GitHub Pages Deployment Guide

## Files in this package
- index.html  — The complete app (all screens, game logic, sounds, haptics)
- sw.js        — Service worker (enables offline play & home screen install)
- manifest.json — PWA manifest (name, icon, display settings)
- DEPLOY.md   — This guide

---

## STEP 1 — Create a GitHub account (if you don't have one)
1. Go to https://github.com
2. Click "Sign up" — it's free
3. Verify your email

---

## STEP 2 — Create a new repository
1. Click the green "New" button (or go to https://github.com/new)
2. Repository name: vegas-roulette  (or any name you like)
3. Set to PUBLIC (required for free GitHub Pages)
4. Click "Create repository"

---

## STEP 3 — Upload your files
1. On your new repo page, click "uploading an existing file" link
2. Drag all 4 files into the upload area:
   - index.html
   - sw.js
   - manifest.json
   - DEPLOY.md (optional)
3. Scroll down, click "Commit changes"

---

## STEP 4 — Enable GitHub Pages
1. Click the "Settings" tab on your repo
2. Scroll down to "Pages" in the left sidebar
3. Under "Source", select "Deploy from a branch"
4. Branch: main  |  Folder: / (root)
5. Click Save
6. Wait 2–3 minutes

---

## STEP 5 — Your app is live!
Your URL will be:
  https://YOUR-USERNAME.github.io/vegas-roulette/

Share this link — it works on iPhone Safari!

---

## STEP 6 — Add to iPhone Home Screen
Tell your users:
1. Open the link in Safari (must be Safari, not Chrome)
2. Tap the Share button (box with arrow)
3. Scroll down and tap "Add to Home Screen"
4. Tap "Add"
The app icon appears on the home screen and opens full-screen like a native app.

---

## STEP 7 — App Icons (recommended)
Create two square PNG images with your roulette logo:
- icon-192.png  (192 x 192 pixels)
- icon-512.png  (512 x 512 pixels)

Free tool: https://www.canva.com (use their logo maker)
Upload them to your GitHub repo the same way as the other files.

---

## STEP 8 — Set Up Google AdSense
1. Go to https://adsense.google.com
2. Sign in with your Google account
3. Enter your GitHub Pages URL as your website
4. Submit tax info + bank account (required for payments)
5. Google reviews your site — takes 1–3 days
6. Once approved, you get a Publisher ID like: ca-pub-1234567890123456

---

## STEP 9 — Activate Ads in index.html
Once you have your Publisher ID:

Open index.html and find this comment near the top:
  <!-- <script async src="https://pagead2.googlesyndication.com/...

Remove the <!-- and --> comment tags.
Replace XXXXXXXXXXXXXXXX with your actual Publisher ID.

For the banner ad (bottom of game screen), find:
  <!-- ADSENSE BANNER — uncomment and replace Publisher ID
Remove the comment tags around the <ins> block.
Replace ca-pub-XXXXXXXXXXXXXXXX with your Publisher ID.
Replace the data-ad-slot value with your actual ad slot ID from AdSense.

Save and re-upload index.html to GitHub.

---

## STEP 10 — Custom Domain (optional, recommended)
A real domain looks more professional and helps AdSense approval.

1. Buy a domain at https://www.namecheap.com (~$12/year)
   Suggestions: vegasroulette.app, spinandwin.app, freeroulette.app

2. In GitHub repo Settings > Pages > Custom domain
   Enter your domain name and click Save

3. In Namecheap DNS settings, add these records:
   Type: A,  Host: @,  Value: 185.199.108.153
   Type: A,  Host: @,  Value: 185.199.109.153
   Type: A,  Host: @,  Value: 185.199.110.153
   Type: A,  Host: @,  Value: 185.199.111.153
   Type: CNAME, Host: www, Value: YOUR-USERNAME.github.io

4. Wait up to 24 hours for DNS to propagate
5. Check "Enforce HTTPS" in GitHub Pages settings

---

## GAME FEATURES INCLUDED
- American roulette (0 and 00), 38 pockets
- Straight up, split, corner, street, and outside bets
- $20 starting balance, stored in browser localStorage
- Balance cap — cannot bet more than you have
- Ad gate when balance hits $0 (simulated — activates with AdSense)
- Daily $20 bonus (24-hour cooldown, only if balance < $20)
- Spin history (last 50 spins)
- Sound effects via Web Audio API (no audio files needed)
- Haptic feedback via Vibration API
- Settings screen (sound/haptic toggles)
- Vegas skyline background
- Casino-style chips with segment design
- Pull-to-spin wheel mechanic
- Ball travels counter-clockwise, wheel clockwise
- Win toast popup (auto-dismisses in 2 seconds)
- PWA: installable to iPhone home screen via Safari
- Offline play after first load (service worker cache)

---

## FUTURE: Native App Store Version
When you're ready to move to the App Store:
1. Post on Fiverr or Upwork: "Convert PWA to Swift iOS app"
2. Share this index.html + this guide + your screen designs
3. Budget: $150–250 for a simple conversion
4. They will handle Xcode, signing, and App Store submission
