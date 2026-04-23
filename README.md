# Block Kitz Website — Handoff Package

> Everything you need to spin up the Block Kitz marketing website in a new Claude Code session.

## 📂 What's in this folder

| File | Purpose |
|---|---|
| **`README.md`** | You are here. Overview. |
| **`CLAUDE.md`** | Project guide for the new repo. Copy this to the root of your new website repo. |
| **`STARTER_PROMPT.md`** | The first message to paste into a fresh Claude Code session. |
| **`privacy-content.md`** | Privacy Policy in Markdown — copy into `src/pages/privacy.mdx` |
| **`terms-content.md`** | Terms of Service in Markdown — copy into `src/pages/terms.mdx` |
| **`game-facts.md`** | Reference sheet of game details for marketing copy |

## 🚀 How to use this

### Step 1 — Create the new repo on your computer

```bash
mkdir blockkitz-website
cd blockkitz-website
git init
```

### Step 2 — Copy the handoff files in

From this `website-handoff` folder, copy:
- `CLAUDE.md` → to the root of your new `blockkitz-website` folder
- Keep the other `.md` files handy (you'll reference them during the build)

### Step 3 — Copy brand assets from the game repo

Copy these files from `C:\Users\kimberly\Documents\Claude Projects\Block Blitz\` to the new website folder:

```
Source (in game repo)                              Destination (in website repo)
─────────────────────────────────────────────────────────────────────────────
Assets/Title_logo.png                        →    assets/Title_logo.png
Assets/Icons/app-icon-512.png                →    assets/app-icon-512.png
Assets/Icons/app-icon-192.png                →    assets/app-icon-192.png
Assets/Icons/feature-graphic-1024x500.png    →    assets/feature-graphic.png
Assets/Icons/screenshot-1-levels.png         →    assets/screenshots/1-levels.png
Assets/Icons/screenshot-2-no-ads.png         →    assets/screenshots/2-no-ads.png
Assets/Icons/screenshot-3-modes.png          →    assets/screenshots/3-modes.png
Assets/Icons/screenshot-4-family.png         →    assets/screenshots/4-family.png
Assets/Icons/screenshot-5-rewards.png        →    assets/screenshots/5-rewards.png
BlockKitz-debug.apk                          →    public/BlockKitz-debug.apk
```

(The asset paths into the website repo are suggestions — Claude can move them wherever it wants during setup.)

### Step 4 — Open a NEW Claude Code session in the new folder

In VS Code or terminal:
```bash
cd blockkitz-website
claude
```

(Or however you launch Claude Code.)

### Step 5 — Paste the starter prompt

Open `STARTER_PROMPT.md` → copy the block between the `---` markers → paste as your first message.

Then tell Claude:

> "Here are the content files you'll need:"
> 1. [paste contents of `privacy-content.md`]
> 2. [paste contents of `terms-content.md`]
> 3. [paste contents of `game-facts.md`]

Or save those as files in the repo first and tell Claude the paths.

### Step 6 — Let Claude build

Claude will:
1. Read your `CLAUDE.md` (placed in repo root)
2. Scaffold the Astro project
3. Build the base layout
4. Show you a preview of the home page for approval
5. After approval, build all 12 required pages
6. Set up Vercel deployment config

Review each major milestone before it moves to the next.

## ✅ Definition of done

The website is "done" when:

- [ ] All 12 pages exist and render without errors
- [ ] `https://blockkitz.com` resolves with valid HTTPS
- [ ] Privacy Policy is at `https://blockkitz.com/privacy`
- [ ] Terms of Service is at `https://blockkitz.com/terms`
- [ ] Support email `support@blockkitz.com` is visible on home + support + footer
- [ ] Developer name (Kimberly) is on `/about`
- [ ] Google Play badge on home + download pages
- [ ] APK download link works (either direct or via Play Store badge)
- [ ] Mobile responsive (test at 360×800 minimum)
- [ ] Lighthouse score ≥ 95 on home + privacy + download pages
- [ ] `robots.txt` + `sitemap.xml` exist
- [ ] Zero 404s on any internal link
- [ ] No external scripts / analytics / tracking
- [ ] Meta tags (OG/Twitter) on every page

## 🔗 Once the website is live

Come back to the game repo (`C:\Users\kimberly\Documents\Claude Projects\Block Blitz\`) and tell me:
- "Website is live at blockkitz.com"

I'll then:
1. Update the rate prompt in the game to link to the real Play Store URL
2. Update the game repo's `LAUNCH_KIT.md` with website URL for Play Console submission
3. Help you with the final Play Console submission checklist

## ⏱ Time estimate

- **Copy files + create repo:** 10 min
- **Paste starter prompt + first build:** 5 min
- **Claude scaffolds + first home page preview:** 15-30 min
- **Your design approval + remaining pages:** 1-2 hours
- **Deploy + domain wiring:** 20 min
- **Total:** ~2-3 hours for a ship-ready site

---

**Good luck! The game is done. The website is the final piece before Play Store submission.** 🚀
