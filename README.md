# 🧵 Filament Tracker

A Progressive Web App (PWA) for managing your 3D printer filament inventory. Single-file HTML app — no server, no dependencies, no framework.

## Features

### Inventory Management
- **Add, edit, delete** filaments with full details (brand, type, color, hex, temperatures, speed, drying, notes)
- **Spool quantity** tracking with inline +/− controls
- **Status system** — New, In Use, Finished (auto-sets qty to 0 when finished)
- **Rating system** — Bad, Good, Favorite
- **Duplicate detection** — same color/brand/type auto-merges by adding qty
- **Photo upload** with color hex pastille overlay
- **Custom brands** — unknown brands auto-added to the list

### Views & Filters
- **List / Grid** toggle
- **Image / Color hex** toggle
- **Multi-select filters** — filter by multiple brands, types, and statuses simultaneously
- **Sort** by hue, color, brand, type, percentage, quantity, status, or rating
- **Search** with instant results
- **Out-of-stock** filaments (qty=0) displayed greyed out

### Project Palette
- **Pin filaments** to a project palette from the inventory
- **Dedicated project tab** showing selected filaments with full specs
- **Color swatch bar** for quick visual reference

### Import / Export
- **JSON import** with duplicate merging
- **JSON & CSV export** (full inventory or selection)
- **Bulk select** mode for multi-operations

### Mobile & PWA
- **Installable** as a standalone app on Android & iOS
- **Offline capable** via Service Worker
- **Responsive** sticky toolbar, compact stats on mobile
- **Status badge hidden** on mobile, replaced by colored progress bar

## Quick Start

### Option 1 — Local
1. Download `index.html`
2. Open in any browser

### Option 2 — GitHub Pages
1. Create a repo on GitHub
2. Add `index.html` to the root
3. Enable GitHub Pages (Settings → Pages → Deploy from `main`)
4. Access at `https://your-username.github.io/your-repo/`
5. On mobile Chrome, tap "Install" or "Add to Home Screen"

## Data Storage

All data is stored in **localStorage** — nothing leaves your device.

| Key | Content |
|---|---|
| `ft-data` | Filament inventory (without images) |
| `ft-brands` | Custom brand list |
| `ft-palette` | Project palette selection |
| `fi-{id}` | Individual filament photos (base64) |

## Tech Stack

- **Zero dependencies** — vanilla HTML/CSS/JS
- **Single file** — everything in one `index.html`
- **PWA** — manifest + service worker generated at runtime
- **~45KB** total (uncompressed)

## Default Filaments

Ships with 6 Bambu Lab sample filaments (PLA Matte, PLA Basic, PLA Silk+). Use 🔄 Reset to restore defaults.

## Version

**v2.0.0**

## License

MIT
