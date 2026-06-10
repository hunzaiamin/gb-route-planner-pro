# GB Route Planner Pro PWA

This folder contains the installable PWA version of the Gilgit-Baltistan Route Planner Pro learning app.

The Pro version adds an Excel-friendly `road-status.csv` sheet that can drive route status warnings, SVG map markings, and route calculation behavior.

## Files

- `index.html` — main planner
- `road-status.csv` — Excel-friendly road closure, landslide, and high-pass status sheet
- `manifest.webmanifest` — Android/Chrome app installation settings
- `service-worker.js` — offline caching
- `icons/` — Android home-screen icons

## Road status sheet

Open `road-status.csv` in Excel and keep these columns:

```csv
from,to,status,severity,type,title,source,source_url,updated_at,valid_until,note
```

Supported status values:

- `open` — normal route behavior
- `caution` — route remains available but receives higher planning risk
- `closed` — route segment is avoided
- `unknown` — route remains available but displays uncertainty

## GitHub Pages deployment

1. Create a new GitHub repository, for example: `gb-route-planner-pro`.
2. Upload all files in this folder to the root of the repository.
3. Go to repository Settings.
4. Open Pages.
5. Under Build and deployment, select:
   - Source: Deploy from a branch
   - Branch: main
   - Folder: /root
6. Save.
7. Wait a few minutes for GitHub Pages to publish the site.
8. Open the published GitHub Pages link on Android Chrome.
9. Tap the three-dot menu and select Add to Home screen or Install app.

## Android install note

The PWA must be opened from an HTTPS link, such as GitHub Pages. Opening `index.html` directly from phone storage may show the planner, but normally will not install as a proper PWA.
