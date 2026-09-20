# Startup Shell 2026 — Portfolio

A single-page portfolio answering the Startup Shell application prompt.

- **Part 1** — past projects: SmartMoney, ReturnFlow, Ride Rite, the Station 43
  redesign, and running sales at Klio Care. Each entry covers what I did, what I
  learned, and the failure I overcame.
- **Part 2** — what I'm working on: Liquid (live), a restaurant feedback-routing
  platform, and SmartMoney expanded.

## Design notes

Built for a reviewer with ten minutes and no expertise in any of these domains:

- Every entry opens with a bolded **"In one line"** summary, so the page can be
  skimmed in about two minutes and read in about nine.
- Jargon (interchange, T+2 settlement, row-level security, money transmitter,
  avalanche/snowball, *Alice Corp.*, Plaid) is translated in grey **Plain English**
  boxes next to where it's used.
- Status markers reflect real state — `LIVE`, `SHIPPED`, `CONCEPT` — rather than
  decorative numbering.

## Running it

`index.html` is a single self-contained file. No build step, no dependencies.
Open it directly, or serve the folder:

```sh
python3 -m http.server 8000   # then open http://localhost:8000
```

Only external request is the Google Fonts stylesheet (Fraunces, IBM Plex Sans,
IBM Plex Mono); the page falls back to system serif/sans/mono without it.

## Publishing a public link

Repository **Settings → Pages → Build and deployment**, set source to
*Deploy from a branch*, pick this branch and the `/ (root)` folder. The site
lands at `https://<username>.github.io/<repo>/`.
