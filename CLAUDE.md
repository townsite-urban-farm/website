# Website — Claude Notes

Hugo static site, hosted on Cloudflare Pages at townsiteuf.org.
Deploy by pushing to `main` — Cloudflare builds automatically.
See README.md for build/deploy details.

## Pages not linked from main nav

`/water-systems/` is intentionally absent from the nav.
It is a worker-facing reference page — share the URL directly.
Do not add it to the nav without checking with the site owner.

## Key contacts embedded in content

- **Greg** is referenced as the OpenSprinkler admin in `/water-systems/`.
  He holds the OTC cloud token and controller password.
  If his role changes, update `layouts/water-systems/single.html`.

## OpenSprinkler controller (irrigation system)

- Hardware: OpenSprinkler v3.2 AC, firmware 2.2.0(1)
- Remote access: OpenThings Cloud (OTC) token — no port forwarding needed
- Source reference document: `../open-sprinkler-controller-notes.txt` (not in this repo)
