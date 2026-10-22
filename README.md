# Japan Morning Brief

Public, mobile-friendly dashboard for the Japan trip.

## Website

Once GitHub Pages is enabled under **Settings → Pages → Build and deployment → Deploy from a branch → main / (root)**, the public URL is:

https://ktbeck22.github.io/morning-brief/

The main page loads the newest report from `briefs/index.json` by default. A dropdown navigates earlier reports. Linking to `?date=2026-10-22` selects a dated report.

## Adding each morning's report

1. Create `briefs/YYYY-MM-DD.json` following the field structure of `briefs/2026-10-22.json`.
2. Add an entry to `briefs/index.json` with `date`, `file`, and `label`.
3. Commit both files. The website reads the manifest and selects the latest date.

Each report may contain calendar event titles and descriptions, but **do not publish booking numbers, excursion IDs, private contact information, calendar authentication tokens, or confidential notes**. Verify that linked sources are public HTTPS URLs.

### Publishing automation status

**Not yet automated.** The existing ChatGPT scheduled task can generate the daily brief, but it does not automatically push its output to this repository. The repository's GitHub Pages serving is independent of report generation. Automating publication requires an authorized source of each day's report (or a separate scheduled generator with appropriate calendar and weather credentials). Do not commit OAuth credentials or API keys in this public repository.

### Files

- `index.html`: responsive website
- `briefs/index.json`: archived report manifest
- `briefs/YYYY-MM-DD.json`: daily snapshots
