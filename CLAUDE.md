# Platinum Ledger — notes for Claude

Single-file static web app (`index.html`), deployed to Netlify site `platinum-ledger` (id ae2d0956-55c1-421f-b720-28aebbeb2537). No build step; `netlify.toml` publishes the repo root.

## Session handoff
- Oct 30, 2026: Built as a claude.ai artifact, then packaged as an installable web app (manifest, service worker, icons) and deployed to https://platinum-ledger.netlify.app.
- Open item: entries are stored per device (localStorage). Cross-device sync is not built yet.

## Decisions and why
- One self-contained HTML file, vanilla JS, no framework: easy to edit and deploy, nothing to build.
- Design: dark navy + brass #dfa849, Lora headings + Inter body (Arnie's default app style).
- Credit catalog lives in the `BENEFITS` array in `index.html`; amounts verified against public sources Oct 30, 2026 (Oura reset timing and Sky Club reset date unverified, labeled in the UI).
- Storage: localStorage key `platinum-ledger-v1`; same JSON shape as the claude.ai artifact version, which synced through the artifact `db` capability. On Netlify that capability is absent, so the app falls back to device storage.
- Badges already earned on load are marked seen quietly, so returning users don't get a flood of pop-ups.
- Service worker is network-first for the page so updates appear on next open; `sw.js` and `index.html` are served no-cache.

## Compact Instructions
- Keep it one file; don't add a build step.
- Change credit amounts only in `BENEFITS`, and note the source/date.
- Never change the localStorage key or state shape without a migration in `hydrate()`.
- Bump `CACHE` in `sw.js` when changing cached files.
