# 5G Live Monitor

**Live page: https://justjarethb.github.io/5g-live-monitor/**

A single-page, always-on network speed monitor for finding the best spot for a 5G router.
Open it on a phone with Wi-Fi off, press **Start**, and walk around.
Pick **Down**, **Both** or **Up**. The big number updates
4× a second (2-second rolling average) and a rolling graph shows the last 1, 5 or 30 minutes,
with dashed average and dotted peak lines for the visible window.
You can optionally tag spots to get a per-spot comparison table, and export a CSV.

### Floor map (beta, opt-in)

Turn on **Floor map** in Settings to place readings on a 2D heatmap of 25 cm squares.
It tracks the phone's own position using the motion and orientation sensors (iPhone will ask
for Motion & Orientation access); up on the map is the way the phone faced when tracking started.

- **Moving the phone (arm, small shuffles):** acceleration is rotated into room coordinates using
  the phone's full 3D orientation and integrated into movement. Every time the phone comes to rest
  its true speed is zero, so the error that built up during the movement is known and the whole
  movement is corrected retroactively. Moving the phone out and back should settle where it started.
- **Walking:** the phone never rests mid-walk, so integration would drift; when steps are detected
  during a movement, step counting (with step length and per-stride direction) decides it instead.
- Speed readings taken while the phone is moving wait until it rests, then go onto the map at
  their corrected position. The best square (at least 2 s of readings) is outlined.

**Sensor log:** Floor map → Sensor log records raw sensor readings plus every decision the map made,
saved as JSON, so tracking can be replayed and tuned against real data.

## How the GitHub Pages link works

GitHub Pages serves a repo at `https://<username>.github.io/<repo-name>/`, so this repo
(`JustJarethB/5g-live-monitor`) is served at https://justjarethb.github.io/5g-live-monitor/.
It publishes `index.html` from the root of the `main` branch (Settings → Pages), and each
push to `main` redeploys in a minute or two.
