# ☠ HORMUZ MINEFIELD

A Minesweeper-inspired browser game set in the Strait of Hormuz. Clear sea mines to open safe passage for oil tankers while the IRGCN watches closely.

## Play

**[▶ Play Now](https://naklitechie.github.io/hormuz-minesweeper/)** — Runs directly in your browser.

⭐ **Like it?** Give this repo a star!

## Run Locally

Just open `index.html` in any modern browser. No server needed.

```bash
# Option 1: Double-click the file
open index.html

# Option 2: If you prefer a local server
python3 -m http.server 8080
# Then open http://localhost:8080
```

No build step, no dependencies — single HTML file (~400 lines).

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

## License

Public domain / MIT — use it however you want.

---

## Built With

Created in a couple of hours with **Claude** and **Qwen** AI assistants.

---

*"The situation is being monitored." (It always is.)*
