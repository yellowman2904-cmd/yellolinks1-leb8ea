# Base44 Dev Environment

## Project Overview
This is a static "Truffled" game portal site. The entire app is a single self-contained HTML page (with CSS + JS) embedded inside an SVG file via `<foreignObject>`. All 5 `truffled-*.svg` files are byte-identical copies of the same page.

## How It Runs
- Served as static files by **nginx:alpine** via `docker-compose.base44.yml`.
- nginx config (`nginx.base44.conf`) serves `truffled-1-i9db.svg` as the index page at `/`.
- The app listens on host port **3000** (mapped to nginx port 80).
- No backend, no database, no build step, no external credentials needed.

## Verification
- `curl http://localhost:3000/` should return the SVG content with the Truffled page.
- The preview iframe renders the SVG, which displays the embedded HTML page.
