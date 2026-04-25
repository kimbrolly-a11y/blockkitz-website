# Block Kitz — Marketing Website

> **Read this first every session.** Keep it short so it doesn't eat context.
> Update when objectives or architecture change — not after every commit.

---

## What this is

The **public marketing website** for the Block Kitz mobile game.

- **Purpose:** Google Play Store developer verification + player acquisition + legal compliance
- **Domain:** https://blockkitz.com
- **Owner:** Kimberly (solo developer)
- **NOT the game** — the game is a separate Capacitor-wrapped mobile app in a different repo

## Tech stack

| Layer | Choice | Why |
|---|---|---|
| Framework | **Astro** | Static site, blazing fast, zero-JS by default, perfect for marketing + legal pages |
| Styling | **Tailwind CSS** | Rapid utility-first styling, matches game's Jelly Pop aesthetic |
| Hosting | **Vercel** | Same ecosystem as the game, one-click deploy from GitHub |
| Domain | **blockkitz.com** | Registered at Cloudflare Registrar, DNS on Cloudflare |
| Fonts | **Fredoka + Baloo 2** (Google Fonts) | Must match the game for brand consistency |
| Content | **Markdown (MDX)** for legal pages, **.astro** for layout | Easy to edit policy text without touching code |

## Hard rules

1. **Static only.** No database, no user accounts, no forms that POST. This is a marketing + legal site.
2. **Zero tracking.** No Google Analytics, no Meta Pixel, no Hotjar. We target children — any analytics breaks our "no data collected" Play Console declaration.
3. **Mobile-first.** 70%+ of traffic will be from phones. Every page must look great at 360×800px before anything else.
4. **Performance budget:** Lighthouse score ≥ 95 on all pages. First Contentful Paint < 1s. Fully static output, no hydration unless absolutely required.
5. **Accessibility:** WCAG 2.1 AA minimum. All images have alt text, all buttons have labels, color contrast ≥ 4.5:1.
6. **NEVER** add external scripts (no jQuery, no analytics, no ad scripts, no widgets).

## Required pages (all must exist before launch)

### Core marketing
- `/` — **Home** (hero + features + CTA)
- `/features` — What's in the game (3 modes, 1000 levels, family-friendly, etc.)
- `/screenshots` — Visual gallery
- `/download` — Play Store badge + direct APK link
- `/about` — About the developer (builds trust for Play Console reviewers)
- `/support` — FAQ + contact form (mailto: link only, no form POST)

### Legal (REQUIRED by Google Play Store)
- `/privacy` — Privacy Policy (content already written — copy from game repo)
- `/terms` — Terms of Service (content already written — copy from game repo)
- `/cookies` — Cookie Policy (we use zero cookies; still needs a page for EU compliance)
- `/safety` — Parental info / Children's safety page (required because we target kids)

### Optional (nice-to-have)
- `/press` — Press kit (logos, screenshots download)
- `/blog` — Blog (empty initially, shows "active" developer)
- `/404` — Custom 404 page

## Google Play Store verification requirements

For Play Console to approve the app, this website MUST have:

1. ✅ **Working HTTPS** at a real domain (blockkitz.com)
2. ✅ **Privacy Policy URL** — publicly accessible, no login required
3. ✅ **Support contact** — a visible email address (support@blockkitz.com)
4. ✅ **Developer identification** — real name or company name on /about
5. ✅ **Consistent branding** — matches the in-app branding
6. ✅ **Active site** — not parked/under-construction. Real content.
7. ✅ **Mobile-responsive** — Google reviewers test on mobile
8. ✅ **Accessible** — no broken links, no 404s on linked pages
9. ✅ **No misleading claims** — if we say "free" or "no ads" it has to be true

### For kid-targeted apps (Families Policy) — ALSO REQUIRED:

10. ✅ **Children's Safety section** — `/safety` page explaining our protections
11. ✅ **Parental info** — COPPA-compliant language
12. ✅ **No data collection claims** — must match the Data Safety form on Play Console
13. ✅ **Age-appropriate imagery** — no violence, no suggestive content on screenshots

## Brand guidelines (copy-paste into prompts)

### Colors (from game's "Jelly Pop" design system)

```css
--bb-bg-deep:      #0a1030;   /* deepest navy */
--bb-bg-mid:       #1a2468;   /* mid navy */
--bb-bg-light:     #2d3b7a;   /* lighter navy */
--bb-primary:      #ffd700;   /* gold */
--bb-primary-dark: #ff9800;   /* orange */
--bb-success:      #22c55e;   /* green */
--bb-danger:       #ff3b6b;   /* hot pink */
--bb-info:         #2aa7ff;   /* bright blue */
--bb-grape:        #9b4bff;   /* purple */
--bb-coin:         #ffd700;   /* coin gold */
--bb-pink:         #ff8fae;
--bb-text-primary: #ffffff;
--bb-text-dim:     rgba(255,255,255,0.85);
--bb-text-faded:   rgba(255,255,255,0.55);
```

