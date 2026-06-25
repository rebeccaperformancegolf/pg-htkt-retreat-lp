# Performance Retreat — Corporate High-Ticket Landing Page

Single-file, zero-build landing page. Drops into a GitHub repo and deploys to Vercel as a static site (same workflow as the dashboard).

## Deploy

1. Put `index.html` at the repo root (rename to `index.html` if needed — Vercel serves it at `/`).
2. Push to GitHub → import the repo in Vercel → deploy. No framework, no build command needed.
3. (Optional) Add a custom domain / subdomain in Vercel, e.g. `retreats.performancegolf.com`.

## Before launch — swap these placeholders

Everything you need to change is grouped and labeled in the file.

**1. Brand tokens** — top of `<style>`, under `BRAND TOKENS`. Replace the hex values and font names with the real Performance Golf brand-guide values. Change once, updates everywhere.

**2. OnceHub link** — in `:root`, the `--oncehub-url` variable. Replace the placeholder URL with your real OnceHub booking link. The CTA buttons auto-append captured UTMs/click-IDs to it (see below). If you'd rather embed the scheduler in-page than link out, paste the OnceHub embed snippet into `<div id="oncehub-embed">` near the bottom of the booking section.

**3. Tracking** — head of the document, under `TRACKING PLACEHOLDERS`. Paste your Meta Pixel, Microsoft UET, and (optional) GTM snippets.

**4. Vidalytics** — already wired into the hero with your embed code. No action needed.

**5. Content placeholders** — search the file for `[ ` (bracketed text) and the image blocks (`data-label="..."`). These mark every spot needing real copy, coach names/bios, resort photos, testimonials, client logos, and stats.

## Attribution (already built in)

On page load, the script captures `utm_source/medium/campaign/term/content/id`, plus `fbclid`, `msclkid`, `gclid`, and `li_fat_id` from the URL, persists them for the session, and appends them to the OnceHub booking link. That way Meta/Bing clicks carry their attribution into the booking → HubSpot, so these corporate leads land clean in High Ticket HQ instead of needing reconciliation later. When you wire HubSpot, map those same params into hidden form fields for a complete chain.

## Notes

- Mobile-first and responsive; respects reduced-motion; keyboard-focus styles included.
- FAQ uses native `<details>` — no JS dependency.
- Hook copy on the page mirrors the winning ad angle (anti-offsite / "the offsite they actually remember") for scent match. The business-case section adds the ROI language the ads leave out — fill in real numbers or swap for outcome statements.
