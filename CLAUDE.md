# Website — Claude Notes

Hugo static site, hosted on Cloudflare Pages at townsiteuf.org.
Deploy by pushing to `main` — Cloudflare builds automatically.
See README.md for build/deploy details.

## Pages not linked from main nav

`/water-systems/` is intentionally absent from the nav.
It is a worker-facing reference page — share the URL directly.
Do not add it to the nav without checking with the site owner.

## Homepage "Live from the farm" section

Added 2026-08-11: timelapse video embed + weather station button at the top of `layouts/index.html` (styles in `assets/css/main.css`, `.farm-live-*`).
Weather Underground no longer offers embeddable widgets/stickers (verified 2026-08-11), so the weather station is a plain link — URL lives in `hugo.toml` as `params.weatherStationUrl`.

## Key contacts embedded in content

- **Greg** is referenced as the OpenSprinkler admin in `/water-systems/`.
  He holds the OTC cloud token and controller password.
  If his role changes, update `layouts/water-systems/single.html`.

## OpenSprinkler controller (irrigation system)

- Hardware: OpenSprinkler v3.2 AC, firmware 2.2.0(1)
- Remote access: OpenThings Cloud (OTC) token — no port forwarding needed
- Source reference document: `../open-sprinkler-controller-notes.txt` (not in this repo)
