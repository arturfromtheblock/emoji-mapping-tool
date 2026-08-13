# Emoji Mapping Tool

A browser-based tool for highlighting areas in images and assigning emojis to those highlights. Ideal for physical challenges, data annotation, games, or any use case where visual areas need to be linked to symbols. Created to participate in the Phy Challenge on the BitcoinTalk forum.

Link: https://bitcointalk.org/index.php?topic=5584952.0$0

<img src="https://raw.githubusercontent.com/arturfromtheblock/emoji-mapping-tool/refs/heads/master/1.png">

<img src="https://raw.githubusercontent.com/arturfromtheblock/emoji-mapping-tool/refs/heads/master/2.png">

---

## 🚀 Features

### Image Management
- **Load images** via file upload (`📂 Picture`) or direct URL input
- **Zoom** from 20% to 800% using buttons or `Ctrl/Cmd + Scroll`
- **1:1 view** for native pixel size
- Status bar shows image dimensions, zoom level, and marker count

### Markers (Boxes)
- **Draw a box**: Drag on empty canvas area
- **Move a box**: Click and drag an existing box
- **Edit a box**: Double-click opens the emoji picker
- **Delete a box**: `Delete` key or the "Delete" button in the sidebar
- **Alt + Drag**: Draw a new box over an existing one
- Manual coordinate input (X, Y, Width, Height) in the sidebar
- Auto-center on the selected box

### Emoji Assignment
- Built-in **emoji picker** with 3,000+ Apple emojis
- **Search** by emoji name (e.g. "cat", "police", "heart")
- **Category filter** (Smileys, Animals, Food, Activities, Travel, Symbols, ...)
- Direct emoji input supported (e.g. via `⌘ + Ctrl + Space` on macOS)
- Live preview of the cropped image region inside the picker

### Sorting
Markers can be re-sorted and re-numbered by different criteria:

| Mode | Description |
|------|-------------|
| **Angle** | Angle from image center (0° at top, clockwise) |
| **Radius** | Distance from image center (inside → outside) |
| **Reading lines** | Reading order (top → bottom, left → right) with row tolerance |
| **only X** | By X coordinate only (left → right) |
| **only Y** | By Y coordinate only (top → bottom) |

### Data Export
- **CSV export** with extensive metadata per marker:
  - ID, coordinates (x, y, w, h)
  - Center (cx, cy)
  - Polar coordinates (angle in °, radius)
  - Assigned emoji (character, name)
  - Codepoints (hex, binary)
  - UTF-8 encoding (hex, binary)
- **Save / load projects** as JSON (including all boxes and settings)
- **Sequence display** of assigned emojis as:
  - UTF-8-Hex
  - UTF-8-Binary
  - Codepoint-Hex
- One-click copy of sequences to clipboard

---

## 📦 Usage

Since this is a pure HTML/CSS/JS application, no installation is required.

### Local Use
```bash
# Clone repository
git clone https://github.com/arturfromtheblock/emoji-mapping-tool.git
cd emoji-mapping-tool

# Simply open the HTML file in your browser
EMT.html
```

Use the files located in the 'Phy Challenge Data' folder. Load pic.png into the mapping tool, select 'Load project file' and then click to select 'project_file.json' to load all the data.

You can easily save your progress to a new JSON file.


> **Note:** An internet connection is required for the emoji picker, as Apple emoji data is loaded from jsDelivr (`emoji-datasource-apple`). All other features work completely offline.

---

## 🖱️ Controls

| Action | Control |
|--------|---------|
| Draw new box | Left-click drag on empty area |
| Move box | Left-click drag on box |
| Draw over box | `Alt` + left-click drag |
| Change emoji | Double-click on box |
| Select box | Single-click on box |
| Delete box | `Delete` / `Backspace` or "Delete" button |
| Zoom | `Ctrl/Cmd + mouse wheel` or +/- buttons |
| Close emoji picker | `Escape` or click outside |

---

## 🗂️ Project Structure

```
emoji-mapping-tool/
├── EMT.html          # Complete application (HTML + CSS + JS)
└── README.md         # This file
```

> The entire application is contained in a single HTML file — no external dependencies except the emoji database (CDN).

---

## 📊 CSV Export Format

The CSV export contains the following columns:

| Column | Description |
|--------|-------------|
| `id` | Running number of the marker |
| `x`, `y`, `w`, `h` | Bounding box (top-left, width, height) |
| `cx`, `cy` | Center of the box |
| `angle_deg` | Angle from image center in degrees |
| `radius` | Distance from image center in pixels |
| `char` | Assigned emoji |
| `name` | Emoji name (e.g. "grinning face") |
| `cp_hex` | Codepoints as hex (e.g. `1F600`) |
| `cp_bin` | Codepoints as binary |
| `utf8_hex` | UTF-8 encoding as hex |
| `utf8_bin` | UTF-8 encoding as binary |

---

## 🛠️ Technical Details

- **Pure Vanilla JavaScript** — no frameworks, no build tools
- **File API** for local file operations (image loading, project loading)
- **Blob API** for CSV and JSON downloads
- **Clipboard API** for copying sequences (with `execCommand` fallback for HTTP contexts)
- **Intl.Segmenter** for correct emoji grapheme detection
- **CSS Transform** for performant zooming
- **Lazy Loading** for emoji images in the picker

### External Resources (CDN)
- `emoji-datasource-apple` from jsDelivr for emoji metadata and images

---

## 📝 Use Cases

- **Physics challenges**: Emojis as solution keys for image puzzles
- **Data annotation**: Visual marking and classification of objects
- **Escape rooms**: Image-based puzzles with emoji codes
- **Learning tools**: Interactive matching exercises
- **Game development**: Rapid prototyping of sprite mappings

---

## 📄 License

MIT License — see [LICENSE](LICENSE).

---

## 🤝 Donate

```text
bc1qlpdkr5djv0mpz948wh2dutq48qnaazaauxxlh0
```
