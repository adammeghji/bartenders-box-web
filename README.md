# Bartender's Box — Landing Page

The marketing landing page for **Bartender's Box**, a craft cocktail subscription. Built to the CMO Landing Page Spec (BAR-5 / BAR-6).

## Stack

- Static **HTML** (`index.html`) — single page, no backend
- **TailwindCSS** compiled to a static, minified stylesheet (`styles.css`) for fast mobile load (no CDN runtime JS)
- Google Fonts (Fraunces display + Inter body), loaded non-render-blocking with `font-display: swap`
- Inline SVG hero (open box + cocktail) and a generated OG image (`og.png`, 1200×630) — no external image dependency for the LCP element

## Sections

Hero (headline · subheadline · box+cocktail illustration · primary + secondary CTA · trust micro-copy · social-proof strip) → Testimonials (3) → Value pillars (3) → What's in the box (labeled callouts) → How it works (3 steps) → Proof badge → Pricing / plan selection + email capture → FAQ accordion → Footer. A sticky mobile CTA appears once the hero scrolls out of view.

## Develop / build

```bash
# Rebuild the stylesheet after editing classes in index.html:
npx tailwindcss@3.4.17 -c tailwind.config.js -i src.css -o styles.css --minify

# Preview locally:
python3 -m http.server 8000   # then open http://localhost:8000
```

`styles.css` is committed so the site deploys as pure static files (no build step required on the host).

## Deploy

Deployed to Vercel as a static site (see `vercel.json`).

```bash
export VERCEL_TOKEN=...        # provided out-of-band, never committed
vercel deploy --prod --token "$VERCEL_TOKEN" --yes
```

> The Vercel token is never committed. It is used only as a shell env var; `.vercel` is gitignored.

## Notes

The email capture form is intentionally client-side — it validates and shows a success state, standing in for the checkout/capture handoff. Wiring it to a real backend (and a real checkout) is a follow-up task.
