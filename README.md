# Housekeeping Room Assignment

Offline PWA for daily housekeeping room assignment: floor rotation (no one repeats yesterday's floor), seniority-weighted checkout/double-bed splits, hard caps (14 checkouts / 16 rooms per person per day), departure + in-house list import (text/PDF), printable per-housekeeper sheets, CSV export.

Live: https://arshcheema4570.github.io/housekeeping-assigner/

## Privacy

This public version ships with **generic placeholder staff** (Staff 1–7) and an empty history. Real names are never in the repo. Use the **Rename** button on the Staff tab to allocate actual names — they are stored only in your browser's localStorage, on your device, and never leave it.

## Rules engine

- Floor rotation: nobody repeats yesterday's floor (Floor 1 → Split or Floor 2).
- Daily working-housekeeper selection + previous 3 days for fairness.
- Odd checkouts / double beds go to the most senior working housekeepers.
- Seniority list is editable (add / remove / re-rank / rename).
- Hard caps: max 14 checkouts and max 16 total rooms per housekeeper per day; overflow is flagged as blocked-for-tomorrow.
- Room codes: NQQ5/NQQ1 (2-queen), NQ1/NQ5 (1-queen), NK5 (king), NHQ1 (accessible).

## Build

The app is generated from `template.html` + `scheduler.js` (see the private build setup). The public build is produced by `build-github.js`, which swaps in placeholder staff, drops the pre-loaded history, and wires the PWA shell. Fully offline — zero external URLs.
