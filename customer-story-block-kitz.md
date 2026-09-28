# Block Kitz

**Client:** Infinity Tech LLP (Singapore UEN T26LL0996E)
**Built by:** Hungry Humans
**Product:** Block Kitz — mobile puzzle game
**Sector:** Family-safe mobile gaming
**Platform:** Android (iOS planned)
**Status:** Closed Beta on Google Play, Q3 2026
**Site:** https://blockkitz.com

## The brief

Ship a family-safe puzzle game for Infinity Tech LLP that could stand up to Google Play's Families Policy, COPPA, GDPR-K and the UK AADC — while still feeling as playful and polished as the top charts.

## What we built

A three-mode block puzzler with **15,000+ levels across 30 themed chapters**:

- **Classic** — 8×8 drag-and-drop block placement
- **Pivot Blocks** — modern falling-block puzzler (SRS rotation, 7-bag randomiser)
- **Adventure** — gems, bombs, frozen cells, locked treasures

Plus infinite daily challenges and a consistent "Jelly Pop" visual system — Fredoka + Baloo 2 typography, high-contrast navy/gold palette, mobile-first UI throughout.

## The compliance work

- Zero personal-data collection; advertising ID only, used solely for opt-in rewarded video
- `tagForChildDirectedTreatment=true`, `maxAdContentRating=G`
- Non-personalized ads only, no in-app purchases in the launch build, no behavioural tracking
- Full offline gameplay; connection needed only for the optional "Watch Ad" reward
- Separate marketing site at blockkitz.com with Privacy, Terms, Cookies and Children's Safety pages — no analytics, no third-party scripts, Lighthouse ≥ 95

## Stack

Unity (game) · Capacitor wrapper · Astro + Tailwind (marketing site) · Vercel · Cloudflare DNS · AdMob (families-safe configuration)

## Outcome

- v1.0.1 shipped to Google Play Closed Testing
- Play Store developer verification: passed
- Families Policy self-certification: passed
- Marketing site: static, tracker-free, mobile-first

## Credit

Designed and built by **Hungry Humans** on behalf of **Infinity Tech LLP**.
