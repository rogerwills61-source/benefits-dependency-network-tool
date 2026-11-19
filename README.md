# BDN Studio — Benefits Dependency Network Mapper (v6.27)

**Live App:** [https://rogerwills61-source.github.io/benefits-dependency-network-tool/](https://rogerwills61-source.github.io/benefits-dependency-network-tool/)

**BDN Studio** is an interactive visual workspace for mapping, exploring, and presenting **Benefits Dependency Networks (BDNs)**. It helps programme leaders, architects, and operational teams connect the technology and tools they build (**Enablers**) to the new ways people work (**Business Changes**), the measurable improvements those changes deliver (**Benefits**), and the overarching goals of the organisation (**Strategic Objectives**).

---

## Part 1: User Guide & Everyday Features

### 1. Smooth, Effortless Navigation & Clutter-Free Workspace
- **Fluid Scrolling, Panning & Zooming:** Glide smoothly across even the largest programme maps using your mouse wheel, trackpad, or two-finger touch gestures on phones and tablets.
- **Always-Visible Column Headings:** As you scroll down through a tall diagram, the column titles stay pinned at the top of the screen so you never lose track of which layer you are viewing.
- **One-Click Fit to Screen:** Press **`Fit`** in the top-right toolbar at any time to centre and scale your entire network neatly inside your window—including wide 6- and 7-column diagrams without clipping right-hand columns.

### 2. One-Click Auto-Tidying (`✨ Tidy`)
- **Instant Diagram Organization:** As you brainstorm and add boxes and links, your map can naturally become tangled. Clicking **`✨ Tidy`** automatically organises every column from right to left, lines up connected boxes so links travel in clean horizontal lines, and removes overlapping boxes.
- **Manual Adjustments vs. Pinned Boxes (`✋ Manual` vs. `📌 Pinned`):**
  - **Move or Stretch Any Box Freely:** Drag any box up or down—or drag its top or bottom edge to resize it—and nearby boxes smoothly part out of the way. Any box you move by hand shows a subtle **`✋ Manual`** badge; clicking **`✨ Tidy`** will sweep those manual edits back into a clean layout.
  - **Lock Important Boxes in Place (`📌 Pinned`):** If you want a specific box to stay exactly where you placed it, select it and press **`P`** (or right-click and choose **`📌 Pin Box`**). It will display a blue **`📌 Pinned`** badge, and clicking **`✨ Tidy`** will organise the rest of the diagram around your pinned box without moving it.
- **Automatic Numbered Split Links (`①—①`):** If you drag or pin a box far away from a box it connects to—or if another box is sitting directly in the path between them—the connecting line automatically converts into a matching pair of numbered orange badges (`①—①`). Hovering over either badge highlights both ends so you can trace distant connections at a glance without messy diagonal lines cutting across your map.

### 3. Notes, Reference URLs & Visual Badges on Boxes and Links
- **Attach Notes & Links to Any Box or Link:** Right-click (or long-press on touch devices) any box or link and choose **`📝 Edit Notes & URL`** to store supporting notes, assumptions, evidence, or a reference URL (`#metaEditorModal`). When a URL is present, **`🔗 Open URL`** also appears in the context menu so you can open it in a new tab.
- **At-a-Glance Canvas Indicators:** Boxes and link annotations with attached notes or URLs display subtle **`📝`** and/or **`🔗`** badges right on the diagram so you can spot annotated items immediately.
- **Safe Editing Inside Text & URL Fields:** While typing inside a note box, URL field, or modal input, global diagram shortcuts (`Delete`, `Backspace`, `Enter`, and single-letter hotkeys) are automatically suspended so editing text never deletes a selected box or link underneath.

### 4. Customisable Spacing, High-Contrast Themes & Colour Palettes
Open **`⚙ Settings`** in the top-left toolbar to tailor the map to your screen or presentation room:
- **BDN Map Spacing (`Compact`, `Comfortable`, `Spacious`):** Choose **Compact** for dense overview maps on a single screen, or switch to **Comfortable** or **Spacious** to noticeably open up the breathing room between boxes and widen the horizontal corridors for links and labels.
- **High-Contrast Box Fill Styles:** Choose between **Card**, **Contrast** (elevated dark/light panels with bold accent bars), **Tinted**, **Vivid** (high-saturation colour fills), **Solid** (full-colour blocks with high-contrast lettering), or **Outline**.
- **One-Click Column Colour Palettes & 16 Box Swatches:** Re-colour all columns instantly using preset palettes (**Default**, **Vivid**, **Jewel**, **RAG**, **Cyber**, **Ice**), or right-click any individual box or column header to pick from 16 high-contrast colour swatches.
- **4 Workspace Themes:** Switch live between **Slate Dark**, **Daylight** (for printed reports and bright projectors), **Solarized Warm**, and **Blueprint**.

### 5. Automatic Near Real-Time Synchronisation Across Devices
- **Work Seamlessly Across Laptop, Tablet & Phone:** When you save a BDN map file (`.bdn.json`) and open that same file on another device—or share the file with a colleague—both screens automatically establish a private, near real-time connection.
- **Zero Accounts or Setup Required:** There are no logins, servers to configure, or room codes to type. Moving a box, editing text, adding notes/URLs, or tidying the layout on your laptop updates on your tablet or colleague's screen in a fraction of a second, and automatically reconnects if your device sleeps, opens a file picker on Android, or switches Wi-Fi networks.

### 6. Install on Laptop, Tablet & Mobile (App Mode)
Just like **ThoughtTree**, **BDN Studio** can be installed directly onto your Windows/Mac laptop, Android phone/tablet, or iPhone/iPad so it launches from your taskbar or home screen in its own full-screen window—and even works offline:
1. Click **`☰ Menu`** in the top-left corner of the app.
2. Click **`📲 Install App (Desktop / Mobile)`**.
3. On **Windows, macOS, or Android (Chrome / Edge)**, confirm the native install prompt. On **iPhone or iPad (Safari)**, follow the on-screen prompt (**Share $\rightarrow$ Add to Home Screen**).

### 7. Built-In Example BDNs
Explore five ready-made reference architectures inside **`☰ Menu` $\rightarrow$ `📚 Example BDNs`**:
- **🧪 Starter Demo BDN (4 Columns):** Clean introduction to Enablers, Business Changes, Benefits, and Strategic Objectives.
- **🚀 National Operations (28 Boxes, 5 Columns):** Complex operational transformation featuring sub-lane pockets and multi-column skip links.
- **✈️ Airport Turnaround (30 Boxes, 5 Columns):** Airside A-CDM and baggage recovery dependency network.
- **⚓ Maritime SAR Diamond (26 Boxes, 6 Columns):** Coastal Search & Rescue network showcasing multi-lane diamond branching and convergence.
- **🛡️ Defence Logistics (32 Boxes, 7 Columns):** Sovereign supply-chain torture test with a 3-lane intra-column staircase and a 4-to-1 central funnel hub.

---

## Part 2: Technical Architecture & Zero-Split-Link Ordering Engine

For developers and architects, BDN Studio is built as a dependency-free HTML5 Canvas engine (`index.html`, `manifest.json`, `sw.js`, `icon.svg`) driven by a deterministic **15-Step Canonical Idempotent Zero-Split-Link Solver** (`performIdempotentTidy`).

### 1. Core Methodological & Geometric Invariants
1. **Strictly Horizontal Orthogonal Routing:** All valid dependency links render as straight horizontal lines (`anchorY = constant`) between the right edge of the upstream box and the left edge of the downstream box. Diagonal lines and multi-bend polylines are forbidden.
2. **Vertical Box Stretching Over Link Bending:** Because links must remain horizontal, two connected boxes in adjacent (or skipped) columns can only share a solid link if their vertical intervals `[y + EDGE_CORNER_PAD, y + height - EDGE_CORNER_PAD]` overlap across an unobstructed horizontal corridor. Rather than bending links, the solver dynamically positions and stretches box heights (`n.height`) so connected hubs span across all of their upstream and downstream partners.
3. **Intra-Column Sub-Lanes (`subLane: 0 -> 1 -> 2`):** When a box links to another box within the *same* column, the target box is automatically assigned to `subLane = parent.subLane + 1`, expanding the column's horizontal width (`computeColumnGeometries` with zoom-independent minimum column width and `cg._totalWorldWidth`) to house side-by-side sub-lanes separated by `SUBLANE_GAP`.

### 2. The 15-Step Canonical Idempotent Ordering & Layout Engine
Every invocation of `performIdempotentTidy(ignorePins = false)` resets unpinned boxes to canonical base heights and executes a deterministic 15-step pipeline:

- **Pin Preservation Guard (`ignorePins !== true`):** Captures the exact `{y, height, subLane}` of any user-pinned box (`isAutoLayoutOptOut === true`) while strictly checking `ignorePins !== true` so truthy DOM `MouseEvent` arguments never bypass user pins.
- **Steps 1–3 (Topological Sub-Lane Assignment):** Propagates sequential `subLane` indices (`0 -> 1 -> 2`) along intra-column link chains, promotes degree-1 pocket feeders (`ena_5`) into `subLane: 1` when they exclusively feed a `subLane: 1` target in the next column, and places the bridging Strategic Objective into `subLane: 1` when $\ge 3$ active objectives exist in the rightmost column.
- **Step 4 (Top Skip-Link Chain Detection):** Identifies multi-column skip links (`Math.abs(cA - cB) > 1`) that terminate on a `subLane: 1` bridging objective (`topSkipChainIds`) so they can be anchored along the top corridor of the network.
- **Steps 5–6 (Slot-Driven Base Heights & 4-Pass Right-to-Left Barycenter Ordering):**
  - Computes each box's minimum height from its wrapped text lines and link degree (`LINK_SLOT_SPACING`).
  - Seeds the rightmost column (`Strategic Objectives`) and sweeps right-to-left (`ci = N - 2` down to `0`) across 4 passes, sorting `subLane: 0` boxes by the mean vertical barycentre (`getLane0DownstreamRank`) of their downstream neighbours to minimise link crossings.
- **Steps 7–9 (Adaptive Central Spine Placement & Bilateral Sweeps):**
  - Selects the primary hub column (`spineIdx = state.columns.length >= 6 ? 3 : Math.min(2, state.columns.length - 1)`), spaces its `subLane: 0` boxes vertically, then sweeps left (`spineIdx - 1 .. 0`) and right (`spineIdx + 1 .. N - 1`) to align upstream and downstream boxes with their spine partners.
- **Steps 10 & 13 (4-Case Immutable Sub-Lane & Staircase Lock):** Solves and locks four distinct intra-column sub-lane topologies across columns `0 .. N - 2`:
  1. **Case A — Cross-Column Pocket Feeder + Under-Pocket Corridor (`leftSubFeeder`, e.g., `ena_5 -> chg_4`):** Finalizes `prevBox` (`chg_2`) height *before* computing `pocketY` so `prevBox` never expands into the horizontal pocket corridor; places `sameP` (`chg_3`) below `leftSubFeeder`; caps `n.height` at `(sameP.y + 38) - n.y`; extends both `sameP` and `rightP` down to `underPocketCorridorBot = n.y + n.height + UNDER_BOX_LABEL_CLEARANCE + 26` so `sameP -> rightP` (`"92% first fix"` / `"99.4% bag load"`) routes cleanly underneath `n`; and stretches straddle-feeder `l0Box` (`ena_3`) in Column 1 below `leftSubFeeder` so `"Field sync"` / `"Ramp sync"` connects solidly.
  2. **Case B — Upward Top-of-Column Dual-Partner Span (`ena_2` / `air_2`):** Spans `n` from `rightP.bottom - 38` down to `sameP.y + 38` and stretches `sameP` at least `48px` below `n.bottom`.
  3. **Case C — Single Downward Diamond Sub-Lane Pocket (Maritime SAR `wf_3` & `cap_m4`):** Locks a `54px + CORRIDOR_EXTRA_PAD * 0.45` top corridor above `n` so `sameP` routes upper links (`wf_2 -> cap_m2`) over `n` unobstructed, overlaps `sameP` and `rightP` with `n` by $\ge 44\text{px}$, pushes `nextL0` (`wf_4`) below `n.bottom + 16`, and extends `n`, `rightP`, and any cross-column feeder `lf` (`wf_4 -> cap_m4`) to `sameP.bottom + 48` to keep the under-partner corridor open.
  4. **Case D — 3-Lane Chained Sub-Lane Staircase (`subLane 0 -> 1 -> 2`, Defence Logistics `def_w2 -> def_w3 -> def_w4`):** Steps each sub-lane down by `54px + CORRIDOR_EXTRA_PAD * 0.45`, calls `resolveColumnCollisions` on `rightP.columnId` immediately after stretching `rightP` so `rightP` and `lastRT` never collide, and executes a 3-pass ripple loop across adjacent columns.
- **Step 11 & Step 13b (Pairwise Overlap Verification & Post-Corridor Link Healing):** Scans all adjacent `subLane: 0` links to guarantee at least `20–22px` of vertical overlap, using `clampStretchToColumnClashes` first and falling back to collision-resolved vertical sliding or stretching.
- **Step 12 (Smart Multi-Column Skip-Link Gap Threading):** For any user-added or preset skip link (`Math.abs(cA - cB) > 1`), locates the closest inter-box gap in intermediate column(s) to the midpoint of `leftEnd` and `rightEnd`, opens that corridor to $\ge 46\text{px}$ via `resolveColumnCollisions`, and extends `leftEnd` and `rightEnd` to reach the corridor without colliding with same-column neighbours.
- **Steps 14–15 (Rightmost Bridging Objective Span & Severed Test Branch Parking):** Spans any `subLane: 1` Strategic Objective across all connected Benefits, parks disconnected test nodes (`⚠ Unlinked`) cleanly at the bottom of their columns, restores any user-pinned (`📌 Pinned`) boxes, and runs `computeHorizontalLinksAndStubs`.

### 3. Link Slot Assignment, Obstacle Avoidance & Label Placement (`computeHorizontalLinksAndStubs`)
- **Collision-Free Vertical Slot Search:** For each link, the engine intersects the vertical intervals of the left and right boxes `[oT, oB]`, filters candidate `Y` coordinates through `isBlockedAt(cY, underClearance)` (which checks all intermediate boxes across `[sL, sR]` including `UNDER_BOX_LABEL_CLEARANCE` below any box when the link carries a text annotation), and selects the `Y` coordinate that maximises vertical separation (`LINK_SLOT_SPACING`) from already-assigned link anchors on either box.
- **Sub-Lane Label Gap Sliding (`getBestLabelSpan`):** When a link crosses a column containing sub-lane boxes, `getBestLabelSpan(sL, sR, anchorY, cg)` splits the link's horizontal span around any intermediate box within $\pm 26\text{px}$ vertically and centres the label pill inside the widest unobstructed inter-box gap.

### 4. File-Bound Cryptographic Multi-Device Sync & PWA Offline Architecture
- **256-Bit File-Bound Sync Channel (`fileSyncToken`):** Every `.bdn.json` file contains a 32-byte cryptographic token generated via `crypto.getRandomValues` (with deterministic legacy migration tokens derived from structural IDs when opening older files lacking a token). Devices opening the same file derive a private channel key (`bdn_v26_<mapId>_<fileSyncToken>`) and synchronise state deltas (`updatedAt`, `deletedById` tombstones) over `BroadcastChannel` (same-browser tabs), binary MQTT-over-WebSockets (`broker.emqx.io`, `broker.hivemq.com`, `test.mosquitto.org`) with `CONNACK` retained `HELLO` announcements and hot-switched topic subscriptions, and direct WebRTC `RTCPeerConnection` DataChannels, guarded against file-picker wake collisions and missing-token packets.
- **Offline-First Progressive Web App (`manifest.json` & `sw.js`):** The registered Service Worker caches `./index.html`, `./manifest.json`, and `./icon.svg` using a network-first-with-cache-fallback strategy so installed desktop and mobile instances always fetch the latest release when online and boot instantaneously from local cache when offline.
