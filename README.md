# e-dig

A simple Bash utility for downloading audio samples from URLs, with optional conversion to WAV format.

---

## Overview

`e-dig` is a lightweight and straightforward Bash script designed to quickly download audio samples from a given URL and save them locally with a user-defined name. It supports common audio formats and optionally converts downloaded files to WAV using `ffmpeg` if available.

This script was originally created as a personal tool to streamline managing audio samples but is shared here for anyone looking for a simple downloader with built-in validation and conversion capabilities.

---

## Features

- Supports downloading from HTTP and HTTPS URLs.
- Validates sample names to avoid invalid filesystem characters.
- Checks URL reachability before attempting to download.
- Automatically detects common audio file extensions (`mp3`, `wav`, `flac`, `ogg`), defaulting to `.mp3` if unclear.
- Prevents accidental overwriting by prompting before overwriting existing files.
- Displays a progress bar during download.
- Optional conversion of downloaded audio to WAV format if `ffmpeg` is installed.
- Simple, interactive prompts fallback when arguments are not supplied.

---

## Requirements

- Bash shell
- `curl` installed and available in the system PATH
- Optional: `ffmpeg` for audio format conversion

---

## Usage

You can run `e-dig` in two ways:

### 1. With URL and sample name as arguments

`./e-dig.sh <audio_file_url> <sample_name>`

Example:

`./e-dig.sh https://example.com/sounds/snare.wav snare_sample`

### 2. Interactive prompt (no arguments)

Simply run:

`./e-dig.sh`

The script will prompt you to enter the URL and sample name.

---

## Sample Name Requirements

- Only letters (a-z, A-Z), numbers (0-9), underscores `_`, and hyphens `-` are allowed.
- This ensures safe file names across different filesystems.

---

## Download Behavior

- The script validates the URL format (`http://` or `https://`).
- It sends a HEAD request to verify the URL is reachable before downloading.
- Supports `.mp3`, `.wav`, `.flac`, `.ogg` extensions; defaults to `.mp3` if none matches.
- Prevents overwriting existing files by prompting the user for confirmation.
- Shows a progress bar during the download.

---

## Optional WAV Conversion

- If `ffmpeg` is installed, after downloading, you'll be prompted whether to convert the file to WAV format.
- Conversion happens in-place and creates a `.wav` version with the same sample name.

---

## Error Handling

- Invalid URLs, unreachable links, or invalid sample names cause the script to exit with an error message.
- Download failures are clearly reported.

---

## Customization

- You can customize or extend this script easily to support other audio formats or post-processing steps.
- Suitable as a quick tool to automate sample downloads for music production or sound design projects.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

## Author & Contact

**galaxy-cli**

GitHub: [https://github.com/galaxy-cli/e-dig](https://github.com/galaxy-cli/e-dig)
