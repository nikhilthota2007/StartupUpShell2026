# Startup Shell 2026 — Portfolio

A single-page portfolio answering the Startup Shell application prompt.

- **Part one, what I've built** — SmartMoney, Station 43, ReturnFlow, Klio Care.
- **Part two, what I'm working on** — Liquid (live), Ride Rite, feedback routing,
  SmartMoney expanded.
- **Why Startup Shell** — a closing section on what I want from the community and
  what I can offer it.

## Diagrams, and adding real screenshots

Four sections carry hand-authored inline SVG diagrams rather than screenshots:

| Section | What it shows |
|---|---|
| SmartMoney | The model calls the tested library for every number, so the chat and the interface read from one source |
| Liquid | Card payment vs Liquid payment, and where the 2-3% goes |
| Ride Rite | Every dispatch passes through the E-Hail licence |
| Feedback routing | The rating branch, and the Google link that is sent either way |

They are plain `<svg>` in the page: no library, no image files, and they inherit
the page colours. Station 43 has no diagram, because a site redesign has no
mechanism worth drawing; it wants a real screenshot.

To add real screenshots, drop the file in `img/` and put a figure where you want
it:

```html
<figure class="shot tilt-a">
  <img src="img/whatever.png" alt="...">
  <div class="drop">img/whatever.png</div>
  <figcaption>One line on what this shows.</figcaption>
</figure>
```

The `.shot` styles and the script that handles a missing file are still in the
page, so a slot falls back to a labelled placeholder rather than a broken image.

## Adding your links

Open `index.html`, find the `LINKS` block at the top of the `<script>` near the
bottom of the file, and paste a URL between the quotes:

```js
var LINKS = {
  github:         "https://github.com/nikhilthota2007",
  linkedin:       "",   // e.g. https://www.linkedin.com/in/your-handle
  liquid:         "https://liquidwallet.co",
  smartmoney:     "",   // the deployed SmartMoney app
  smartmoneyRepo: "",   // the SmartMoney repository
  riderite:       ""    // the Ride Rite repository
};
```

Any entry left empty stays hidden and its row collapses, so the page never shows
a dead link. Links appear in the hero, the footer, and under the project they
belong to. GitHub is already filled in from this repository's remote.

## Adding Liquid's numbers

The single highest-impact addition. Inside the Liquid section there is a commented
block in the `<dl class="proof">` list with transaction count and volume ready to
uncomment once you have the real figures. No invented numbers ship in this file.

## Design notes

Built for a reviewer with ten minutes and no expertise in any of these domains:

- Each entry opens with a large-type standfirst, so the page can be skimmed in a
  couple of minutes. No reading-time estimate is printed: announcing a number
  invites a reviewer to check it.
- Jargon (interchange, T+2 settlement, row-level security, money transmitter,
  avalanche/snowball, *Alice Corp.*, Plaid) is translated in margin sidenotes
  beside the paragraph that uses it.
- A print direction: paper grain, two spot inks (federal blue and riso orange),
  and a misregistered overprint on one headline word. Archivo grotesque over a
  Newsreader serif body, monospace only where it carries meaning. Every section
  sits on the same paper; no section gets its own colour.
- Full entries and brief entries use deliberately different layouts, so the page
  has rhythm rather than one repeated module.
- The page commits to a single light theme: warm paper, dark ink. It renders the
  same way whether or not the viewer's system is set to dark mode.

## Running it

`index.html` is a single self-contained file. No build step, no dependencies.

```sh
python3 -m http.server 8000   # then open http://localhost:8000
```

The only external request is the Google Fonts stylesheet; the page falls back to
system serif/sans/mono without it.

## Publishing a public link

Repository **Settings → Pages → Build and deployment**, set source to
*Deploy from a branch*, pick this branch and the `/ (root)` folder. The site lands
at `https://<username>.github.io/<repo>/`.
