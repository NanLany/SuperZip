<p align="center"><a href="README.md">简体中文</a> · <strong>English</strong></p>

<p align="center"><img src="assets/mark.svg" width="88" height="88" alt="SuperZip"></p>

<h1 align="center">SuperZip</h1>

<p align="center">A free, fast compression tool.</p>

<p align="center">
  <a href="https://github.com/NanLany/SuperZip/releases"><img src="assets/badges/version.svg" alt="v0.4.3 · Build47"></a>
  <img src="assets/badges/platform.svg" alt="macOS · Apple Silicon">
  <a href="#download"><img src="assets/badges/windows.svg" alt="Windows · Not released"></a>
  <a href="RELEASE-NOTES.md#english"><img src="assets/badges/status.svg" alt="Beta"></a>
</p>

<p align="center">
  <a href="https://github.com/NanLany/SuperZip/releases"><strong>Download for macOS</strong></a>
  &nbsp; · &nbsp;
  <a href="#installation">Installation</a>
  &nbsp; · &nbsp;
  <a href="#benchmarks">Benchmarks</a>
  &nbsp; · &nbsp;
  <a href="https://github.com/NanLany/SuperZip/issues">Report an issue</a>
</p>

SuperZip creates `.szp` archives and extracts ZIP, 7z, and RAR. Automatic table optimization is enabled by default and can be turned off. Other files use regular compression.

This repository provides downloads, documentation, and issue tracking. SuperZip's own core and interface are closed source.

> **The Windows beta is expected in about a week.** We will test it on Windows hardware before release. Check Releases for the confirmed date.

## Download

| Platform | Status | Download |
| :-- | :-- | :-- |
| macOS · Apple Silicon | v0.4.3 · Build47 beta | [Releases](https://github.com/NanLany/SuperZip/releases) · DMG / ZIP |
| Windows | Expected in about a week | In preparation |

The macOS build is for M-series Macs; Intel Macs are not supported. Its deployment target is macOS 12. Testing so far uses an Apple M1 with 8 GB of RAM on macOS 26.2; older macOS releases have not been individually verified.

## Installation

1. Download the macOS DMG from [Releases](https://github.com/NanLany/SuperZip/releases), open it, and drag `SuperZip.app` to Applications in the window. Alternatively, download the ZIP, extract it, and move the complete app to Applications.
2. If macOS says Apple cannot verify the app, dismiss the dialog with “Done”.
3. Go to **System Settings → Privacy & Security → Security → Open Anyway** and follow the prompts.

This beta is locally signed and has not been notarized by Apple. You do not need to disable macOS security protections or grant Full Disk Access.

## Updates

Choose **Check for updates…** from the app menu. Automatic checks are enabled by default, run at most once a day, and can be disabled in the same menu. When an update is available, SuperZip shows release notes and a full installer download. Quit SuperZip, then drag the new app to Applications and replace the old copy.

Update information and installers are hosted on GitHub; no account is needed. Compression and extraction continue to work offline.

## Features

| Action | Support |
| :-- | :-- |
| Compress files and folders | Create `.szp` archives, optimize eligible tables, and reuse duplicate content blocks |
| Extract common formats | `.szp`, ZIP, 7z, RAR/RAR5; common password-protected and split archive layouts have been tested |
| Read legacy Chinese ZIP filenames | Choose GBK or CP437 and preview names before extraction |
| Finder services | Right-click → Services → SuperZip compression or extraction; one item at a time |

**Recipients need SuperZip to extract `.szp`.** Include this project's download link when sharing an archive. This version does not create ZIP, 7z, or RAR files.

## Benchmarks

SuperZip's default mode on an everyday project folder containing **4.147 GB across 23,792 files**:

| Archive size | Compression time | Extraction time |
| :-- | :-- | :-- |
| **2.543 GB** | **24.445 s** | **6.817 s** |

These are medians of five runs on an Apple M1, 8 GB of RAM, and macOS 26.2. Timings include file scanning and automatic detection. Results depend on the contents of your files.

[Download data preview (HTML)](https://github.com/NanLany/SuperZip/releases/download/untagged-98937f0c841fd5b0a29c/data-preview.html) — 28 datasets, comparing archive size, compression time, and extraction time under common tools' default settings. The charts have a Chinese/English switch.

Open the downloaded `data-preview.html` in Safari, Chrome, or another browser; it works offline. If double-clicking opens a text editor, right-click the file and choose **Open With → your browser**. A direct online page will be available once the repository is public.

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
