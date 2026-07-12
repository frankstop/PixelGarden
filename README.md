# Pixel Garden

A tiny pixel-art idle gardening toy. Plant seeds, let them grow in real time —
they keep growing even while the tab is closed — then harvest blooms for coins.
Progress saves automatically to your browser's local storage.

Built as a Claude Design Component (`.dc.html`) rendered by the bundled
`support.js` runtime, which loads React and Babel from a CDN at page load.

## Run it

Any static host works. Locally:

    python3 -m http.server 8000
    # open http://localhost:8000

## Files

- `index.html` — the Design Component (garden UI + game logic)
- `support.js` — the dc-runtime that renders it
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
