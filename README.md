# Apex F1 Track Studio

An interactive, browser-based Formula 1 circuit designer inspired by modern race-control graphics. Draw and reshape a circuit, divide it into sectors, place DRS detection zones and speed traps, edit its profile, and export the finished map as a PNG.

## Features

- Smooth point-based circuit drawing and editing
- Optional automatic start/finish connection
- Automatic three-sector racing line with contained sector boundaries
- Toggleable corner numbers
- Editable circuit name, three-letter code, country, location, and direction
- DRS and speed-trap placement
- Track-width and sector-palette controls
- Undo, redo, local autosave, and PNG export
- Responsive interface with no build step or runtime dependencies

## Run locally

```bash
python -m http.server 4189
```

Then open `http://127.0.0.1:4189/`.

## Deployment

Every push to `main` deploys the static site to GitHub Pages through the included Actions workflow.
