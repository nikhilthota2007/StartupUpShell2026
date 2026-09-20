# Startup Shell 2026 — Portfolio

A single-page portfolio answering the Startup Shell application prompt.

- **Part 1** — past projects: SmartMoney, ReturnFlow, Ride Rite, the Station 43
  redesign, and running sales at Klio Care. Each entry covers what I did, what I
  learned, and the failure I overcame.
- **Part 2** — what I'm working on: Liquid (live), a restaurant feedback-routing
  platform, and SmartMoney expanded.

## Design notes

Built for a reviewer with ten minutes and no expertise in any of these domains:

- Each entry opens with a large-type standfirst, so the page skims in about two
  minutes and reads in about nine.
- Jargon (interchange, T+2 settlement, row-level security, money transmitter,
  avalanche/snowball, *Alice Corp.*, Plaid) is translated in margin sidenotes
  beside the paragraph that uses it.
- Typography is a heavy grotesque (Archivo) over a warm serif body (Newsreader),
  with monospace reserved for tech stacks, where it carries meaning.
- Liquid gets a full-bleed ultramarine section because it is the only thing here
  taking live payments; everything else stays on quiet warm paper.

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
