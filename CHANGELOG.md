# Changelog

## 2026-06-23 — v1.1 (team board)
- Added a shared **team board**: opt-in "Add me to the team board" plots everyone as a colored
  dot (by style) with their name on the 2×2 grid; your own dot is highlighted.
- Pluggable storage layer: **Firebase Firestore** when `FIREBASE_CONFIG` is filled in (real-time,
  shared), otherwise **local demo mode** with seeded sample dots (per-browser).
- Names rendered via `textContent` (no HTML injection); dots de-duplicated by name (latest wins),
  with deterministic jitter so identical scores don't overlap.
- See README "Team board" for the 5-minute Firebase setup.

## 2026-06-23 — v1.0 (initial release)
- Recreated the social-styles.firebaseapp.com assessment as a single self-contained `index.html`.
- 10 paired statements, 1–8 clickable scale (replaces the original's dropdowns).
- Scores Assertiveness + Responsiveness, plots the result on a 2×2 Social Styles grid with an
  animated marker and highlights the winning quadrant.
- Per-style result page: description, strengths, watch-outs under pressure, and
  "how teammates can work best with you" tips.
- "Email my result back" (mailto), "Copy summary", and "Save as PDF" actions; optional name field.
- Editorial design: Fraunces + Hanken Grotesk, warm paper theme, responsive + print styles.
- Deployed to GitHub Pages at https://talos91.github.io/employees-social-style/
