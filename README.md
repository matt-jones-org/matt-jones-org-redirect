# matt-jones.org redirect

Browser redirects from old matt-jones.org arcade URLs to [Cool Matt Games](https://coolmatt.games).
Each page sends the visitor to the same path on coolmatt.games, so old links and bookmarks keep
working. The arcade itself lives in
[matt-jones-org/cool-matt-games](https://github.com/matt-jones-org/cool-matt-games).

## Status

This repo **formerly** answered at matt-jones.org, right after the arcade moved. Its `CNAME` was
removed in `f2dcdfb`, and matt-jones.org now serves the Matt Jones, LLC company site from
[Matt-Jones-LLC/matt-jones.org](https://github.com/Matt-Jones-LLC/matt-jones.org). These pages
are kept for reference and in case the redirects are needed again.

## How it works

GitHub Pages cannot send a real HTTP redirect, so each page redirects in the browser:

- `index.html`, `about/index.html` and one `index.html` per game are tiny pages with a canonical
  link, a meta refresh and a line of JavaScript, all pointing at the matching page on
  coolmatt.games.
- `404.html` catches every other path and sends it to the same path on coolmatt.games. Without
  JavaScript it can only fall back to the coolmatt.games home page.

The script uses `location.pathname` as-is, so it only maps paths correctly when served at the root
of a custom domain. Served from a `github.io/<repo>/` project URL, the repo name would end up in the
target path.

To preview, open any of the HTML files in a browser; they redirect immediately.

## Adding a page

Nothing has to change for new games: `404.html` already forwards any path. A folder with an
`index.html` like the others is only worth adding for pages that were once published at
matt-jones.org, since those get a proper canonical link.

## DNS and email

Not managed here. Email for matt-jones.org is Google Workspace. DNS notes are in `dns/records.md`
in [matt-jones-org/cool-matt-games](https://github.com/matt-jones-org/cool-matt-games) (formerly
`matt-jones-org/website`).
