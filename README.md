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

Google Analytics (GA4, measurement ID `G-RSVR6Y389R`) is loaded in `index.html`.
Page views are collected automatically; gameplay also fires custom events:

| Event | Fires when | Parameters |
| --- | --- | --- |
| `plant_seed` | A seed is planted in an empty plot | `seed_name`, `cost` |
| `harvest_bloom` | A fully bloomed plant is harvested | `seed_name`, `coins_earned` |
| `clear_weed` | An overgrown plot is cleared | `coins_earned` |
| `select_seed` | A different seed type is selected in the picker | `seed_name` |

## Cheat
 https://frankstop.github.io/PixelGarden/?speed=60
