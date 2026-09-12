# Klingenberg — indhold

This repository holds the restaurant content for Klingenberg Food, edited through
[Pages CMS](https://pagescms.org). It contains text and photos only.

## What is here

- `.pages.yml` — the Pages CMS editing setup (Danish labels, field rules, media limits).
- `content/site/**` — the content itself, one JSON file per part of the site.
- `public/photos/**` — the photographs the content refers to.
- `.github/workflows/cms-content-trigger.yml` — the publishing trigger, described below.

## How an edit reaches the site

Pages CMS commits edits to `main`. When a push to `main` changes anything under
`content/site/**` or `public/photos/**`, the trigger asks
[myimaginarii/klingenberg-food](https://github.com/myimaginarii/klingenberg-food) to
run its publisher. Changes to anything else here (`.pages.yml`, this README,
`.github/`) publish nothing.

Production reads those two folders as data, validates them, and publishes through its
own protected pull request and CI. Content that fails validation does not go live.

## What is not here

Application code, the build, the deployment and the production publisher's
credentials live in klingenberg-food, not here.

The only credential in this repository is the Actions secret
`PRODUCTION_DISPATCH_TOKEN`: a token limited to klingenberg-food with Actions
permission only. It can ask production to start a publication run, and nothing else.
No other tokens, keys or environment files belong in this repository.
