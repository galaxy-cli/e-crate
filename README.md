# e-dig

A simple Bash utility for downloading audio samples from URLs, with optional conversion to WAV format.

## Overview

`e-dig` is a lightweight, easy-to-use Bash script designed to quickly download audio samples from one or more URLs and save them locally with user-defined names or default naming based on URLs.

Originally created as a personal tool for managing audio samples efficiently, e-dig is now shared to help anyone who needs a straightforward downloader with integrated progress display, URL validation, and conversion features.

---

## Features

- Supports downloading audio from multiple HTTP or HTTPS URLs in a single command.
- Automatically installs or updates yt-dlp (YouTube downloader) to the latest version with a simple command.
- Validates sample names to avoid invalid filesystem characters.
- Checks URL reachability before downloading.
- Detects common audio file extensions (`mp3`, `wav`, `flac`, `ogg`) and uses `.mp3` as a default when unclear.
- Prevents accidental file overwrites by prompting confirmation.
- Displays a progress bar during downloads.
- Interactive prompts for URL(s) and sample names if not supplied as command line arguments.
- Clear error messages for invalid URLs, network failures, or invalid inputs.
- Supports batch downloads by allowing multiple URLs after the -d option.

---

## Requirements

- Bash shell
- curl installed and available in your system PATH
- yt-dlp (the script can install or update it automatically)

Installation and Updating yt-dlp
Use the -u flag with e-dig to install or update yt-dlp to the latest version automatically.

This process tries to install via your package manager (apt) first, and falls back to downloading the latest binary directly from GitHub if needed.

---

## Usage

### 1. Update or install yt-dlp
```./e-dig -u```
This ensures that yt-dlp is available and up-to-date to handle YouTube downloads.

### 2. Download one or more audio files
```./e-dig -d [URL1] [URL2] [URL3] ...```
#### Example:

```./e-dig -d https://youtu.be/abc123 https://youtu.be/def456```
This downloads audio from each given URL sequentially, extracting in MP3 format by default.

### 3. Interactive mode
Run the script without arguments to be prompted for URLs and sample names.

### 4. Download with custom sample names and format validation
The script supports safe sample names containing only letters, numbers, underscores _, and hyphens -.

Before downloading, it verifies each URL’s reachability and extension.

Prevents overwriting files by asking before saving.

---

## Sample Name Requirements

Allowed characters: letters (a-z, A-Z), numbers (0-9), underscores _, and hyphens -.

Ensures generated file names are filesystem-safe across platforms.

### Error Handling
- Invalid or unreachable URLs produce clear error messages.
- Network failures or permission issues during download report descriptive feedback.
- Sample name format errors abort the process to avoid issues.

## Customization

Easily extend the script to support additional audio formats or custom post-processing steps.

Can be adapted for various use cases in sound design, music production, or media archiving.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

## Author & Contact

**galaxy-cli**

GitHub: [https://github.com/galaxy-cli/e-dig](https://github.com/galaxy-cli/e-dig)