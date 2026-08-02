# Rupifi Payments Dashboard — Live Preview

A hosted preview of a dashboard I built as a portfolio piece: a pixel-accurate
implementation of Payments, Invoices, Customers, Bulk Actions and Workflow
screens from a Figma design, in React + TypeScript.

**[View the live preview →](https://ranjuravindran.github.io/kuki-design-system-test/)**

It's password-protected, not because anything is hidden, but because the
underlying design is a real product and this preview isn't meant to be
publicly indexed or crawled. Ask me for the password if you'd like to look.

## What's in this repo

Just the built output — no source code:

```
index.html   the built app
.nojekyll    tells GitHub Pages to serve files as-is
robots.txt   disallows crawlers
```

The app itself is encrypted client-side (AES-256-GCM, password-derived key)
so the page is inert without the password — decryption happens entirely in
your browser and nothing is sent anywhere. The actual source (React
components, Figma tokens, etc.) lives in a separate private repository and
gets rebuilt into this one each time the preview updates:

```bash
npm run build:protected -- --password "..."
cp docs/index.html docs/.nojekyll docs/robots.txt /path/to/rupifi-payments-preview/
cd /path/to/rupifi-payments-preview
git add -A && git commit -m "Update preview" && git push
```
