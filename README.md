# rupifi-payments-preview

Deploy-only mirror for GitHub Pages. This repo intentionally contains nothing
but the built, password-protected page:

```
index.html   the entire app, AES-256-GCM encrypted, gated behind a password
.nojekyll    tells Pages to serve files as-is
robots.txt   disallows crawlers
```

There is no source code here — no React, no components, no design tokens. The
actual project lives in a separate private repository and is rebuilt and
copied into this one each time the preview needs to update. That separation
is deliberate: this repo can be public without exposing anything, because
`index.html` contains only ciphertext until the correct password is entered
in the browser.

To update the preview, from the source project:

```bash
npm run build:protected -- --password "..."
cp docs/index.html docs/.nojekyll docs/robots.txt /path/to/rupifi-payments-preview/
cd /path/to/rupifi-payments-preview
git add -A && git commit -m "Update preview" && git push
```
