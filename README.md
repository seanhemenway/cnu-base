# CNU Chicago

The website for **CNU Chicago** — a sub-chapter of CNU Midwest ([Congress for the New Urbanism](https://www.cnu.org/)) focused on better cities, towns, and neighborhoods across Illinois.

The site introduces the chapter and its leadership and hosts the **Chicago Single Stair Design Competition** — an open competition exploring single-stair (point-access block) housing as a tool for more livable, affordable infill in Chicago.

## Pages

| Page | File | Description |
| :--- | :--- | :--- |
| Home & Contact | [`public/index.html`](public/index.html) | About the chapter, leadership, and social links |
| Design Competition | [`public/competition.html`](public/competition.html) | Brief, rules, site diagrams, jurors, prizes, and sponsors |

## Tech

This is a **static site** — plain HTML, CSS, and assets in [`public/`](public/), with no framework and no build step. It is served and deployed via [Cloudflare Workers static assets](https://developers.cloudflare.com/workers/static-assets/) using [Wrangler](https://developers.cloudflare.com/workers/wrangler/) (see [`wrangler.json`](wrangler.json)).

## Project structure

```
public/
  index.html          # Home & Contact
  competition.html    # Single Stair Design Competition
  styles.css          # Shared styles
  cnu-footer-logo-256.jpg  # CNU Chicago square logo (also the favicon)
  fonts/              # Self-hosted webfonts
  logos/              # Sponsor & partner logos
  *.png               # Competition site diagrams
wrangler.json         # Cloudflare Workers config
package.json
```

## Commands

All commands are run from the root of the project:

| Command | Action |
| :--- | :--- |
| `npm install` | Install dependencies (Wrangler) |
| `npm run dev` | Start a local dev server via Wrangler |
| `npm run deploy` | Deploy to Cloudflare Workers |

> There is no compile step — `npm run build` is intentionally a no-op, since assets are served directly from `public/`.
