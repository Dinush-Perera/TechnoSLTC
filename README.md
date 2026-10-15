# Techno 2026

Exhibition site for four projects from the Faculty of Engineering, Sri Lanka Technology Campus.

Plain HTML and CSS — no JavaScript, no build step. Open `index.html` in a browser, or serve the
folder (`python3 -m http.server 4321`) and visit <http://localhost:4321>.

## Pages

| File | Exhibit |
| --- | --- |
| `index.html` | Poster wall and floor index |
| `crawl-bot.html` | Crawl-Bot |
| `dobot-magician.html` | DOBOT Magician |
| `sigiriya-vr.html` | Sigiriya VR |
| `flight-simulator.html` | VR Flight Cockpit |

## Getting around

There is no top menu. Visitors move through the site two ways:

- **`index.html`** — the poster wall at the top and the floor index below it both link to all
  four exhibits.
- **The pager** at the foot of every product page — previous exhibit, back to all exhibits,
  next exhibit.

Adding a fifth exhibit means adding a tile to the wall and a row to the index on `index.html`,
then fixing the pager links on the pages either side of it.

## Changing an image

Originals live in `IMages/`. The web copies in `assets/img/` are resized and compressed —
the originals are around 3.5 MB each, far too heavy for a phone on exhibition wifi.

To regenerate them after replacing an original:

```bash
sips -s format jpeg -s formatOptions 72 -Z 1600 "IMages/Project 1.jpg" --out assets/img/crawl-bot-wide.jpg
sips -s format jpeg -s formatOptions 65 -Z 900  "IMages/Project 1.jpg" --out assets/img/crawl-bot-card.jpg
```

`-wide` is the page banner, `-card` is the home-page tile.

The posters already carry their own titles, so the site never prints text over them.

## Text

All copy comes from the documents in `Project Details/`, lightly edited for the screen.
