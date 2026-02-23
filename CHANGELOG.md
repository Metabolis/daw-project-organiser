# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0] - 2026-02-23

### Added
- **Help Topics dialog** — Help → Help Topics with left navigation and styled content
- **Scan Library** — unified entry point that scans monitored folders; on first run, offers to scan all drives and then select which deduped root folders to monitor (checkbox dialog)
- **Multiple watched folders** — manage multiple monitor roots in Preferences; add via File → Add Folder to Library…
- **Rescan File…** — File → Rescan File… to force-rescan selected .mx files without monitoring their folders
- **Samples column (toggled by preference)** — visible when “Check Missing Samples” is enabled (default ON); shows ✓ All found / ⚠ N missing / No samples
- **Time signature** — extracted from project file and shown in the info panel (e.g. 4/4, 3/7, 5/8); stored in database, populated on rescan
- **Automatic database integrity check** — runs weekly when idle; issues are reported automatically, no user action required
- **Rescan failed projects** — Tools → Rescan Failed Projects uses the `ScanError` table to retry only projects that previously failed to parse
- **Scan status in details** — the project details pane now shows a `STATUS: LAST SCAN ERROR` line when the last scan for that project failed
- **Automatic database maintenance (VACUUM)** — runs weekly when idle and after cleaning ≥20 dead entries; no user action required
- **Column chooser + Auto-size** — View → Columns… lets you choose which columns are visible; View → Auto-size Columns fits widths to content. Defaults match previous layout. New optional columns available: Time Sig, Year, Album, Genre, Comments, Copyright.
- **Header context menu** — right‑click column headers for sort, move, reset width, and auto‑size actions; project actions remain on row right‑click
- **Sorting status** — shows “Sorting…” in the status bar during sorts
- **Key and Scale parsing** — stored in the database and shown in the details pane
- **Key and Scale columns** — visible in the project list
- **Key/Scale filters** — filter results by musical key and scale
- **Group by Key/Scale** — organise the list by musical key or scale
- **CSV export header** — matches current visible columns automatically
- **Cancelable scans** — progress dialog now includes a Cancel button; list refreshes if partial results were saved
- **Excel‑friendly exports** — CSV/Text written with UTF‑8 BOM

### Fixed
- **Column alignment** — after column reordering, data now aligns with the correct headers
- **Column visibility persistence** — columns hidden via View → Columns remain hidden across sessions
- **Horizontal scroll** — sorting a far-right column preserves horizontal scroll position
- **Update prompt** — semantic version comparison avoids flagging 0.9.1-beta as newer than 1.0
- **First-run prompts** — removed redundant “Don’t show again”; only shows initial scan prompt on an empty DB; database update prompt appears only when a migration ran and the DB isn’t empty
- **Rescan reliability** — avoid invalid cast by safely converting `LastModified` from SQLite when checking if a project needs rescan
- **Column move alignment** — moving columns now updates row content to match new header order; dragging columns persists the layout
- **Blank Key/Scale after rescan** — incremental refresh now populates these fields
- **SQLite reserved word (“Key”)** — queries quote the column name to avoid conflicts
- **Minor SQL formatting issues** — cleaned up to prevent build errors
- **Hidden column drag** — block resizing of hidden (zero-width) columns when dragging the last visible column
- **Header separator** — removed trailing header separator when the last column is hidden
- **Help dialog formatting** — resolve stray/blank bullets and duplicate headings in Help Topics
- **Older DB migration** — ensure Tracks table includes IsSoloed and Effects
- **False-positive rescans** — timestamp precision tolerance prevents unnecessary rescans
- **Bulk deletes** — menu actions delete in batches for large selections
- **Incremental refresh** — avoids per‑project detail queries for updated IDs

