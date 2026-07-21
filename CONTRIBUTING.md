# Contributing to onvif_h265

## About this fork

`onvif_h265` is a narrow fork of the official Home Assistant ONVIF
integration, adding support for H.265 (HEVC) and H.265+ video
profiles. Because Home Assistant Core changes frequently, keeping
this fork in sync with upstream — without losing the H.265 changes —
is the main maintenance task.

## Syncing with upstream Home Assistant

When a new Home Assistant Core release comes out, follow these steps:

1. Check the "Notes" section of `CHANGELOG.md` for the upstream
   version this fork currently tracks (e.g. `2026.7.2`).
2. Fetch the ONVIF component from the new upstream version:
   `https://github.com/home-assistant/core/tree/<version>/homeassistant/components/onvif`
3. Diff it against `custom_components/onvif_h265`, paying special
   attention to the files that carry the H.265 changes:
   - `device.py` — `async_get_profiles()` and max-resolution
     calculation
   - `config_flow.py` — profile validation during setup
4. Re-apply the H.265 / H.265+ changes on top of the new upstream
   code.
5. Manually test against a real H.264 and a real H.265/H.265+ camera
   (or an ONVIF simulator) before publishing.
6. Update `CHANGELOG.md`:
   - Bump the version following semantic versioning.
   - Update the upstream version referenced in "Notes".
   - List what changed.
7. Bump the version in `manifest.json` and, if needed, `hacs.json`.
8. Tag a release matching the new version.

## Reporting issues

Please include:

- Home Assistant version
- Camera manufacturer and model
- The camera's ONVIF profile information (from `GetProfiles`)
- Relevant Home Assistant logs (`custom_components.onvif_h265`)

## Pull requests

- Keep changes scoped to H.265/H.265+ support wherever possible.
- Avoid unrelated refactors of the original Home Assistant code —
  this keeps future upstream syncs (see above) much easier to review.
- Update `CHANGELOG.md` for any user-facing change.
- Note any file you touch beyond `device.py` and `config_flow.py`,
  since those are the two files this fork is expected to diverge in.
