# 5G Live Monitor

**Live page: https://justjarethb.github.io/5g-live-monitor/**

A single-page, always-on network speed monitor for finding the best spot for a 5G router.
Open it on a phone with Wi-Fi off, press **Start**, and walk around.
Pick **Down**, **Both** or **Up**. The big number updates
4× a second (2-second rolling average) and a rolling graph shows the last 1, 5 or 30 minutes,
with dashed average and dotted peak lines for the visible window.
You can optionally tag spots to get a per-spot comparison table, and export a CSV.

### Floor map (beta, opt-in)

Turn on **Floor map** in Settings to place readings on a 2D heatmap of 25 cm squares as you walk.
It works on iPhone and Android, using step counting from the accelerometer and the phone's
orientation sensors (iPhone will ask for Motion & Orientation access). Set your step length
in Settings for best results. Because it's dead reckoning, position drifts by roughly 5–10%
of the distance walked; walk back to the start point to see how far it has drifted. Up on the map is the
direction you faced when you pressed Start tracking / Reset map. The best square (at least
2 s of readings) is outlined.

Traffic goes to Cloudflare's public speed-test endpoints (`speed.cloudflare.com/__down` and `/__up`).

**Data use:** it keeps the link saturated, so it uses data at full line rate (about 2 GB/min at 300 Mbps).
It auto-stops at 10 GB by default; change that in Settings.

## How the GitHub Pages link works

GitHub Pages serves a repo at `https://<username>.github.io/<repo-name>/`, so this repo
(`JustJarethB/5g-live-monitor`) is served at https://justjarethb.github.io/5g-live-monitor/.
It publishes `index.html` from the root of the `main` branch (Settings → Pages), and each
push to `main` redeploys in a minute or two.
