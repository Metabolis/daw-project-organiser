# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Planned for v1.0
- Sample library deduplication
- Backup validator
- BPM distribution chart

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
- Project scanning (files, folders, all drives)
- SQLite database with Projects, Tracks, and Samples tables
- Advanced search and filtering (filename, title, author, BPM, version, track type, sample names)
- Async background scanning with progress tracking
- Incremental ListView refresh for fast rescans
- Missing sample detection with colour-coded indicators
- Find & Fix Missing Samples tool with multi-drive search
- Metadata editing (Title, Author, and more) with optional backups
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

### Known Issues
- Large libraries (10,000+ projects) may take time on first scan
- MX8 song length field unreliable (only present in some files)
- Mixcraft must be closed to edit metadata (file locking)

