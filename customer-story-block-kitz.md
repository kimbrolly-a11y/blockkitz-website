# Block Kitz

*Shipping a compliant, family-safe puzzle game end-to-end with a Claude Code-native studio.*

---

**Client:** Infinity Tech LLP (Singapore UEN T26LL0996E)
**Studio:** Hungry Humans
**Product:** Block Kitz — mobile puzzle game
**Sector:** Family-safe mobile gaming
**Platform:** Android (iOS on roadmap)
**Status:** 10,000+ downloads · Google Play Closed Testing · v1.0.1
**Live:** [blockkitz.com](https://blockkitz.com) · [Play Store beta opt-in](https://play.google.com/apps/testing/com.blockkitz.game)

---

## The brief

Infinity Tech LLP commissioned Hungry Humans to design, build, and launch a family-safe mobile puzzle game that could stand up to the strictest regulatory bars in the market — Google Play's Families Policy, COPPA, GDPR-K, the UK Age Appropriate Design Code — while still feeling as playful and polished as the top-charting titles. The mandate: no compromises on compliance, no compromises on craft.

## What we shipped

A three-mode block puzzler with **15,000+ hand-crafted levels across 30 themed chapters** and infinite daily challenges:

- **Classic** — 8×8 drag-and-drop block placement, chapter-based progression from "Rookie Grounds"
- **Pivot Blocks** — modern falling-block puzzler with SRS rotation, 7-bag randomiser, T-Spin bonuses, hold piece, guideline scoring
- **Adventure** — gems, bombs, frozen cells, locked treasures across ten mystical chapters, each with its own rules and visual world

Wrapped in a proprietary "Jelly Pop" design system — Fredoka + Baloo 2 typography, high-contrast navy/gold palette, mobile-first UI, ambient piano soundtrack, thirty distinct chapter environments.

## The compliance work

Family-safe by architecture, not by afterthought:

- **Advertising ID only** — no personal data collected, no profiles built, no behavioural tracking, no data sharing
- **Non-personalized ads only** — `tagForChildDirectedTreatment=true`, `tagForUnderAgeOfConsent=true`, `maxAdContentRating=G`
- **No forced ads** — every ad is player-initiated ("Watch Ad for Revive," "Watch Ad for x2 Coins")
- **No in-app purchases** in the launch build; optional cosmetic packs planned with a parental math gate
- **Offline gameplay** — connection needed only for the optional rewarded ad
- **Separate marketing site** ([blockkitz.com](https://blockkitz.com)) with Privacy, Terms, Cookies and Children's Safety pages — no analytics, no third-party scripts, Lighthouse ≥ 95

## How we built it

Hungry Humans is a Claude Code-native studio. Every layer of Block Kitz — game logic, UI/UX, mobile packaging, monetization, Play Store compliance, marketing site, ongoing live operations — was designed and delivered inside a Claude Code development environment. That end-to-end methodology is what let a small team ship a full-lifecycle commercial mobile product, from procedural level generation to Android release signing to blockkitz.com to Google Ads campaigns, at the velocity Infinity Tech needed.

**Stack:**
Vanilla HTML / CSS / JavaScript (game core) · Capacitor 6 (Android wrapper) · Astro + Tailwind (marketing site) · Vercel · Cloudflare DNS · Google AdMob (families-safe configuration) · Google Play Billing (deferred) · ElevenLabs (audio pipeline)

## Outcomes

- **10,000+ downloads** on Google Play
- **18+ iteration cycles** from live player feedback, shipped as sequential production releases
- **v1.0.1** live in Google Play Closed Testing
- Play Console developer verification: **passed**
- Google Play Families Policy self-certification: **passed**
- Marketing site: static, tracker-free, mobile-first, Lighthouse ≥ 95

## Credit

Published by **Infinity Tech LLP**. Developed by **Hungry Humans**.
