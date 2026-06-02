# ACV Rater Study

Self-contained rating form for the Algorithmic Cultural Vandalism rater study.

## Deploy on GitHub Pages

1. Create a new public GitHub repo (e.g. `acv-rater-study`)
2. Copy `index.html`, `stimuli/`, and (optional) this README into the repo root
3. In Settings → Pages, set Source = `main` branch, root folder
4. **Before deploying**, edit `index.html`:
   - Find `RESEARCHER_EMAIL` near the top of the `<script>` block
   - Replace `pietro.lugaro@example.com` with your real email
5. Wait 1–2 minutes; the site will be live at `https://<your-username>.github.io/acv-rater-study/`
6. Share that URL with raters

## What raters do

- Open the URL, enter a short pseudonym
- Rate 40 drawing pairs on a 1–5 scale (~15–20 minutes)
- At the end, click "Download results" and email you the JSON, OR click "Open in email" to launch their mail client

## What you do with the results

For each rater you receive a JSON file `acv_ratings_<pseudonym>.json` containing:
```json
{
  "schema": "acv-rater-v1",
  "raterId": "blue42",
  "completedAt": "2026-06-02T14:23:45.123Z",
  "nTrials": 40,
  "ratings": {"pair_001": 4, "pair_002": 2, ...}
}
```

Collect all these files into a folder, then run `analyze_ratings.py` (provided separately) to compute inter-rater reliability, descriptive stats, and the Real vs Shuffled comparison.

## Stimulus key

`stimuli/stimulus_key.csv` maps each `pair_id` to its condition (Real or Shuffled).
**Do not share this with raters.**
