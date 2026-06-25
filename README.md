# Performance Retreat — Corporate High-Ticket Landing Page

Zero-build static landing page on the real Performance Golf brand system. Deploys to Vercel like the dashboard.

## Repo structure — upload ALL of this (not just index.html)

```
index.html
assets/
  fonts/   ABCRepro-{Regular,Medium,Bold}.woff2, ABCReproMono-Regular.woff2, GT-Super-Text-Book{,-Italic}.woff2
  logos/   combination-white.png, symbol-orange.png  (+ black/white variants, all transparent)
```

The page references `assets/...` with relative paths, so the **assets folder must sit next to index.html** in the repo. In GitHub's "Upload files," drag the whole folder in together.

## Deploy

1. Put `index.html` + `assets/` at the repo root → push to `pg-htkt-retreat-lp`.
2. Import as a new Vercel project (Framework: Other, no build command).
3. Point your domain/subdomain at it.

## Brand system (already wired)

- **Fonts:** Repro (primary), Repro Mono (technical labels/eyebrows/buttons), GT Super (serif, used only for the testimonial quote). Self-hosted from `assets/fonts`.
- **Colors:** Performance Orange `#FF3D00`, warm black `#1D1A1A`, warm grays (Stone/Pebble/Sand/Fog/Mist). All in `:root` as variables.
- **WCAG rule honored:** Performance Orange always pairs with **black** text — so every orange button/section uses black text, per the brand's text-combination guidance.
- **Logos:** transparent PNGs generated from the brand files. White lockup on dark sections, black on light, orange symbol as favicon. Source files are licensed (Repro/GT Super = Grilli Type) — fine to self-host, don't redistribute.

## Before launch — swap these placeholders

1. **OnceHub link** — `--oncehub-url` in `:root`. CTAs auto-append captured UTMs/click-IDs. To embed the scheduler in-page instead of linking out, paste the OnceHub snippet into `<div id="oncehub-embed">`.
2. **Tracking** — `TRACKING PLACEHOLDERS` block in `<head>`: Meta Pixel, Microsoft UET, optional GTM.
3. **Content** — search `[ ` for copy/proof to fill (coach names/bios, testimonial, stats) and the `data-label` image blocks for photos.
4. **Vidalytics** — already embedded in the hero. No action.

## Attribution (built in)

Captures `utm_*`, `fbclid`, `msclkid`, `gclid`, `li_fat_id`, persists for the session, and appends to the OnceHub link so Meta/Bing clicks carry attribution into HubSpot / High Ticket HQ. Map the same params into hidden HubSpot fields when you wire the form.

## Note on the in-chat preview

The chat preview renders index.html alone, so the brand fonts and logos (separate files in `assets/`) may not appear there and it'll fall back to system fonts. That's expected — it renders correctly once the whole folder is in the repo and deployed.
