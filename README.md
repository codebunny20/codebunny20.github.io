# Ripper

Ripper is a desktop app for downloading video and audio from supported sites, starting with YouTube. It is designed for quick downloads, a simple GUI, and a local setup that keeps everything easy to manage.

Official releases are distributed through Google Drive for now:

[Download the app from Google Drive](https://drive.google.com/file/d/1w6rMgCAcSEteAssXIGJmYHrtyPHY99tC/view?usp=drive_link)

I build and maintain the app myself. Please use only the official download link above.

**Disclaimer:** Use this app responsibly and only download content you have the right to access. The developer is not responsible for misuse of the app.

## Features
- Download YouTube videos as MP4
- Download YouTube audio as MP3
- Extract MP3 from local MP4 files
- Show live progress while ripping
- Open the save folder directly from the app
- Save a preferred download location in app settings

## Tech Stack
- Python
- CustomTkinter
- yt-dlp
- ffmpeg

## Project Layout
- main.py: main app UI and rip logic
- requirements.txt: Python dependencies
- settings/settings.json: saved app settings
- ripped it/: default output folder
- ffmpeg/bin/ffmpeg.exe: bundled ffmpeg binary used for MP3 conversion
- build_exe.ps1: PowerShell script to build a clean one-file EXE

## Quick Start
1. Install Python 3.10+ if needed.
2. Open PowerShell in the project folder.
3. Install dependencies:

```powershell
py -m pip install -r requirements.txt
```

4. Run the app:

```powershell
py main.py
```

## Build the EXE
Use the included PowerShell script for a clean rebuild:

```powershell
./build_exe.ps1
```

This script removes old build output, clears stale spec files, installs PyInstaller if needed, and builds a fresh one-file executable with ffmpeg bundled.

The output is created here:

```text
dist\Ripper.exe
```

## How to Use
1. Open the app.
2. Choose the output mode: MP4 or MP3.
3. Paste a video URL.
4. Click Rip.
5. Use Open Folder to view the file.
6. Use Settings to change the save location.

## ffmpeg Notes
- MP4 downloads can work without ffmpeg in some cases.
- MP3 conversion and extraction require ffmpeg.
- You can either add ffmpeg to your system PATH or keep the bundled ffmpeg binary in the project folder.

## Current Status

### Completed
- [x] Working YouTube download flow
- [x] CustomTkinter UI
- [x] MP3 download support
- [x] MP3 extraction from local MP4 files
- [x] Save-folder settings

### Planned
- [ ] More supported sites
- [ ] Support for more video and audio formats
- [ ] Better reliability, error handling, and retry logic
- [ ] Improved UI polish and user experience
- [ ] Better performance and efficiency
- [ ] URL preview
- [ ] Optional audio manipulation after download
- [ ] Audio converters
- [ ] Text selection and copying support
- [ ] Video converters
- [ ] Video trimming
- [ ] Rip duration in the log
- [ ] Batch downloads
- [ ] Drag-and-drop URL support
- [ ] Metadata editing

## Goal
Keep the app simple, fast, and dependable while gradually adding more sites, formats, and features. I want to turn what I have learned into a useful tool that I and others can rely on.

## Development Notes

- Current version: 1.0.3 as of 8/22/26
- The included PowerShell scripts are the recommended way to rebuild the app
- Bundled ffmpeg is easier to manage than asking users to install it separately
- Future work is focused on distribution, reliability, and feature expansion