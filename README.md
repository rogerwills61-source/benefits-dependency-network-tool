# BDN Studio

A zero-clutter, keyboard-first, 60 FPS cross-platform Progressive Web App (PWA) for building, validating, and auto-tidying Benefits Dependency Networks (BDNs), deployed as a single self-contained `index.html` with no external runtime dependencies.

## Key Capabilities

- **Continuous Multi-Column Workspace:** Supports 4 default columns (*Enablers*, *Business Changes*, *Benefits*, *Strategic Objectives*) expandable to 6–7+ columns, with sticky word-wrapped column headers, drag-and-drop or button column reordering, and *Compact*, *Comfortable*, and *Spacious* map spacing presets.
- **Canonical Zero-Split-Link Layout Solver:** Idempotent layout tidying with support for `✋ Manual` adjustments, `📌 Pinned` lock opt-outs (`P`), intra-column sub-lanes (`Alt + ← / →`), sub-lane pockets, and multi-column skip-links.
- **Box & Link Notes and Reference URLs:** Attach structured notes and external reference URLs to any box or link via the right-click context menu (`📝 Edit Notes & URL` and `🔗 Open URL`). Boxes and link annotations with attached notes or URLs display subtle `📝` and/or `🔗` indicators directly on the canvas, and global keyboard shortcuts (`Delete`, `Backspace`, `Enter`, and single-letter hotkeys) are suspended while typing inside input or note fields.
- **Full-Width Multi-Column `Fit`:** Uses a zoom-independent column geometry calculation (`_totalWorldWidth`) so wide 6–7+ column diagrams fit cleanly inside the viewport without clipping right-hand columns.
- **Installable PWA & Offline Support:** Includes `manifest.json`, `sw.js` (network-first with cache fallback), and `icon.svg`, plus an **Install App (Desktop / Mobile)** option in the main menu.
- **Self-Healing Cryptographic File-Bound Sync:** Synchronizes edits across devices and tabs over `BroadcastChannel`, binary MQTT-over-WebSockets, and WebRTC DataChannels using channels derived strictly from each file's `mapId` and 256-bit `fileSyncToken` with LWW/tombstone CRDT merging, Android file-picker wake guards, hot-switched MQTT topic subscriptions, and deterministic legacy token migration.

## Keyboard & Mouse Quick Reference

| Action | Shortcut / Gesture |
| --- | --- |
| Add Box / Context Menu | `Enter` / Right-Click / Long-Press |
| Add Connected Left Box | `Tab` |
| Start / Complete Link | `L` |
| Stretch Box Top or Bottom | Hover Top/Bottom Edge & Drag |
| Drag Box / Upstream Chain | `Drag` / `Shift + Drag` |
| Shift Intra-Column Sub-Lane | `Alt + ←` / `Alt + →` |
| Edit Text / Annotation / Column | `F2` / Double-Click |
| Return Box to Auto-Layout | `M` |
| Toggle Pin / Upstream Branch Pin | `P` / `Shift + P` |
| Cycle Arrowhead / Toggle Split Stub | `A` / `S` |
| Open / Save File | `Ctrl + O` / `Ctrl + S` (`Ctrl + Shift + S` Save As) |
| Undo / Redo | `Ctrl + Z` / `Ctrl + Y` |
| Delete Selected Box or Link | `Delete` / `Backspace` |

## Links

- **Live App:** `https://rogerwills61-source.github.io/benefits-dependency-network-tool/`
- **Repository:** `https://github.com/rogerwills61-source/benefits-dependency-network-tool`
