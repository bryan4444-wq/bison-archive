# Oklahoma City Bison static archive

Portable static site. No build step, database, subscription, or API key required.

## Files
- `index.html`: responsive homepage, roster search, cast, transactions, media, continuity UI.
- `data.js`: editable cast, roster, and transactions.
- `continuity.md`: the canonical ChatGPT handoff. Update this after each major event.

## Run locally
In this folder, run `python3 -m http.server 8080`, then visit `http://localhost:8080`.
A web server is recommended because browsers often block fetching `continuity.md` from `file://`.

## Self-host on a home server
Serve this folder with Nginx, Caddy, Apache, or a NAS static web service. An example Caddyfile for local DNS:

```
bison.home.arpa {
    root * /srv/bison-archive
    file_server
}
```

Configure your local DNS resolver to point `bison.home.arpa` to the server. HTTPS may need additional configuration with local certificates. You can also use plain HTTP on a trusted LAN, but avoid transmitting secrets. No port forwarding is needed for LAN-only access.

## Can ChatGPT access it?
ChatGPT web browsing generally requires a publicly reachable HTTPS URL. It cannot directly access your LAN-only DNS, private IP, or Tailscale-only address. A public hostname alone does not make a private server accessible. A public Cloudflare Pages site is the simplest option for URL-based reading. For a private site, copy `continuity.md` into the chat or upload it instead. A public website is not private even if the URL is obscure.

## Deploy for free
Upload this directory to a static hosting provider such as Cloudflare Pages, GitHub Pages, or Netlify. Provider plans and limits may change; check their current terms. A custom domain is optional.

## Maintain the archive
1. After a game or major transaction, update `data.js` and `continuity.md`.
2. Keep old seasons in additional markdown files as needed.
3. Commit changes to Git for history and rollback.
4. Share the public `/continuity.md` URL in a new ChatGPT thread, or copy its contents if the site is private.

## Canon disclaimer
This is a fictional Madden roleplay archive, not an official NFL, ESPN, or team website. Information is based on the user-provided fictional franchise history; unknown details should not be invented.

## Archive update
The 2026 History section preserves screenshot-based historical depth charts and trade/free-agent evidence. The 2027 roster and draft remain separate. Deploy all four files together to GitHub Pages.

## Character Bible update
The new searchable Character Bible section in `index.html` is populated by `characterBible` in `data.js`. The full canon, relationships, dialogue guidelines and unresolved details are mirrored in `continuity.md`. The seven original cast cards are retained. Replace all four repository files together.

## 2027 preseason Week 1 update
Added 79-player searchable roster with jersey numbers, ratings, speed, and dev traits; interactive Offense / Defense / Special Teams / Specialist depth chart; and a continuity snapshot. Replace all four files together.

## Preseason Week 1 finance/staff/injuries update
Added searchable contract ledger (79 screenshot-transcribed entries), injury report, coordinator profiles and salary-cap summary to the Team Ops section. All four files must be deployed together. Finance and roster player counts are preserved as separate screenshots.