### Changed
- **Row colour scope** — tag colour now applies to the entire row, not just the first column
- **Help Topics polish** — aligned blue heading with left list, added spacing and tidy bullets
- **FX list** — excludes the instrument plugin name on instrument tracks (no duplication)
- **Root selection** — when projects are under Users, proposes per‑user roots (e.g. `C:\Users\metabolis`) instead of `C:\Users`
- **Scan entry points** — replaced multiple scan menu items with a single “Scan Library”; “Scan File/Folder” remain for ad‑hoc adds
- **Status bar** — removed “Watching …” message from the bottom-left
- **Samples preference default** — “Check Missing Samples” now defaults to ON for new installs
- **Update checker version** — uses the application’s product version from metadata instead of a hardcoded string
- **Scan error time** — `LastScanned` for scan errors now uses local time to match the rest of the app’s timestamps
- **Database path** — database stored under `%LOCALAPPDATA%\DAWProjectOrganiser\projects.db` with automatic migration from Roaming if needed
- **Resource cleanup** — database connection is disposed on app exit and form close
- **Data aggregation** — improved aggregation for musical attributes and metadata for greater accuracy
- **Startup prompt on schema change** — recommends performing a full rescan to refresh the library
- **Metadata encoding** — read/write uses Windows‑1252; accented characters display correctly
- **Filter bar** — compact, DPI‑safe wrapping layout
- **Database** — WAL mode enabled for safe background maintenance alongside reads

## [0.9.1-beta] - 2026-02-19

### Added
- **Colour filter** in the search bar — filter by tag colour, or select "None" to find untagged projects
- **Batch Metadata Editor** (Tools → Batch Edit Metadata, or right-click) — edit metadata across multiple selected projects at once; fields left blank are not changed, pre-fills fields where all selected projects share the same value
- **Recently Opened** (File → Recently Opened) — quick access to the last 10 projects opened in Mixcraft, with a "Clear" option; missing files are automatically filtered out
- **Folder Watch** (Preferences → Folder Watch) — automatically scans new or modified .mx files in a watched folder while the app is open; uses a 3-second debounce to wait for Mixcraft to finish writing

### Fixed
- Deleting projects from the database now correctly reports the count in the status bar (previously always showed 0)
- "Find & Fix Missing Samples" now replaces all occurrences of a missing sample path in a project file, not just the first — prevents partially-fixed projects
- Duplicate delete handler removed (context menu and Tools menu now share a single implementation)

### Changed
- Dead commented-out BPM editing code removed from source
- Update checker key obfuscated in source code
- Redundant database migration check removed from `CreateTables`

## [0.9.0-beta] - 2026-02-18

### Initial Beta Release
First public release - feature complete and stable, seeking community testing.

### Features
- **Project scanning** — files, folders, all drives
- **SQLite database** — Projects, Tracks, and Samples tables
- **Advanced search and filtering** — filename, title, author, BPM, version, track type, sample names
- **Async background scanning** — progress tracking
- **Incremental refresh** — fast rescans
- **Missing sample detection** — colour‑coded indicators
- **Find & Fix Missing Samples** — multi‑drive search
- **Metadata editing** — Title, Author and more; optional backups
- **Dark mode support**
- **Font size options** — Small, Medium, Large
- **Column reordering** — with persistence
- **CSV and text export** — all or selected projects
- **Context menu operations** — open, rescan, delete, fix samples
- **Tools menu** — Find & Fix Samples, Delete from Database/Disk, Clean Up Dead Entries, Scan Errors
- **About dialog** — version info
- **Tooltips** — full file paths on hover
- **Window state persistence** — size, position, splitter, sort order
- **Keyboard shortcuts** — Ctrl+O, Ctrl+F, Ctrl+S
- **Status bar totals** — projects, tracks, samples
- **Double‑click to open** — opens project in Mixcraft

### Supported Formats
- Mixcraft 6–10 (.mx6, .mx7, .mx8, .mx9, .mx10)
- Support covers the fields this app uses (version, BPM, time signature, track summaries, sample paths, basic metadata), not every project feature.

### Known Issues
- Large libraries (10,000+ projects) may take time on first scan
- MX8 song length field unreliable (only present in some files)
- Mixcraft must be closed to edit metadata (file locking)
