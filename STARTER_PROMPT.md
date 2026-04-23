# Block Kitz Website — Starter Prompt for New Claude Code Session

> Paste the block below (between `---` markers) into a **fresh** Claude Code session.
> Have the `CLAUDE.md` file (in this same folder) ready — you'll place it in the new repo.

---

I'm building the marketing website for my mobile game **Block Kitz** at **blockkitz.com**. This is a SEPARATE project from the game itself — the website is purely for marketing, legal compliance, and Google Play Store verification.

## Goal

Build a **static marketing website** using Astro + Tailwind + deployed to Vercel. Must pass Google Play Store's developer verification and Families Policy review.

## Context — what already exists

I have a mobile game called Block Kitz that's ready for Play Store submission. The game is a kid-friendly block puzzle with 3 modes (Classic, Pivot, Adventure), 1,000+ levels, COPPA-compliant, no data collection, optional rewarded ads via AdMob.

**Reference materials I'll provide:**
- `CLAUDE.md` — project context + hard rules (read this FIRST)
- `Title_logo.png` — game logo (transparent PNG, colorful BLOCK KITZ text)
- `app-icon-512.png` — app icon
- `feature-graphic-1024x500.png` — Play Store banner
- 5 marketing screenshots (1080×1920 each)
- `privacy-content.md` — existing privacy policy content to use
- `terms-content.md` — existing terms of service content
- `game-facts.md` — key facts about the game (modes, levels, etc.)

## What I need you to do (in this order)

### Step 1 — Read CLAUDE.md first
It has the full architecture, tech choices, brand guidelines, page list, and hard rules. Don't deviate from it without asking me.

### Step 2 — Scaffold the Astro project

```bash
npm create astro@latest . -- --template minimal --typescript relaxed --install --no-git
npm install -D @astrojs/tailwind @astrojs/mdx @astrojs/sitemap @astrojs/image
npx astro add tailwind
```

Configure `astro.config.mjs` with:
- Site URL: `https://blockkitz.com`
- Integrations: Tailwind, MDX, sitemap
- Output: static

### Step 3 — Build the base layout + design system

Create `src/layouts/BaseLayout.astro` with:
- Header (logo + nav: Home, Features, Screenshots, Download, Support, Privacy)
- Footer (legal links + copyright + developer name)
- `<head>` with Google Fonts (Baloo 2 + Fredoka), meta tags, favicon, Open Graph
- Brand CSS variables in global stylesheet
- Mobile-responsive hamburger menu (CSS-only checkbox hack, no JS)

Match the game's "Jelly Pop" aesthetic:
- Deep navy background with radial gradient
- Candy-block decorative elements
- Fredoka One for headings, Fredoka regular for body
- Warm, kid-friendly tone

### Step 4 — Build all required pages

**Marketing pages:**
- `/` (home) — hero with logo + tagline + "Download" CTA + 3 feature cards + screenshot row
- `/features` — detailed breakdown of 3 modes, 1000 levels, family-safe positioning
- `/screenshots` — gallery grid of 5 screenshots
- `/download` — Play Store badge (placeholder until approved) + direct APK link
- `/about` — "Made by Kimberly, a solo indie developer" story
- `/support` — FAQ accordion + prominent mailto:support@blockkitz.com

