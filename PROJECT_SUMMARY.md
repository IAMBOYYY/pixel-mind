# PixelMind AI — Project Summary

## What We're Building
A **premium text-to-image generator PWA** (Progressive Web App) that works like a native mobile app, hosted free on Netlify. No Play Store needed. Users open it in Chrome and add to home screen.

---

## Tech Stack
- **Pure HTML + CSS + Vanilla JS** — single `index.html` file, zero frameworks
- **PWA** with Service Worker, manifest, installable on Android/iOS
- **Hosted on Netlify** (free tier)

---

## APIs (Free, with fallback chain)
1. **Pollinations.ai** — PRIMARY. 100% free, no key needed, always first
2. **HuggingFace** — FALLBACK 1. Free key from huggingface.co/settings/tokens
3. **Together.ai** — FALLBACK 2. Free $25 credit from api.together.xyz
4. **Stability AI** — FALLBACK 3. Free trial from platform.stability.ai

API keys entered by user in Settings → stored in localStorage (never uploaded).

---

## Features Built
- ✅ Premium animated splash screen (spinning gradient orb)
- ✅ Text prompt input with send button
- ✅ Reference image upload button
- ✅ 6 aspect ratios (1:1, 16:9, 9:16, 4:3, 3:4, 21:9) — visual grid buttons
- ✅ 9 style presets (Cinematic, Oil Paint, Neon City, Watercolor, Pixel Art, Dark Fantasy, Minimal, Vintage)
- ✅ 6 AI models (Flux, Realism, Anime, 3D Art, Turbo, GPT Image)
- ✅ Negative prompt support
- ✅ Seed control (random or fixed)
- ✅ **Rate limiting: 20 generations per 12 hours** (resets automatically, countdown timer shown)
- ✅ Rate limit wall with live countdown
- ✅ Gallery/History tab (saved to localStorage as base64)
- ✅ Download image to device
- ✅ Delete individual images
- ✅ Clear all history
- ✅ Detail view modal per image (shows prompt, model, ratio, style, date)
- ✅ Settings modal
- ✅ API key management modal (HF + Together + Stability)
- ✅ PWA install prompt
- ✅ Haptic feedback (vibration API)
- ✅ Toast notifications
- ✅ AdSense placeholder (commented block, ready to activate)

---

## Files
```
PixelMind_PWA/
├── index.html       ← ENTIRE APP (HTML + CSS + JS in one file)
├── manifest.json    ← PWA manifest (name, icons, theme)
├── sw.js            ← Service Worker (offline + caching)
└── netlify.toml     ← Netlify headers + redirect config
```

---

## Design
- **Font:** Syne (headings) + DM Sans (body) — from Google Fonts
- **Color:** Deep navy-black bg (#06060F), purple primary (#7C3AED), cyan accent (#22D3EE)
- **Style:** Dark luxury, noise texture overlay, glowing elements, animated splash

---

## What's NOT Done Yet (continue in new chat)
- [ ] AdSense setup not activated (placeholder exists in code, needs real ad unit ID)
- [ ] App icon / favicon not created
- [ ] Netlify deploy steps not fully walked through
- [ ] Ads monetization guide (Google AdSense step by step)
- [ ] Alternative stores guide (Amazon, Samsung, APKPure, Itch.io)

---

## How to Deploy (Quick Steps)
1. Go to **netlify.com** → Sign up free → "Add new site" → "Deploy manually"
2. Zip the 4 files → drag & drop the zip onto Netlify
3. Done — live URL instantly. Share it. Users open in Chrome → "Add to Home Screen"

---

## Rate Limit Logic
```js
LIMIT_MAX    = 20          // generations per window
LIMIT_WINDOW = 12 hours    // stored in localStorage
// Key: 'pm_limit_v1' → { count, windowStart }
// Auto-resets when Date.now() - windowStart >= LIMIT_WINDOW
```

---

## Paste This in New Chat to Continue
> "I'm building PixelMind AI — a premium text-to-image PWA. I have all 4 files done (index.html, manifest.json, sw.js, netlify.toml). I need help with: [your next task]. Here's the project summary: [paste this file]"
