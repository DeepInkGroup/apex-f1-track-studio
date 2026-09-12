<div align="center">

# APEX — F1 Track Studio

**Design, configure, and export Formula-style racing circuits directly in the browser.**

[![Deploy to GitHub Pages](https://github.com/DeepInkGroup/apex-f1-track-studio/actions/workflows/pages.yml/badge.svg)](https://github.com/DeepInkGroup/apex-f1-track-studio/actions/workflows/pages.yml)
![Vanilla JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?logo=javascript&logoColor=111)
![Zero dependencies](https://img.shields.io/badge/runtime_dependencies-0-d8ff38)

[Open the live editor](https://deepinkgroup.github.io/apex-f1-track-studio/) · [Report an issue](https://github.com/DeepInkGroup/apex-f1-track-studio/issues)

</div>

## Overview

Apex is a responsive, dependency-free circuit editor inspired by modern motorsport timing graphics. It combines a precise canvas renderer with a compact race-control interface, allowing users to create a track and prepare a presentation-ready circuit map without installing design software.

The road, racing line, markers, sectors, and corner labels remain editable throughout the design process. Projects are saved automatically in the browser and can be exported as PNG images.

## Highlights

| Area | Capabilities |
| --- | --- |
| Circuit design | Draw smooth layouts, move control points, delete corners, and optionally auto-connect the finish to the start |
| Racing line | Exact center-path rendering, three editable sectors, selectable palettes, and adjustable line width |
| Circuit profile | Editable name, circuit code, country code, location, and driving direction |
| Race features | Place, rename, reposition, convert, or remove DRS zones and speed traps |
| Drive simulation | Accelerate, brake, steer across the track surface, complete timed laps, and restart instantly |
| Presentation | Corner numbering, adjustable road and edge widths, grid control, and watermarked PNG export |
| Workflow | Undo/redo history, responsive layout, local autosave, and automatic GitHub Pages deployment |

## Quick start

No package installation or build step is required.

```bash
git clone https://github.com/DeepInkGroup/apex-f1-track-studio.git
cd apex-f1-track-studio
python -m http.server 4189
```

Open [http://127.0.0.1:4189](http://127.0.0.1:4189) in a modern browser.

## Editor workflow

1. Select **New Blank Track**.
2. Click the canvas to create control points, then double-click to finish.
3. Use **Edit** to reshape the circuit by dragging its control points.
4. Use **Sectors** or the sector sliders to position the second and third sector boundaries.
5. Select **DRS** or **Trap** to add race markers. Select an existing marker to edit or drag it.
6. Customize the circuit profile and track appearance in the inspector.
7. Select **Drive This Circuit** to simulate laps on any completed circuit.
8. Select **Export PNG** to save the circuit map with its APEX watermark.

### Useful controls

| Control | Action |
| --- | --- |
| `Ctrl/Cmd + Z` | Undo |
| `Ctrl/Cmd + Shift + Z` | Redo |
| `Delete` / `Backspace` | Remove the hovered corner or selected marker |
| `Escape` | Return to Edit mode |
| Double-click | Finish the current track |

### Drive controls

| Control | Action |
| --- | --- |
| `W` / `↑` | Accelerate |
| `S` / `↓` | Brake |
| `A` `D` / `←` `→` | Move across the track surface |
| `R` | Restart the current simulation |
| `Escape` | Exit Drive mode |

Touch controls appear automatically on mobile and other coarse-pointer devices. The drive HUD reports current speed, lap number, and live lap time.

## Rendering architecture

Apex uses a single sampled cubic Bézier center path for the road, racing line, sector boundaries, marker anchors, and distance calculation. Sharing one geometry source keeps the racing line contained within the track—even through tight corners—and avoids duplicate or offset paths.

The application is intentionally small:

```text
.
├── index.html                  # Accessible application structure
├── styles.css                 # Responsive race-control interface
├── app.js                     # Canvas renderer and editor state
└── .github/workflows/pages.yml # GitHub Pages deployment
```

There are no runtime dependencies, frameworks, cookies, analytics, or remote data services. Project data is stored only in the browser through `localStorage`.

## Deployment

Pushes to `main` are deployed automatically by GitHub Actions. The workflow uploads the static repository contents and publishes them to GitHub Pages.

Production: **https://deepinkgroup.github.io/apex-f1-track-studio/**

## Browser support

Apex targets current desktop and mobile versions of Chrome, Edge, Firefox, and Safari with support for the Canvas 2D API and `Path2D`.

## Contributing

Issues and focused pull requests are welcome. For visual changes, include a short explanation and a before/after capture. For interaction changes, describe the expected pointer and keyboard behavior.
