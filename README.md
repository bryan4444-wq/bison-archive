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

## Offseason and media archive update
This revision adds three visible site sections: **Offseason** (2027 review), **Bison Beat** (expanded Daniel Mercer article reconstructed from established canon), and **30 for 30** (Colts Wrapped, The Final Conversation, and Always Compete: The New Frontier). Original roleplay scripts were not available verbatim; episode guides and article prose are labeled reconstructed. No extra dependencies. Upload all four files together.

## 2026 transaction ledger correction
The historical transaction section now contains 12 major trade entries with received/sent packages and 10 confirmed midseason free-agent signings, searchable and filterable. The 2026 ledger in continuity.md supersedes prior abbreviated notes.


### 2026 transaction ledger cache fix
The website loads a versioned data.js URL to prevent GitHub Pages/browser caches from mixing the new 22-entry transaction ledger with an older four-entry data file. Upload **all four files together**. After GitHub Pages publishes, use Ctrl+Shift+R once if needed.

## Archive 2.1 — Full written stories
Expanded `colts-wrapped.html`, `final-conversation.html`, and `always-compete.html` into substantial chapter-by-chapter fictional documentary narratives. Expanded `mercer-offseason-2027.html` with deeper analysis. These are reconstructed creative prose, not recovered verbatim scripts. No dialogue is invented for owner Bryan, and no future game outcomes are fabricated. Deploy all files together to GitHub Pages.

## Archive 2.2 — navigation and polish
- Homepage documentary links now correctly advertise complete written treatments.
- Documentary reading pages include chapter navigation, estimated reading time and a next-story link.
- Added `database.html` with focused views for roster, depth, operations, 2026 and 2027 transactions, people, offseason and continuity. This reuses the complete original archive rendering and data; `archive.html` remains available as an all-in-one fallback.
- The database checks for 22 historical 2026 transactions and reports a stale/missing data.js file.
- All 12 files must be uploaded together. On GitHub Pages, hard-refresh after deployment.
- This does not claim browser-based QA of live deployment; source and syntax were validated locally.


## Archive 2.3 — 2027 preseason sweep
New full Daniel Mercer column `mercer-preseason-2027.html`, homepage headline and 3–0 scoreboard, 33-entry Week 4 transaction page `preseason-transactions-2027.html`, updated documentary narrative, and authoritative continuity update. Source files came from user uploads; do not overwrite data.js with an older version. Madden Super Bowl LXII is a projection only. Upload ALL root files together to GitHub Pages.


## Archive 2.4 — Final 53
- New final 53-man roster and all four post-cut depth-chart tabs; updated team 87 OVR / 88 OFF / 87 DEF and development distribution.
- Previous Week 1 roster, finances, injuries and contracts are historical snapshots.
- Preserved 2026 transaction ledger, 2027 Week 4 transaction ledger, Mercer features, Mina documentaries, and 3–0 preseason results.
- Upload all files together; updated data.js uses cache-busted `?v=20261026-roster53-v24` in database and archive views.

## Archive 2.6 — Built, Not Given Episode 01
- Added `built-not-given-episode-01.html` with the full narrative treatment of The First Roar, including private screening, Colts acquisition, relocation, Patricia’s memorial, Tennessee 21–14, and the Beast Mode cliffhanger.
- Linked the episode from the homepage Newsroom and Bison Films sections, and from the prior ongoing documentary page.
- One duplicate intro paragraph was consolidated; chapter time markers are approximate. This is a fictional written screenplay, not a playable video.
- The original no-fumbles-for-the-entire-regular-season Lamborghini agreement is unchanged despite Marshawn’s joking dialogue in the screening.


## Archive 2.7 — Character Bible update
Expanded searchable Character Bible entries for Andy, Lindy and Marshawn Lynch, plus a new continuity addendum. Updated data.js; upload all files together.

## Archive 2.8 — Lindy character update
Expanded Lindy’s canonical Character Bible entry: 33, white, from Iowa, petite and blonde; has grown to love Vietnamese home cooking through family meals with the Luongs. All other archive files and canon preserved. Upload all 18 files to the GitHub Pages repository root.


## Version 2.9 — Week 2 photo
Added `week2-jaguars-action.png`, a Week 2 Jaguars game page (`week2-2027.html`), and the image to the schedule page. Week 2 result remains pending.


### 3.0 Week 2 result
Week 2 Jacksonville W 31–14; 2–0 season record; full recap and new Daniel Mercer article; homepage and schedule updated.
