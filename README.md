# 5G Live Monitor

A single-page, always-on network speed monitor for finding the best spot for a 5G router.
Open it on a phone with Wi-Fi off, press **Start**, and walk around. The big number updates
4× a second (2-second rolling average) and a rolling graph shows the last 1, 5 or 30 minutes.
You can optionally tag spots to get a per-spot comparison table, and export a CSV.

Traffic goes to Cloudflare's public speed-test endpoints (`speed.cloudflare.com/__down` and `/__up`).

**Data use:** it keeps the link saturated, so it uses data at full line rate (about 2 GB/min at 300 Mbps).
It auto-stops at 10 GB by default; change that in Settings.
