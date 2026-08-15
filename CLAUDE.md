# Website — Claude Notes

Hugo static site, hosted on Cloudflare Pages at townsiteuf.org.
Deploy by pushing to `main` — Cloudflare builds automatically.
See README.md for build/deploy details.

## Water systems page

`/water-systems/` was added to the main nav ("Water") and footer 2026-08-15 at the site owner's request (it was previously worker-facing only).
The site-plan page shows CSS-stacked thumbnails of the water-systems map layers (`.ws-thumbs` in `assets/css/main.css`) — they reuse the full-size PNGs from `static/water-systems/`, so they stay current if the maps are updated.

## Design language (restyled 2026-08-15)

Flat, type-driven layout: neutral gray ground, white cards with 1px hairline borders, no gradients or box shadows.
Brand blues (`--blue-primary` #2979B5, `--blue-dark` #0D3D6B) are accents only — no large colored blocks.
Legacy variable names (`--blue-light`, `--blue-mid`, `--text-muted`, `--radius`, etc.) are kept as aliases in `assets/css/main.css` because the timelapse and water-systems templates use them in inline styles — do not remove them.

## Hoophouse montage (homepage + timelapse page)

Replaced the "Live from the farm" video embed 2026-08-15: a photo montage (matching the TUF timelapse flyer) rendered by `layouts/partials/hoophouse-montage.html`, styles in `assets/css/main.css` (`.montage`, `.montage-strip`).
Used 2×2 on the homepage and 4-across above the video on `/timelapse/`.
Photos live in `static/images/hoophouse/` in two sizes each: 640w (copied from R2 gallery previews) and 1280w (resized from the full-res originals in the private B2 `hoophouse-photos` bucket; the 2022 photo's original camera tops out at 720w).
Browsers choose via `srcset`/`sizes` — keep both sizes if photos are ever swapped.
Weather Underground no longer offers embeddable widgets/stickers (verified 2026-08-11), so the weather station is a plain link — URL lives in `hugo.toml` as `params.weatherStationUrl`.

## Key contacts embedded in content

- **Greg** is referenced as the OpenSprinkler admin in `/water-systems/`.
  He holds the OTC cloud token and controller password.
  If his role changes, update `layouts/water-systems/single.html`.

## OpenSprinkler controller (irrigation system)

- Hardware: OpenSprinkler v3.2 AC, firmware 2.2.0(1)
- Remote access: OpenThings Cloud (OTC) token — no port forwarding needed
- Source reference document: `../open-sprinkler-controller-notes.txt` (not in this repo)
