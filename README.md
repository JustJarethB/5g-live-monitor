# 5G Live Monitor

**Live page: https://justjarethb.github.io/5g-live-monitor/**

A single-page, always-on network speed monitor for finding the best spot for a 5G router.
Open it on a phone with Wi-Fi off, press **Start**, and walk around.
Pick **Down**, **Both** or **Up**. The big number updates
4× a second (2-second rolling average) and a rolling graph shows the last 1, 5 or 30 minutes,
with dashed average and dotted peak lines for the visible window.
You can optionally tag spots to get a per-spot comparison table, and export a CSV.

Traffic goes to Cloudflare's public speed-test endpoints (`speed.cloudflare.com/__down` and `/__up`).

**Data use:** it keeps the link saturated, so it uses data at full line rate (about 2 GB/min at 300 Mbps).
It auto-stops at 10 GB by default; change that in Settings.

## How the GitHub Pages link works

GitHub Pages serves a repo at `https://<username>.github.io/<repo-name>/`, so this repo
(`JustJarethB/5g-live-monitor`) is served at https://justjarethb.github.io/5g-live-monitor/.
It publishes `index.html` from the root of the `main` branch (Settings → Pages), and each
push to `main` redeploys in a minute or two.
