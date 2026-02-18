# DAW Project Organiser for Mixcraft

A powerful database-driven project manager for Acoustica Mixcraft (versions 6-10). Scan, search, and organise your Mixcraft projects with advanced filtering, metadata editing, and sample tracking.

Born from never saving my Mixcraft projects where I should, or naming them appropriately and not being able to find music I've written in the past - this tool solves the eternal struggle of music producers everywhere: **"Where did I save that project?"**

![Version](https://img.shields.io/badge/version-0.9.0--beta-blue)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey)
![Mixcraft](https://img.shields.io/badge/Mixcraft-6%20%7C%207%20%7C%208%20%7C%209%20%7C%2010-orange)

## Features

### Core Functionality
- 📁 **Project Scanning** - Scan individual files, folders, or entire drives
- 🔍 **Advanced Search** - Search by filename, title, author, BPM, version, track type, or sample name
- 📊 **Detailed Analysis** - View tracks, samples, effects, metadata, and mixer settings
- ⚡ **Async Scanning** - Background scanning with progress tracking - UI stays responsive
- 🎯 **Incremental Refresh** - Fast updates for rescans without rebuilding the entire list

### Organisation & Filtering
- 🎵 **BPM Range Filter** - Find projects within specific tempo ranges
- 🎚️ **Track Type Filter** - Filter by INST, AUDIO, VIDEO, SEND, SUBMIX, OUTPUT tracks
- 📌 **Version Filter** - Separate Mixcraft 8, 9, and 10 projects
- 🔢 **Smart Sorting** - Sort by any column with visual indicators
- 📍 **Column Reordering** - Customise column layout - positions saved automatically

### Sample Management
- 🎹 **Sample Detection** - Automatically detects and catalogues all samples used in projects
- 🔴 **Missing Sample Tracking** - Red text indicators for projects with missing files
- 🔧 **Find & Fix Missing Samples** - Multi-drive search with user-guided selection
- 🔎 **Sample Name Search** - Find projects using specific samples (e.g., "kick.wav")
- ✅ **Real-time Status** - Colour-coded sample status (all found vs. some missing)

### Metadata & Editing
- ✏️ **Metadata Editing** - Edit Title, Author, BPM with automatic backups
- 📝 **Rich Metadata Display** - Copyright, Album, Year, Comments, Genre
- 💾 **Safe Editing** - Optional backup creation before modifications
- 🎛️ **Technical Details** - Track count, master volume, mixer settings (pan, mute, solo)
- 🔌 **Effects Detection** - Lists all effects/plugins used in each project

### Data Management
- 💾 **SQLite Database** - Fast, reliable local storage
- 📤 **Export Options** - Text and CSV export (all projects or selected)
- 🗑️ **Database Management** - Delete from database or disk, clean up dead entries
- 📊 **Statistics** - Total projects, tracks, and samples displayed in status bar
- 🔄 **Smart Rescanning** - Skip unchanged files, force rescan when needed

### User Experience
- 🌓 **Dark Mode** - Easy on the eyes for late-night sessions
- 📏 **Font Sizes** - Small, Medium, Large options
- 💬 **Tooltips** - Hover to see full file paths
- 🪟 **Window State Persistence** - Size, position, splitter, and sort settings saved
- ⌨️ **Keyboard Shortcuts** - Ctrl+O (scan file), Ctrl+F (scan folder), Ctrl+S (export)
- 🎨 **Clean Interface** - Professional ListView with aligned columns

### File Format Support
- ✅ **Mixcraft 10** (.mx10) - Full support including mixer settings
- ✅ **Mixcraft 9** (.mx9) - Full support
- ✅ **Mixcraft 8** (.mx8) - Full support
- ✅ **Mixcraft 6-7** (.mx6, .mx7) - Basic support
- 📊 **Track Types** - INST, AUDIO, VIDEO, SEND, SUBMIX, OUTPUT

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
1. **Scan Projects** - File → Scan Folder, select your Mixcraft projects folder
2. **Browse** - Projects appear in the main list with all metadata
3. **Search** - Type in the search box to filter (filename, title, author, samples)
4. **View Details** - Click any project to see full details in the bottom panel
5. **Open in Mixcraft** - Double-click or right-click → Open in Mixcraft

### Scanning Tips
- **First Time** - Use "Scan All Drives" to find all projects (may take a while)
- **Add New Projects** - Scan folder/file - only new/modified files are scanned
- **After Update** - Use "Rescan All" to refresh track names, volumes, etc.
- **Fix Missing Samples** - Tools → Find & Fix Missing Samples

### Search Examples
- `bass` - Finds projects with "bass" in filename, title, author, or sample names
- Filter BPM: 120-130 - Finds projects between 120-130 BPM
- Version: Mixcraft 10 - Shows only MX10 projects
- Track Type: AUDIO - Projects with audio tracks

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl+O | Scan File |
| Ctrl+F | Scan Folder |
| Ctrl+S | Export All to Text |
| Ctrl+A | Select All |
| Delete | Delete Selected from Database |

## Privacy & Updates

This app stays up-to-date by checking for new versions once a day. It sends only your current app version and OS (e.g., Windows 11) to the update server. No personal information is ever collected or stored.

You can disable this at any time in Settings → Check for Updates.

**What is collected:**
- App version (e.g., "0.9.0-beta")
- Operating system (e.g., "Windows 11")
- Anonymous usage statistics (helps understand which versions are in use)

**What is NOT collected:**
- Your name, email, or any personal information
- Project files, paths, or names
- Computer name or username
- Any identifiable information

All data is used solely to improve the software and understand version adoption.

## Technical Details

### What Gets Scanned
- Project metadata (Title, Author, Copyright, Album, Year, Comments, Genre)
- BPM and master volume
- Track information (type, name, volume, pan, mute/solo status)
- Effects and plugins used
- Sample files and their paths
- File size and modification dates

### Database
- Uses SQLite for fast, reliable storage
- Database location: `%LOCALAPPDATA%\DAWProjectOrganiser\projects.db`
- Automatic backup recommended - just copy the entire folder

### Performance
- Async scanning - UI stays responsive during scans
- Incremental refresh - only updates changed projects
- Efficient sample searching across large libraries

## Known Issues

- Large libraries (10,000+ projects) may take a while for first scan
- Mixcraft must be closed to edit BPM/metadata (file locking)
- Some very old MX6 files may not parse completely

## Roadmap

Planned features for future releases:
- [ ] Project notes/comments field
- [ ] Star/favourite system
- [ ] Batch metadata editor
- [ ] Sample library deduplication
- [ ] Backup validator
- [ ] BPM distribution chart
- [ ] Recently opened projects list

## Privacy & Updates

This app stays up-to-date by checking for new versions once a week. It sends only your current app version and OS (e.g., Windows 11) to the update server. No personal information is ever collected or stored.

You can disable this at any time in Settings → Check for Updates.

## Support

- 📫 **Bug Reports**: [GitHub Issues](https://github.com/Metabolis/daw-project-organiser/issues)
- 💬 **Questions**: [GitHub Discussions](https://github.com/Metabolis/daw-project-organiser/discussions)

## Privacy & Updates

This app stays up-to-date by checking for new versions once a day. It sends only your current app version and OS (e.g., Windows 11) to the update server. No personal information is ever collected or stored.

You can disable this at any time in Settings → Check for Updates.

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
- **Metadata Editing** - When editing Title, Author, or BPM (with optional backup)
- **Fix Missing Samples** - When updating sample paths to point to new locations

All modifications are performed with user consent and confirmation dialogs.

---

**Made with ❤️ for music producers**

**Current Version:** 0.9.0-beta (February 2026)
