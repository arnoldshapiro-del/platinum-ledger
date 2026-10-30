# Platinum Ledger

A phone-friendly web app that tracks every Amex Platinum credit: how much it's worth, the exact window to use it, what you've used, and what's left. It has five screens (Today, Credits, Calendar, Perks, Wins) with progress rings, a color-coded year calendar, a welcome-bonus tracker, a lounge counter, badges and confetti.

- Live: https://platinum-ledger.netlify.app
- One file app: `index.html` (no build step). `sw.js` + `manifest.webmanifest` make it installable to a phone home screen.
- Data is saved in the browser on each device (localStorage key `platinum-ledger-v1`).
- Credit amounts checked against public sources on Oct 30, 2026. The Amex app's Benefits tab is the final word.
