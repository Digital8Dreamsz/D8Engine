# D8Engine 8.1: Release Notes

## What changed
- New engine base: FFmpeg git master snapshot `N-125875-g5d4d3bdc61` (2026-07-31), up from the earlier D8 builds.
- **License is GPL v3** (this build includes libx264 and libx265). Source and build-script links are in the README.
- Includes Windows Media Foundation encoders (`h264_mf`, `hevc_mf`, `aac_mf`, `mp3_mf`).

## Notes
- Newer FFmpeg rejects named profiles for the MF encoders. Use numeric values, e.g. `-profile:v 100` for H.264 High.
- `hevc_mf` needs the Windows "HEVC Video Extensions" component.
- "8.1" is the D8 release label, not an upstream FFmpeg release number.

## Files
- `D8Engine.exe`, `D8Probe.exe`, `SHA256SUMS.txt`

## Support
Ko-fi: https://ko-fi.com/digital8dreamsz
