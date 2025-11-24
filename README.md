# github-search-user
React app for searching GitHub users with pagination, Tailwind styling, and rate-limit awareness. Everything lives in a single `index.html`.

## How to Run
1. Install any static HTTP server (e.g. `npm install -g serve`) or use your own.
2. From `/home/dmujuzi/coding/github-search-user`, run `serve .` (or `python -m http.server`).
3. Open `http://localhost:3000/index.html` (or the port your server prints) in a browser.

> You can also double-click `index.html`, but serving it avoids CSP and caching quirks.

## Main Features
- **Single-file React app**: uses CDN React + Babel, so no bundler required.
- **GitHub Search API integration**: leverages `https://api.github.com/search/users` with query + pagination params.
- **Smart pagination**: Previous/Next always visible, disable themselves appropriately, and reset to page 1 on fresh searches.
- **Tailwind UI**: responsive cards showing avatar, username, and profile URL in a dark GitHub-inspired palette.
- **State awareness**: loading spinner, empty onboarding state, and explicit error copy when rate limits are hit.

## Major Limitations
- **Unauthenticated API quota**: anonymous requests quickly hit rate limits; add a GitHub token header for production.
- **Client-only architecture**: no caching or proxying, so every search hits GitHub directly and exposes your IP.
- **Minimal pagination controls**: only previous/next buttons—no numeric jump or infinite scrolling.
- **Single-file design**: great for demos, but hard to scale or test as the UI grows.