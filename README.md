# Bartender's Box — Landing Page

A static splash page for **Bartender's Box**, a craft cocktail subscription service. Every month we ship spirits, mixers, garnishes, and recipe cards to make bar-quality cocktails at home — no bartender required.

## Stack

- Plain **HTML** + **TailwindCSS** (via CDN) — no build step, no backend
- Google Fonts: Fraunces (display) + Inter (body)
- Inline SVG cocktail illustration (no external image dependencies)
- Fully mobile-responsive

## Local preview

Just open `index.html` in a browser, or serve it:

```bash
npx serve .
# or
python3 -m http.server 8000
```

## Deploy

Deployed to Vercel as a static site (see `vercel.json`).

```bash
export VERCEL_TOKEN=...        # provided out-of-band, never committed
vercel deploy --prod --token $VERCEL_TOKEN --yes
```

## Notes

The waitlist email form is intentionally static — it shows a client-side success
message but does not yet post anywhere. Wiring it to a real capture backend is a
follow-up task.
