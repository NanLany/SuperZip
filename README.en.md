<p align="center"><a href="README.md">简体中文</a> · <strong>English</strong></p>

<p align="center"><img src="assets/mark.svg" width="88" height="88" alt="SuperZip"></p>

<h1 align="center">SuperZip</h1>

<p align="center">A free, fast compression tool.</p>

<p align="center">
  <a href="https://github.com/NanLany/SuperZip/releases/tag/v0.4.4"><img src="assets/badges/version.svg" alt="v0.4.4 · Build51"></a>
  <img src="assets/badges/platform.svg" alt="macOS · Apple Silicon">
  <a href="#download"><img src="assets/badges/windows.svg" alt="Windows · Not released"></a>
  <a href="RELEASE-NOTES.md#english"><img src="assets/badges/status.svg" alt="Beta"></a>
</p>

<p align="center">
  <a href="https://github.com/NanLany/SuperZip/releases/download/v0.4.4/SuperZip-0.4.4-build51-macOS-arm64.dmg"><strong>Download macOS DMG</strong></a>
  &nbsp; · &nbsp;
  <a href="#installation">Installation</a>
  &nbsp; · &nbsp;
  <a href="#benchmarks">Benchmarks</a>
  &nbsp; · &nbsp;
  <a href="https://github.com/NanLany/SuperZip/issues">Report an issue</a>
</p>

SuperZip creates SZP and standard ZIP archives, and extracts ZIP, 7z, and RAR. SZP uses automatic table optimization by default; other files use regular compression. You can turn the optimization off, or choose ZIP when the recipient uses another archive app.

This repository provides downloads, documentation, and issue tracking. SuperZip's own core and interface are closed source.

> **The Windows build has not been released.** Downloads will follow testing on Windows hardware. Check Releases for progress.

## Download

| Platform | Status | Download |
| :-- | :-- | :-- |
| macOS · Apple Silicon | v0.4.4 · Build51 beta | [Download DMG](https://github.com/NanLany/SuperZip/releases/download/v0.4.4/SuperZip-0.4.4-build51-macOS-arm64.dmg) |
| Windows | Planned, not released | In preparation |

The macOS build is for M-series Macs; Intel Macs are not supported. Its deployment target is macOS 12. Testing so far uses an Apple M1 with 8 GB of RAM on macOS 26.2; older macOS releases have not been individually verified.

## Installation

1. Download the [macOS DMG](https://github.com/NanLany/SuperZip/releases/download/v0.4.4/SuperZip-0.4.4-build51-macOS-arm64.dmg), open it, and drag `SuperZip.app` to Applications in the window.
2. If macOS says Apple cannot verify the app, dismiss the dialog with “Done”.
3. Go to **System Settings → Privacy & Security → Security → Open Anyway** and follow the prompts.

This beta is locally signed and has not been notarized by Apple. You do not need to disable macOS security protections or grant Full Disk Access.

## Language

The interface supports Simplified Chinese and English. By default, SuperZip follows your system's first preferred language: Chinese, including Traditional Chinese, uses the Simplified Chinese interface; all other languages use English.

Choose **SuperZip → Language**, then **Follow System**, **简体中文**, or **English**. A manual selection takes precedence over the system language and is saved for future launches. The interface and menus update immediately.

System file dialogs use the selected language the next time you open the app.

## Updates

Choose **Check for Updates…** from the app menu. Automatic checks are enabled by default, run at most once a day, and can be disabled in the same menu. When an update is available, SuperZip shows release notes and opens a full installer download in your browser. Quit SuperZip, then drag the new app to Applications and replace the old copy.

Update information and installers are hosted on GitHub; no account is needed. Compression and extraction continue to work offline.

## Features

| Action | Support |
| :-- | :-- |
| Create SZP | Optimize eligible tables by default and reuse duplicate content blocks |
| Create standard ZIP | Use regular compression that opens in common archive apps |
| Extract common formats | `.szp`, ZIP, 7z, RAR/RAR5; common password-protected and split archive layouts have been tested |
| Read legacy Chinese ZIP filenames | Choose GBK or CP437 and preview names before extraction |
| Batch processing | Select multiple files or folders, process them in sequence, and save a separate output for each |
| Finder services | Right-click → Services → SuperZip compression or extraction to send selected items to the app |

**Recipients need SuperZip to extract `.szp`.** Include this project's download link when sharing SZP archives. This version creates SZP and ZIP, but does not create 7z or RAR. ZIP output does not support table optimization, encryption, or split creation.

## How to use

Choose Compress or Extract in the main window, add your files, and check the options before starting. You can select up to 256 items. For multiple items, choose one destination folder; SuperZip processes them in sequence. Each selected item gets its own archive or extraction folder. Numbered names resolve conflicts without overwriting existing files.

If one item fails, processing continues with the next. **Skip This Item** in a password or filename-preview prompt skips only the current item. The main window's **Cancel** stops the active item and all pending items while keeping completed results.

## Benchmarks

SuperZip's default mode on an everyday project folder containing **4.147 GB across 23,792 files**:

| Archive size | Compression time | Extraction time |
| :-- | :-- | :-- |
| **2.543 GB** | **24.445 s** | **6.817 s** |

These are medians of five runs on an Apple M1, 8 GB of RAM, and macOS 26.2. Timings include file scanning and automatic detection. Results depend on the contents of your files. These earlier SZP default-mode measurements do not include this release's new ZIP output.

[View data preview](https://nanlany.github.io/SuperZip/data-preview.html) — 28 datasets, comparing archive size, compression time, and extraction time under common tools' default settings. The charts have a Chinese/English switch.

You can also [download the HTML](https://github.com/NanLany/SuperZip/releases/download/v0.4.4/data-preview.html) and open `data-preview.html` in Safari, Chrome, or another browser to view all charts offline.

## Before using

- Save to a new name or directory; existing destinations are not overwritten. Keep every part of a split archive in the same folder.
- Permissions, timestamps, and other metadata are not restored. Links, special files, self-extracting archives, and separate passwords for files within one archive are not supported.
- This is an early beta. Keep your original files and do not use its archives as your only backup.

## Feedback

To report a problem, open an [issue](https://github.com/NanLany/SuperZip/issues) with the app version, operating system version, hardware model, steps to reproduce, and error text. A small sample helps us investigate; remove personal information and passwords before attaching it.

## Technology and licensing

<p>
  <img src="assets/badges/rust.svg" alt="Core · Rust">
  <img src="assets/badges/swift.svg" alt="macOS UI · Swift / AppKit">
  <img src="assets/badges/sevenzip.svg" alt="Archive compatibility · 7-Zip 26.03">
</p>

The core uses Rust, the macOS interface uses Swift/AppKit, and common archive extraction uses the 7-Zip 26.03 library.

SuperZip's own implementation is closed source and is not included in this repository. The complete corresponding 7-Zip source, licenses, rebuild instructions, and library replacement instructions are bundled with the app under **App menu → Third-party licenses**. Third-party components retain the rights granted by their respective licenses.

[Release notes](RELEASE-NOTES.md#english) · [简体中文](README.md)
