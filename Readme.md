# SimpleMediaDownloader

A lightweight, menu-driven Python script for downloading videos, audio, and playlists from various websites. Powered by [yt-dlp](https://github.com/yt-dlp/yt-dlp) (a fork of youtube-dl) and [ffmpeg](https://ffmpeg.org/). Supports single items, multiple URLs, and full playlists. Cross-platform compatible (Linux, macOS, Windows).

## Features

- **Download Modes**:
  - Video with Audio (MP4 format).
  - Audio Only (MP3 with best quality VBR).
  - Video without Audio (silent MP4).
- **Playlist Support**: Download entire playlists, organizing files into dedicated folders.
- **Concurrent Downloads**: Adjustable number of simultaneous downloads (default: 5).
- **Failure Handling**: Tracks failed downloads and allows easy retries.
- **Progress Display**: Real-time progress, speed, and ETA for each download.
- **Cross-Platform**: Works on Linux, macOS, and Windows.
- **Supported Sites**: YouTube, Vimeo, Dailymotion, and over 1000+ sites via yt-dlp.
- **Custom Output Directory**: Defaults to user's Downloads folder, with option to customize.
- **Safe and Efficient**: Skips duplicates, retries on failures, and validates URLs.

## Requirements

- **Python**: 3.6+ (tested on 3.12).
- **yt-dlp**: Install via `pip install yt-dlp or trough your package manager`.
- **ffmpeg**: Must be installed and available in your system's PATH. Download from [ffmpeg.org](https://ffmpeg.org/download.html).
  - On Linux: `sudo apt install ffmpeg` (Debian/Ubuntu) or `sudo pacman -S ffmpeg` (Arch).
  - On macOS: `brew install ffmpeg`.
  - On Windows: Download the build and add to PATH.

The script will check for ffmpeg on startup and exit if missing. It also prompts to install yt-dlp if not found.

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/SimpleMediaDownloader.git
   cd SimpleMediaDownloader
   ```

2. Install dependencies:
   ```
   pip install yt-dlp (on linux you can install yt-dlp trough your package manager)
   ```
   Ensure ffmpeg is installed (see Requirements).

3. Run the script:
   ```
   python SimpleMediaDownloader.py
   ```
   Or make it executable (on Linux/macOS):
   ```
   chmod +x SimpleMediaDownloader.py
   ./SimpleMediaDownloader.py
   ```

## Usage

1. Launch the script: `python SimpleMediaDownloader.py`.
2. The menu will appear:
   ```
   ====================================
      SimpleMediaDownloader
      Powered by yt-dlp and ffmpeg
   ====================================

   [1] Video with Audio (Single or Multiple)
   [2] Audio Only (Single or Multiple)
   [3] Video without Audio (Single or Multiple)
   [4] Video with Audio (Playlist Mode)
   [5] Audio Only (Playlist Mode)
   [6] Video without Audio (Playlist Mode)
   [7] Resume Failed Downloads
   [8] Download-Thread Settings
   [9] Help
   [10] Exit
   ```
3. Select an option by entering the number.
4. For downloads:
   - Enter URLs (one per line, press Enter twice to finish).
   - Choose output directory (defaults to ~/Downloads).
5. Use Ctrl+C to interrupt and exit at any time.

### Examples

- **Download a Single Video with Audio**:
  - Select [1].
  - Enter URL: `https://www.youtube.com/watch?v=example`.
  - Files save as `Title [ID].mp4`.

- **Download Playlist Audio**:
  - Select [5].
  - Enter playlist URL: `https://www.youtube.com/playlist?list=PLexample`.
  - Creates a folder with the playlist title and saves MP3 files inside.

- **Retry Failed Downloads**:
  - Select [7] to view and retry failed items from the current session.

- **Adjust Threads**:
  - Select [8] to change concurrent downloads (e.g., set to 3 for slower connections).

For detailed help, select [9] in the menu.

## Troubleshooting

- **ffmpeg Not Found**: Install ffmpeg and ensure it's in your PATH. Restart the terminal after installation.
- **yt-dlp Missing**: Run `pip install yt-dlp`.
- **Invalid URL**: Ensure the URL is correct and not a pure playlist in non-playlist modes.
- **Download Failures**: Check internet connection. Use [7] to retry. Adjust threads via [8] if overload occurs.
- **Permissions Issues**: Run with admin rights if saving to protected directories.
- **Playlist Not Detected**: Use playlist-specific modes ([4]-[6]) for playlist URLs.

If issues persist, check yt-dlp's [documentation](https://github.com/yt-dlp/yt-dlp#readme) or open an issue here.

## Acknowledgments

- yt-dlp and ffmpeg devs <3 .
