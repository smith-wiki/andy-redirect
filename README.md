# andy-redirect

Keeps the Card site's `andy.smith.wiki` URLs alive after it moved to
[old.smith.wiki](https://old.smith.wiki): `andy.smith.wiki/<id>/` →
`old.smith.wiki/<id>/`. Built like `smith-wiki/cards-redirect`.

- `<id>/index.html` — one page per Card, served with 200, with the Card's
  title, description, and image, `rel=canonical` to the old.smith.wiki page,
  `location.replace` (keeps query and fragment) and `meta refresh`.
- `index.html`, `all/index.html` — the same for the home page and `/all/`.
- `404.html` — any other path, including Cards created after these pages were
  generated, redirects with `location.replace`.

`generate.mjs` writes the pages from a checkout of `smith-wiki/cards`
(`node generate.mjs ../cards`).

Temporary: when the new wiki takes over `andy.smith.wiki`, these pages move into
its build and this repository is retired.

GitHub Pages (deploy from branch `main`, `/`), custom domain `andy.smith.wiki`,
DNS `CNAME andy -> smith-wiki.github.io`.
