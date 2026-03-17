# ☠ HORMUZ MINEFIELD

A Minesweeper-inspired browser game set in the Strait of Hormuz. Clear sea mines to open safe passage for oil tankers while the IRGCN watches closely.

## Play

**[GitHub Pages Link]** - Deploy and play directly in your browser.

## How to Run Locally

```bash
# Using Python
python3 -m http.server 8080

# Then open http://localhost:8080
```

No build step required — single HTML file with CDN dependencies.

## Gameplay

- **Click** to reveal a cell
- **Right-click** or toggle Flag mode to mark suspected mines
- Clear all water cells without detonating a mine to win
- First click is always safe (3×3 zone cleared)

## Difficulties

| Mode | Mines | Description |
|------|-------|-------------|
| Easy | 22 | Light minefield |
| Medium | 42 | Standard patrol |
| Hard | 65 | Heavy deployment |
| Realistic | 42 + escalating | On win, Iran remotely deploys fresh mines each wave |

## Features

- 🗺️ Real map of the Strait of Hormuz (Leaflet + CartoDB Voyager tiles)
- 🎯 Accurate shoreline masking — only water cells are playable
- ⏱️ Timer and mine counter
- 🌊 Wave escalation in Realistic mode
- 📡 IRGCN news ticker with procedurally generated updates

## Tech Stack

- Single HTML file (~400 lines)
- Leaflet.js 1.9.4 (map rendering)
- CartoDB Voyager tiles (light theme basemap)
- Vanilla JavaScript, no frameworks

## Deployment (GitHub Pages)

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Enable Pages from the `main` branch root
4. Your game will be live at `https://<username>.github.io/<repo>/`

## License

Public domain / MIT — use it however you want.

---

*"The situation is being monitored." (It always is.)*