**Legal pages (content I'll paste from the game repo):**
- `/privacy` — full Privacy Policy (COPPA + GDPR + UK AADC + Families Policy compliant)
- `/terms` — Terms of Service
- `/cookies` — Cookie Policy (we use zero cookies, but still need the page)
- `/safety` — Children's Safety / Parental Info page

**Utility:**
- `/404` — friendly not-found page

### Step 5 — Configure for Vercel

- Add `vercel.json` with clean URL rewrites (no `.html` in URLs)
- Add `robots.txt` allowing all
- Auto-generate `sitemap.xml` via `@astrojs/sitemap`
- Verify build locally: `npm run build && npm run preview`

### Step 6 — Google Play Store verification checklist

Before declaring "done", verify:

- [ ] Privacy policy is publicly accessible at `https://blockkitz.com/privacy`
- [ ] Terms is publicly accessible at `https://blockkitz.com/terms`
- [ ] Support email `support@blockkitz.com` is visible on at least 3 pages
- [ ] Developer name (Kimberly) appears on `/about`
- [ ] Zero 404s on any internal link
- [ ] Lighthouse score ≥ 95 on all pages (Performance, Accessibility, Best Practices, SEO)
- [ ] Mobile responsive (test at 360×800 minimum)
- [ ] All images have alt text
- [ ] Open Graph meta tags on every page
- [ ] No analytics, tracking, or external scripts
- [ ] `/safety` page exists and mentions COPPA + no data collection
- [ ] `robots.txt` + `sitemap.xml` exist
- [ ] Deployed to Vercel at `https://blockkitz.com` with valid HTTPS

## Design direction (for reference)

Look at the game screenshots I'll provide — the website should feel like a natural extension of that world:
- Same purple/navy cosmic backgrounds
- Same colorful candy-block accents scattered around
- Same warm, playful fonts (Baloo 2 + Fredoka)
- Hero section should feature the logo prominently with candy-cube decorations
- CTAs (Download, Play Now) should be chunky rounded buttons with gradient fills and drop shadows — matching the game's "bb-btn" style

## Hard don'ts

1. **No analytics.** Not Google, not Plausible, not Vercel Analytics.
2. **No forms that POST data.** Use `mailto:` links only for contact.
3. **No external scripts.** Jquery, CDN libs, embeds — all forbidden.
4. **No cookies.** We declare "no cookies" in the cookie policy, must match reality.
5. **No user accounts.** This is a static brochure site.
6. **No placeholder "Lorem Ipsum".** Use real copy from the start.
7. **No inline styles except color CSS vars.** Use Tailwind utility classes.

## Deployment

Once the site is ready:
1. Create a new GitHub repo (`kimbrolly-a11y/blockkitz-website`)
2. Push code to `main`
3. Import project on Vercel (https://vercel.com/new)
4. Connect to the `blockkitz.com` domain (DNS is already on Cloudflare, records point to Vercel)
5. Verify HTTPS works
6. Submit site URL to Google Play Console as my developer website

## Start here

1. Read `CLAUDE.md`
2. Confirm you understand the scope by listing the 12 required pages
3. Scaffold the Astro project
4. Build the base layout and show me a preview of the `/` home page first — I want to approve the design direction before you build the rest

Let's go!

---

## 📦 What to bring from the game repo (copy these files before starting)

From `C:\Users\kimberly\Documents\Claude Projects\Block Blitz\`:

| Source | Destination in website repo |
|---|---|
| `Assets/Title_logo.png` | `assets/Title_logo.png` |
| `Assets/Icons/app-icon-512.png` | `assets/app-icon-512.png` |
| `Assets/Icons/feature-graphic-1024x500.png` | `assets/feature-graphic.png` |
| `Assets/Icons/screenshot-1-levels.png` | `assets/screenshots/1-levels.png` |
| `Assets/Icons/screenshot-2-no-ads.png` | `assets/screenshots/2-no-ads.png` |
| `Assets/Icons/screenshot-3-modes.png` | `assets/screenshots/3-modes.png` |
| `Assets/Icons/screenshot-4-family.png` | `assets/screenshots/4-family.png` |
| `Assets/Icons/screenshot-5-rewards.png` | `assets/screenshots/5-rewards.png` |
| `privacy.html` | Extract text → `privacy-content.md` |
| `terms.html` | Extract text → `terms-content.md` |
| `BlockKitz-debug.apk` (optional) | `public/BlockKitz-debug.apk` |
| `CLAUDE.md` (this folder) | Root of new repo |

## 🔗 Links & info for reference

- **Game repo:** https://github.com/kimbrolly-a11y/Blockblitz
- **Current game Vercel project:** https://vercel.com/kimbrolly-a11ys-projects/blockblitz
- **Domain:** blockkitz.com (registered at Cloudflare Registrar)
- **Existing working domain:** block-blitz.com (for fallback)
- **Support email:** support@blockkitz.com (forwarding setup pending)
- **Developer:** Kimberly (solo indie)
- **Package ID:** com.blockkitz.game
- **Play Store URL (future):** https://play.google.com/store/apps/details?id=com.blockkitz.game
