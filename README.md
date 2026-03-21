# ☠ STRAIT COMMAND

A Minesweeper-inspired browser game set in strategic maritime chokepoints. Clear sea mines to open safe passage for oil tankers while hostile forces watch closely.

## Play

**[▶ Play Now](https://naklitechie.github.io/strait-command/)** — Runs directly in your browser.

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

No build step, no dependencies — single HTML file (~500 lines).

## Gameplay

- **Click** to reveal a cell
- **Right-click** or toggle Flag mode to mark suspected mines
- Clear all water cells without detonating a mine to win
- First click is always safe (3×3 zone cleared)

## Maps

| Map | Location | Threat |
|-----|----------|--------|
| 🗺️ Strait of Hormuz | Persian Gulf | IRGCN patrols |
| 🗺️ Bab el-Mandeb Strait | Red Sea / Yemen | Houthi rebels |
| 🗺️ Malacca Strait | Singapore Strait / Malaysia | Pirates |
| 🗺️ Taiwan Strait | Taiwan / China | PLA |

## Difficulties

| Mode | Mines | Description |
|------|-------|-------------|
| Easy | 22 | Light minefield |
| Medium | 42 | Standard patrol |
| Hard | 65 | Heavy deployment |
| Realistic | 42 + escalating | On win, enemies remotely deploy fresh mines each wave |

## Features

- 🗺️ Multiple real-world chokepoint maps (Leaflet + CartoDB Voyager tiles)
- 🎯 Accurate shoreline masking — only water cells are playable
- ⏱️ Timer and mine counter
- 🌊 Wave escalation in Realistic mode
- 📡 Dynamic news ticker with region-specific updates

## Tech Stack

- Single HTML file (~500 lines)
- Leaflet.js 1.9.4 (map rendering)
- CartoDB Voyager tiles (light theme basemap)
- Vanilla JavaScript, no frameworks

---

## 🤖 For Agents: Adding New Maps

Want to remix this game with new chokepoint maps? Here's how:

### The Auto-Sampler Tool

Open `auto-sampler.html` in your browser. This tool:

1. **Loads the map** at a specific lat/lng and zoom level using Leaflet + CartoDB tiles
2. **Locks the view** to prevent scrolling/zooming
3. **Samples tile colors** to detect water vs land:
   - Water = blue-dominant pixels (B > R + 15)
   - Land = cream/white pixels (high RGB, R ≥ B)
4. **Generates a 35×19 mask** array where `0` = water, `1` = land
5. **Outputs the mask** ready to paste into `index.html`

### Adding a New Chokepoint

1. **Pick a location** (e.g., Suez Canal, Panama Canal, Malacca Strait)
2. **Find coordinates** that show the chokepoint clearly at zoom 8-9
3. **Edit `auto-sampler.html`**:
   - Change `center: [lat, lng]` to your coordinates
   - Adjust `zoom` level (8-10 works best)
4. **Run the sampler**:
   - Wait for tiles to load
   - Click "🔒 LOCK MAP"
   - Click "🤖 AUTO-DETECT WATER"
   - Adjust threshold if needed
   - Manually fix any errors by clicking cells
5. **Add to `index.html`**:
   - Copy the generated mask
   - Add a new entry to the `MAPS` object with:
     - `name`: Display name
     - `subtitle`: Tagline for the map
     - `center`: [lat, lng] for the map view
     - `zoom`: Zoom level (8-10)
     - `mask`: Your sampled mask array
     - `ticker`: Region-specific news messages (8-12 items)
   - Add map-specific win/lose messages
6. **Add map selector option** in the HTML dropdown

### Example Coordinates

| Chokepoint | Coordinates | Zoom | Status |
|------------|-------------|------|--------|
| Strait of Hormuz | [26.4, 56.5] | 8 | ✅ Added |
| Bab el-Mandeb | [12.65, 43.35] | 9 | ✅ Added |
| Malacca Strait | [2.5, 101.5] | 8 | ✅ Added |
| Taiwan Strait | [24.3, 119.4] | 8 | ✅ Added |
| Suez Canal | [30.0, 32.3] | 9 | _Ready to add_ |
| Panama Canal | [9.1, -79.6] | 9 | _Ready to add_ |
| Bosphorus | [41.1, 29.1] | 10 | _Ready to add_ |

### Tips

- **Zoom level matters**: Higher zoom = more detail, smaller coverage
- **Threshold adjustment**: If auto-detect misses water, increase threshold; if it detects too much, decrease
- **Manual cleanup**: Always review and click to fix stray cells
- **Test alignment**: The grey overlay should match visible coastline

---

## See Also

**[Chokepoint](https://github.com/NakliTechie/chokepoint)** — same maps, different genre. A tower defense game where you build coastal batteries and hold the strait against waves of enemy ships.

---

## License

Public domain / MIT — use it however you want.

---

## Built With

Created in a couple of hours with **Claude** and **Qwen** AI assistants.

---

*"The situation is being monitored." (It always is.)*
