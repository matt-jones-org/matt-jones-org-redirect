# matt-jones.org redirect

[Cool Matt Games](https://coolmatt.games) used to live at matt-jones.org. This repository is what
answers at matt-jones.org now: every page sends the visitor to the same path on coolmatt.games, so
old links and bookmarks keep working.

The site itself is in [matt-jones-org/website](https://github.com/matt-jones-org/website).

## How it works

GitHub Pages serves this repository from the `main` branch with `matt-jones.org` as its custom
domain (`www.matt-jones.org` redirects to it). GitHub Pages cannot send a real HTTP redirect, so
each page redirects in the browser:

- `index.html`, `about/index.html` and one `index.html` per game are tiny pages with a canonical
  link, a meta refresh and a line of JavaScript, all pointing at the matching page on
  coolmatt.games.
- `404.html` catches every other path and sends it to the same path on coolmatt.games.

Email for matt-jones.org is Google Workspace and has nothing to do with this repository.

## When a game is added

Nothing has to change here: `404.html` already forwards any path. Adding a folder with an
`index.html` like the others is only worth it for pages that were once published at matt-jones.org.

## DNS

Unchanged from when the site lived here. See `dns/records.md` in the website repository.
