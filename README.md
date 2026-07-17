# 🏀 NBA Player Wiki Search

An interactive, single-file web demo: type any NBA player's name and get live
autocomplete suggestions plus a player card (photo, bio summary, link to the
full article) — all powered by the free **Wikipedia REST API**. No API key,
no build step, no dependencies.

## Features

- 🔍 **Live autocomplete** — debounced search-as-you-type, biased toward basketball results
- ⌨️ **Keyboard navigation** — arrow keys + Enter to pick a suggestion
- 🃏 **Player cards** — photo, description, and article summary
- 🎲 **Random legend** button + quick-pick chips for famous players
- 🌙 Dark, GitHub-flavored UI in one `index.html`

## Run it

Just open `index.html` in a browser — that's it.

```bash
open index.html        # macOS
```

## Publish with GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Under *Build and deployment*, choose **Deploy from a branch** → `main` / `/ (root)`
4. Your demo goes live at `https://<your-username>.github.io/<repo-name>/`

## How it works

- Autocomplete uses the [MediaWiki search API](https://www.mediawiki.org/wiki/API:Search)
  (`action=query&list=search`) with `origin=*` for CORS
- Player cards use the [Wikipedia REST summary endpoint](https://en.wikipedia.org/api/rest_v1/)
  (`/page/summary/{title}`)

Both are public, key-free, and CORS-friendly — which is why this works as a
static page anywhere, including GitHub Pages.
