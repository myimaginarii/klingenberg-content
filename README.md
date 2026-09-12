# Klingenberg — indhold

This repository holds the restaurant content for Klingenberg Food, edited through
[Pages CMS](https://pagescms.org). It contains text and photos only.

## What is here

- `.pages.yml` — the Pages CMS editing setup (Danish labels, field rules, media limits).
- `content/site/**` — the content itself, one JSON file per part of the site.
- `public/photos/**` — the photographs the content refers to.

## What is not here

Application code, the build and the deployment live in
[myimaginarii/klingenberg-food](https://github.com/myimaginarii/klingenberg-food).

This repository must never contain production credentials — no tokens, no keys,
no environment files.

Production publishing is not connected to this repository yet. Editing here does
not change the live site.
