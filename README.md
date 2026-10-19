# Keeta Karnival — Performance Monitoring Dashboard

Interactive, self-contained HTML dashboard for the Keeta Karnival UAE campaign
(15 Oct 2026 → · Meta / TikTok / Snapchat / GDN / YouTube).

**View:** open `index.html` — data is embedded as a JSON snapshot; no external
dependencies, no build step.

## Structure

- `index.html` — the dashboard (protected template + embedded `karnival-data` snapshot)
- Data refreshed from `SoMe_Master_Repository.xlsx` (central data file); only the
  embedded JSON snapshot changes between refreshes.

## Refresh procedure

1. Append new day(s) to the master workbook (SoMe pipeline, 5:30 AM Dubai).
2. Rebuild the embedded JSON snapshot per the data contract (13 locked plans,
   4 activations, dedup rules for QR campaign data).
3. Inject the new snapshot into a copy of the template; everything outside the
   `karnival-data` script block must remain byte-identical.
4. Validate (record counts, workbook reconciliations, browser click-through)
   before committing.

## Deploy

GitHub Pages — main branch / root:
https://shawncaramol-droid.github.io/keeta-karnival-dashboard/
