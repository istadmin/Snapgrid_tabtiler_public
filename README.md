# SnapGrid — Tab Tiler

A lightweight, privacy-first browser extension that snaps your tabs and windows into perfectly aligned grid layouts. Built with Manifest V3 — works on **Chrome**, **Edge**, and all Chromium-based browsers.

## Features

### Layout Modes

| Layout | Description | Slots |
|--------|-------------|-------|
| **1x2** | Side by side (horizontal split) | 2 |
| **2x1** | Stacked vertically | 2 |
| **2x2** | Quad grid | 4 |
| **3 Rows** | Three horizontal strips | 3 |
| **3 Columns** | Three vertical columns | 3 |

### Tab Picker

Select exactly which tabs to arrange from a visual list grouped by browser window. Each tab displays its favicon and title for quick identification. The picker automatically limits your selection to match the chosen layout.

### Tile Existing Windows

Already working across multiple browser windows? Tile them directly into your chosen grid layout without splitting or moving tabs between windows.

### Drag-and-Drop Rearrangement

After arranging windows, use the interactive position grid to drag and drop windows between slots. Swap two windows instantly or move a window to an empty slot.

### Merge Back

Consolidate all open windows back into a single maximized browser window with one click.

### Multi-Monitor Support

Automatically detects which monitor your active window occupies and tiles within that display's available work area. Respects taskbar position across any number of connected monitors.

### Right-Click Context Menu

All five layout modes and the merge option are accessible from the extension icon's right-click context menu.

## Installation

### From Source (Developer Mode)

1. Clone or download this repository
2. Open your browser's extension page:
   - **Chrome:** `chrome://extensions`
   - **Edge:** `edge://extensions`
3. Enable **Developer mode** (toggle in the top-right corner)
4. Click **Load unpacked**
5. Select the project folder

### From Chrome Web Store

*(Link will be added once published)*

## Usage

1. Click the **SnapGrid** icon in your browser toolbar
2. Choose a layout: 1x2, 2x1, 2x2, 3 Rows, or 3 Columns
3. Select the tabs you want to arrange, or click **Tile Existing Windows**
4. Click **Arrange Selected Tabs** to snap them into place
5. Drag windows in the position grid to swap or move them
6. Click **Merge All to One Window** when you are done



## Permissions

| Permission | Purpose |
|---|---|
| `tabs` | Read tab titles and IDs to populate the tab picker |
| `system.display` | Detect monitor dimensions and positions for multi-monitor tiling |
| `contextMenus` | Add layout and merge options to the extension icon's right-click menu |

## How It Works

1. **Display detection** — Identifies which monitor the active window occupies by comparing the window's center-point against all connected display bounds.
2. **Grid calculation** — Divides the target monitor's `workArea` (which excludes the taskbar) into the chosen grid layout.
3. **Window management** — Creates new windows for selected tabs or repositions existing windows to fill the calculated grid cells.
4. **Swap and move** — Reads current window positions, matches them to grid slots, and allows swapping two windows or moving one to a different slot.
5. **Merge** — Moves all tabs from every open window into the active window, then maximizes it.

## Privacy

SnapGrid collects **zero** user data. No analytics, no tracking, no telemetry, no external network requests. All operations run entirely within your browser. See [privacy-policy.md](privacy-policy.md) for full details.

## Browser Compatibility

| Browser | Supported | Minimum Version |
|---------|-----------|-----------------|
| Google Chrome | Yes | 88+ |
| Microsoft Edge | Yes | 88+ |
| Brave | Yes | 88+ |
| Opera | Yes | 74+ |
| Vivaldi | Yes | 3.6+ |



## License

This project is private and not open source. No public license applies. If you have access, please do not redistribute or publish the code or resources without permission.