### Fonts

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@500;700;800&family=Fredoka:wght@400;500;600;700&display=swap" rel="stylesheet">
```

- **Display/headings:** Baloo 2, 800 weight, letter-spacing 2-4px
- **Body:** Fredoka, 400-500 weight
- **UI/buttons:** Fredoka 700

### Logo
- Source: copy `Title_logo.png` from the game repo at `Assets/Title_logo.png`
- Format: PNG with transparent background, 832×352px
- Use on: hero, header, favicon (auto-generate smaller sizes)

### Tone of voice
- **Friendly, warm, clear.** Not corporate.
- Speaks to parents AND kids.
- Short sentences. Active voice.
- Emojis OK in small doses (🎮 🧩 ⭐ 🏆) — match the in-app vibe.

## Game facts (use verbatim in copy)

- **Genre:** Block puzzle / casual puzzle
- **Platform:** Android (iOS in future)
- **Age rating:** Rated for All Ages (IARC rating pending — do not claim PEGI/USK/ESRB specifics until IARC lands)
- **Modes:** Classic (8×8 drag & drop), Pivot Blocks (modern falling-block puzzler — SRS, 7-bag), Adventure (gems + bombs + frozen cells + locked treasures)
- **Levels:** **15,000+ total across 30 themed chapters** (5,000 per mode × 3 modes; 10 chapters per mode). Marketing copy must say "15,000+ levels across 30 themed chapters. Three game modes. Infinite daily challenges." per the v1.0.1 compliance spec confirmed by Kimberly.
- **Monetization (v1.0.1 build):** Optional rewarded video ads (AdMob). **No in-app purchases in the launch build.** Optional cosmetic coin packs with a parental math gate are planned for a later update.
- **Offline play:** Gameplay works offline. Only optional rewarded video ads need a connection. **Do NOT claim "100% offline" or "completely offline"** — it's inaccurate and policy-risky.
- **Family-safe:** COPPA-compliant, GDPR-K compliant, UK AADC aligned, Google Play Families Policy aligned. **Data posture:** advertising ID only, used solely to serve non-personalized ads when the player taps "Watch Ad." No profiles. No behavioural tracking. No data sharing. **Do NOT claim "zero data collection"** — it contradicts the Data Safety form.
- **Ads:** Non-personalized only. `tagForChildDirectedTreatment=true`, `maxAdContentRating=G`.
- **Beta status:** v1.0.1 is live in Google Play Closed Testing. Opt-in URL: `https://play.google.com/apps/testing/com.blockkitz.game`. CTA sitewide is "Join the Beta", not "Download Free".
- **Beta feedback URL:** `https://blockblitz-eight.vercel.app/feedback.html` (linked from footer).
- **Languages:** English only (v1). More planned.

## Working conventions

- **Static-first.** Prefer `.astro` pages with zero client JS. Only add JS if absolutely required (e.g., mobile menu toggle).
- **No CMS.** All content lives as MDX files in the repo. Commits = content updates.
- **Use `<Image>` from `@astrojs/image`** for all images so they're optimized and responsive.
- **Every legal page** has a "Last updated" date at the top. Update it when content changes.
- **Every page's `<head>`** has unique `<title>`, `<meta description>`, `<link rel="canonical">`.
- **Open Graph / Twitter Card meta tags** on every page so shared links look good.
- **sitemap.xml + robots.txt** auto-generated (Astro has integrations for both).

## Files in this project (target structure)

```
blockkitz-website/
├── CLAUDE.md                         ← this file
├── astro.config.mjs
├── package.json
├── tailwind.config.mjs
├── tsconfig.json
├── public/
│   ├── BlockKitz-debug.apk           ← copy from game repo when ready
│   ├── favicon.ico
│   ├── favicon.svg
│   ├── og-image.png                  ← 1200×630 Open Graph banner
│   ├── apple-touch-icon.png
│   └── robots.txt
├── src/
│   ├── layouts/
│   │   ├── BaseLayout.astro          ← site-wide shell (header, footer, meta)
│   │   └── LegalLayout.astro         ← for privacy, terms, cookies, safety
│   ├── components/
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   ├── Hero.astro
│   │   ├── FeatureCard.astro
│   │   ├── ScreenshotCarousel.astro
│   │   ├── DownloadButtons.astro
│   │   ├── CTA.astro
│   │   └── BlockDecoration.astro     ← decorative candy-cube accents
│   ├── pages/
│   │   ├── index.astro               ← /
│   │   ├── features.astro
│   │   ├── screenshots.astro
│   │   ├── download.astro
│   │   ├── about.astro
│   │   ├── support.astro
│   │   ├── privacy.mdx
│   │   ├── terms.mdx
│   │   ├── cookies.mdx
│   │   ├── safety.mdx
│   │   └── 404.astro
│   ├── content/                      ← if using Astro content collections
│   └── styles/
│       └── global.css                ← Tailwind base + brand CSS vars
└── assets/
    ├── Title_logo.png                ← copied from game repo
    ├── app-icon-512.png              ← copied from game repo
    ├── feature-graphic.png           ← copied from game repo
    └── screenshots/                  ← 5 marketing screenshots, copied from game repo
```

## Session etiquette

- **Don't re-read CLAUDE.md** every time — once per session is enough.
- **Don't install analytics.** Not Google Analytics, not Plausible, not Vercel Analytics. Our data posture is "nothing collected."
- **When in doubt about legal language** — copy from the existing `privacy.html` and `terms.html` in the game repo. Don't rewrite from scratch.
- **Build + preview locally** before pushing: `npm run build && npm run preview`
- **Check Lighthouse score** before declaring a feature done.

---

*Last updated: 2026-04-25 (v1.0.1 compliance rewrite — 15,000+ levels, Closed Testing, advertising-ID-only data posture)*
