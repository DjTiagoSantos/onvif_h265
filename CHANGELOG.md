# Changelog

## [1.0.0] - 2026-07-20

### Added
- Support for H.265 (HEVC) video encoding profiles
- Support for H.265+ video encoding profiles
- Portuguese (pt-BR) translations
- HACS compatibility (hacs.json)

### Changed
- Modified `device.py` to accept H.264, H.265, and H.265+ profiles in `async_get_profiles()`
- Modified `device.py` to calculate max resolution from H.264, H.265, and H.265+ profiles
- Modified `config_flow.py` to validate H.264, H.265, and H.265+ profiles during setup

### Notes
- Based on Home Assistant ONVIF integration from version 2026.7.2
- All original ONVIF functionality (PTZ, events, imaging, snapshots) is preserved
