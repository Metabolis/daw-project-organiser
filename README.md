# DAW Project Organiser for Mixcraft

A powerful database-driven project manager for Acoustica Mixcraft (versions 6-10). Scan, search, and organise your Mixcraft projects with advanced filtering, metadata editing, and sample tracking.

Born from never saving my Mixcraft projects where I should, or naming them appropriately and not being able to find music I've written in the past - this tool solves the eternal struggle of music producers everywhere: **"Where did I save that project?"**

![Version](https://img.shields.io/badge/version-1.0-blue)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey)
![Mixcraft](https://img.shields.io/badge/Mixcraft-6%20%7C%207%20%7C%208%20%7C%209%20%7C%2010-orange)

## Features

- Scan Library with first‑run drive scan; pick folders to watch
- Fast rescans with incremental updates; cancellable background scanning
- Key & Scale columns, filters, and Group by views
- Time Signature column and details
- Missing sample detection + Find & Fix Samples
- Batch metadata editor; safe optional backups
- CSV/Text export matches your visible columns and opens cleanly in Excel
- Accurate metadata with accented characters (e.g., Róisín) 
- Full‑row colour tags; clean ListView with sorting/reorder
- Help Topics dialog with dark‑mode styling

### File Format Support
- ✅ **Mixcraft 6–10** (.mx6, .mx7, .mx8, .mx9, .mx10)
- 📘 **Scope** — Parses the fields this app uses: version, BPM, time signature, track summaries, sample paths, and basic metadata. It does not attempt to fully model every project feature.
- 📊 **Track Types** — INST, AUDIO, VIDEO, SEND, SUBMIX, OUTPUT

## Installation

### Requirements
- Windows 7/8/10/11
- **.NET 8.0 Desktop Runtime** (download if prompted)
  - If you don't have it, Windows will prompt you to download it automatically
  - Or download manually: [.NET 8.0 Desktop Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
  - **Size:** ~50 MB download, one-time install
- No installation of Mixcraft required (reads files directly)

### Download & Install
1. Download the latest release from [Releases](https://github.com/Metabolis/daw-project-organiser/releases)
2. Extract the ZIP file to a folder of your choice
3. Run `DAWProjectOrganiser.exe`
4. If prompted for .NET 8, click "Download" and follow the installer
5. That's it! No installer needed.

**Note:** Windows may show a SmartScreen warning for unsigned applications. Click "More info" → "Run anyway".

## Usage

### Quick Start
1. File → Scan Library (first‑run: scan drives, pick folders to watch)
2. Filter and sort to find projects fast
3. Click a project to view tracks, samples, and metadata
4. Tools → Find & Fix Missing Samples for broken paths
5. Right‑click for Open, Rescan, Delete, and Set Colour

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl+L | Scan Library |
| Ctrl+O | Scan File |
| Ctrl+F | Scan Folder |
| Ctrl+S | Export All to Text |
| Ctrl+A | Select All |
| Delete | Delete Selected from Database |

## Data & Privacy

- Settings: `%APPDATA%\DAWProjectOrganiser\settings.json`
- Database: `%LOCALAPPDATA%\DAWProjectOrganiser\projects.db`
- Weekly optional update check sends only app version and OS; toggle in Settings

## Support

- 📫 **Bug Reports**: [GitHub Issues](https://github.com/Metabolis/daw-project-organiser/issues)
- 💬 **Questions**: [GitHub Discussions](https://github.com/Metabolis/daw-project-organiser/discussions)

## Support Development

If you find this tool useful and want to support its development, donations are greatly appreciated!

You can find a **PayPal QR code** in the About dialog (Help → About), or donate directly via PayPal.

Donations are completely voluntary and help keep development going. Thank you! 🙏

## Version History

See [CHANGELOG.md](CHANGELOG.md) for detailed version history.

## License

This software is proprietary and closed-source. See [LICENSE](LICENSE) for terms of use.

## Disclaimer

This software is not affiliated with, endorsed by, or connected to Acoustica, Inc. or Mixcraft. 
Mixcraft is a registered trademark of Acoustica, Inc. 

**File Modifications:** This tool reads Mixcraft project files and modifies them only when you 
explicitly use the following features:
- **Metadata Editing** - When editing Title, Author, or other metadata (with optional backup)
- **Fix Missing Samples** - When updating sample paths to point to new locations

All modifications are performed with user consent and confirmation dialogs.

---

**Made with ❤️ for music producers**

**Current Version:** 1.0 (February 2026)
