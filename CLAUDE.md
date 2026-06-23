# CLAUDE.md — Social Style assessment

## What this is
A single self-contained `index.html` — a 2-minute employee self-assessment that maps people
onto the Merrill & Reid **Social Styles** model (Analytical / Driving / Amiable / Expressive).
No build step, no framework, no backend. Recreates social-styles.firebaseapp.com.

## Where it runs
- Repo: `Talos91/employees-social-style`, branch `main`, GitHub Pages served from root `/`.
- Live: https://talos91.github.io/employees-social-style/
- Push to `main` → Pages auto-redeploys in ~1 min. There is no CI.
- Local working copy lives at `C:\Users\itisf\social-styles\` (folder name differs from repo — harmless).

## How it works (all in index.html)
- `ITEMS` array: 10 paired statements. `axis:"A"` = Assertiveness (asks↔tells),
  `axis:"R"` = Responsiveness (controls↔shows emotion). 5 of each.
- Each item rated 1–8. Score = average per axis (1–8). Midpoint 4.5 splits the 2×2:
  - asks + controls → Analytical · tells + controls → Driving
  - asks + shows → Amiable · tells + shows → Expressive
- `STYLES` object holds each style's description, strengths, watch-outs, and "work with me" tips.

## Common edits
- **Change where results are emailed:** edit `SEND_RESULTS_TO` near the top of the `<script>`.
- **Reword a question:** edit the `ITEMS` array (keep the `axis` value correct).
- **Change style copy:** edit the `STYLES` object.

## Verifying a change
Serve locally (`python -m http.server` in this folder) and walk the flow, or just push and
load the live URL. Scoring logic was validated by driving all four corners of the grid.

## Not done yet
Results only come back via the employee clicking "Email my result back" (mailto). No automatic
collection — see ROADMAP.md.
