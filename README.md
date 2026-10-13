# D8Engine 8.1

**A static Windows FFmpeg build from Digital8Dreamz (D8), licensed under the GNU GPL v3.**

D8Engine is the media engine behind D8 tools such as CFF, Weld, CamWatch and Just Convert: a single `ffmpeg.exe` (shipped as `D8Engine.exe`, with `D8Probe.exe` as the ffprobe-style inspector) that needs no extra DLLs.   **See it in action:** [D8 Converter](https://github.com/Digital8Dreamsz/D8Converter) is a free Windows converter (audio, video, GIF) built on D8Engine.

[![License: GPL v3](https://img.shields.io/badge/license-GPL%20v3-blue.svg)](COPYING.GPLv3)
[![Support on Ko-fi](https://img.shields.io/badge/Ko--fi-support-ff5e5b.svg)](https://ko-fi.com/digital8dreamsz)

> **Heads-up:** this build is **GPL v3**, not LGPL. It includes libx264 and libx265. If you want to bundle an engine inside closed-source software, do not use this one.

---

## Downloads

Get the files from the **[Releases page](../../releases/latest)**.

| File | Description |
|------|-------------|
| `D8Engine.exe` | Static FFmpeg build (ffmpeg.exe, renamed) |
| `D8Probe.exe` | Static ffprobe build (renamed) |
| `SHA256SUMS.txt` | Checksums |

Verify (PowerShell):

```powershell
Get-FileHash .\D8Engine.exe -Algorithm SHA256
```

## What it is

- **Base:** FFmpeg git master, snapshot `N-125875-g5d4d3bdc61` (2026-07-31), built by [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) (`win64-gpl`). "8.1" is the D8 release label, not an upstream FFmpeg version number.
- **Unmodified upstream binary:** D8Engine is BtbN's stock build, renamed. Run `D8Engine.exe -version` and `D8Engine.exe -buildconf` for the exact configuration.
- **Includes (among others):** libx264, libx265, libvpx, libaom, SVT-AV1, libvorbis, libopus, libmp3lame, libwebp, plus Windows Media Foundation encoders (`h264_mf`, `hevc_mf`, `aac_mf`, `mp3_mf`).

### Quick start

```bat
D8Engine.exe -i input.mkv -c:v libx264 -crf 20 -c:a aac_mf output.mp4
```

Animated GIF with a clean palette:

```bat
D8Engine.exe -i input.mp4 -vf "fps=12,scale=480:-1:flags=lanczos,split[a][b];[a]palettegen[p];[b][p]paletteuse" output.gif
```

## Source code (GPL)

The complete corresponding source is public:

- FFmpeg commit `5d4d3bdc61`: https://github.com/FFmpeg/FFmpeg
- Build scripts used to produce the binary: https://github.com/BtbN/FFmpeg-Builds
- Written offer: see [`WRITTEN-OFFER.txt`](WRITTEN-OFFER.txt)

## License & credits

D8Engine is FFmpeg (https://ffmpeg.org) plus third-party libraries, distributed under the **GNU General Public License v3**. Full text: [`COPYING.GPLv3`](COPYING.GPLv3). Each bundled library keeps its own license; see [`CREDITS.md`](CREDITS.md).

FFmpeg is a trademark of Fabrice Bellard. D8Engine is not affiliated with or endorsed by the FFmpeg project or BtbN.

> Codec patents (H.264, HEVC, AAC, MP3) may apply in your region. You are responsible for any licensing your use requires.

## Support the project

I'm a solo developer and everything under the D8 brand is built by hand. If D8Engine saves you time, a tip helps:

**[☕ ko-fi.com/digital8dreamsz](https://ko-fi.com/digital8dreamsz)**

---

*© Digital8Dreamz (Richard "Jonesy" Jones). FFmpeg is © the FFmpeg developers.*
