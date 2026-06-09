# AGENTS.md — Level Up – Internet Segura

This repo is the **HTML/CSS/JS landing page** for a Roblox educational game. The game itself is built in Roblox Studio with Luau; only the website lives here.

## Setup & serve

No build step, no package manager, no dependencies. Open `index.html` in a browser or use any static file server (e.g. `npx serve .`).

## Deployment (GitHub Pages)

After pushing to `main`, enable via: Repo Settings → Pages → Deploy from branch `main`.

## Architecture

- Flat structure: `index.html` + `script.js` + `styles.css` + image files at root.
- Images (screenshots) are referenced via public `raw.githubusercontent.com` URLs in `index.html`.
- Video placeholders expect YouTube/Vimeo iframe embeds (currently dummy).
- Roblox game link placeholder: `https://www.roblox.com/games/SEU_GAME_ID` — replace with real ID.

## Style quirks to avoid breaking

- **Portuguese** — all text is in pt-BR (`lang="pt-BR"`).
- Brand colors via CSS custom properties in `:root` (`--primary-color: #FF6B35`, etc.).
- Intersection Observer animations on `.feature-card, .gallery-item, .team-member` — adding new sections may need the same observer hook.
- Smooth scroll on `click` of `a[href^="#"]` links.

## Known CSS issues

- `styles.css:285` — double semicolon `width: 800px;;`
- `styles.css:303` — `overflow: auto` should be `hidden` on `.gallery-item`
- `styles.css:294` — `grid-template-columns: 500px` on `.gallery-grid` is overridden by `display: flex; flex-direction: column` on the same rule; the grid property is dead code.
