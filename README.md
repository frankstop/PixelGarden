# Pixel Garden

A tiny pixel-art idle gardening toy. Plant seeds, let them grow in real time —
they keep growing even while the tab is closed — then harvest blooms for coins.
Progress saves automatically to your browser's local storage.

The whole game is a single self-contained `index.html` — no build step, no
runtime, no dependencies beyond the web fonts and analytics it loads itself.

## Run it

Any static host works. Locally:

    python3 -m http.server 8000
    # open http://localhost:8000

## Files

- `index.html` — the entire game (garden UI + game logic)
- `.nojekyll` — tells GitHub Pages to serve files as-is

## Deploy on GitHub Pages

Repo Settings → Pages → Build and deployment → Source: **Deploy from a branch**,
Branch: **main** / **/ (root)**. The site publishes at
`https://<user>.github.io/PixelGarden/`.

## Analytics

Analytics are handled by the shared `embed-analytics.js` loaded in
`index.html` from `https://frankiejvaldez.com/assets/js/embed-analytics.js`
(GA4 measurement ID `G-RSVR6Y389R`). Page views are collected automatically;
gameplay uses the portfolio-wide event contract:

| Event | Fires when | Parameters |
| --- | --- | --- |
| `game_start` | First meaningful interaction of a session (select, plant, harvest, or weed) | `game_name` |
| `game_end` | Leaving or backgrounding the page after playing | `game_name`, `outcome` (`quit`), `score` (coins), `duration_seconds` |

## Cheat
 https://frankstop.github.io/PixelGarden/?speed=60
