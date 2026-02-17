# Changelog

All notable changes to DAW Project Organiser for Mixcraft will be documented in this file.

## [0.9.0-beta] - 2026-02-18

### Initial Beta Release
First public release - feature complete and stable, seeking community testing.

### Features
- Project scanning (files, folders, all drives)
- SQLite database with Projects, Tracks, and Samples tables
- Advanced search and filtering (filename, title, author, BPM, version, track type, sample names)
- Async background scanning with progress tracking
- Incremental ListView refresh for fast rescans
- Missing sample detection with colour-coded indicators
- Find & Fix Missing Samples tool with multi-drive search
- Metadata editing (Title, Author, BPM) with optional backups
- Dark mode support
- Font size options (Small, Medium, Large)
- Column reordering with persistence
- CSV and text export (all or selected projects)
- Context menu operations (open, rescan, delete, fix samples)
- Tools menu (Find & Fix Samples, Delete from Database/Disk, Clean Up Dead Entries, Scan Errors)
- About dialog with version info
- Tooltips showing full file paths on hover
- Window state persistence (size, position, splitter, sort order)
- Keyboard shortcuts (Ctrl+O, Ctrl+F, Ctrl+S)
- Status bar with project/track/sample totals
- Double-click to open project in Mixcraft

### Supported Formats
- Mixcraft 10 (.mx10) - Full support
- Mixcraft 9 (.mx9) - Full support
- Mixcraft 8 (.mx8) - Full support
- Mixcraft 6-7 (.mx6, .mx7) - Basic support

### Technical Features
- Binary parser for Mixcraft proprietary format
- Track type detection (INST, AUDIO, VIDEO, SEND, SUBMIX, OUTPUT)
- Mixer settings extraction (volume, pan, mute, solo)
- Effects/plugin detection
- Sample path tracking with usage counts
- Version-specific parsing logic
- Scan error tracking and reporting
- File size tracking
- Last modified/scanned timestamps

## Planned for v1.0

### Features Under Consideration
- Project notes/comments field
- Star/favourite system
- Batch metadata editor
- Sample library deduplication
- Backup validator
- Custom columns
- BPM distribution chart
- Recently opened projects list

---

**Note:** This is proprietary software. Source code is not publicly available.
