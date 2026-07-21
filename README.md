# ONVIF H265/H265+ Integration for Home Assistant

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=for-the-badge)](https://github.com/hacs/integration)

A custom integration for Home Assistant that extends the official ONVIF integration to support **H.265 (HEVC)** and **H.265+** video codecs.

## Why this integration?

The official Home Assistant ONVIF integration only supports the H.264 (AVC) codec. It filters out any camera profiles that are not H.264. This custom integration modifies that behavior to accept H.264, H.265 (HEVC), and H.265+ streams, allowing you to use modern cameras that require these higher-efficiency codecs.

## Installation

### HACS (Recommended)

1. Go to **HACS** > **Integrations**
2. Click **...** (top right) > **Custom repositories**
3. Add the URL of this repository and select **Integration** as the category
4. Search for **ONVIF H265/H265+** and click **Download**
5. Restart Home Assistant

### Manual Installation

1. Copy the `onvif_h265` folder into your Home Assistant `config/custom_components/` folder
2. Restart Home Assistant

## Configuration

1. Navigate to **Settings** > **Devices & Services** > **Add Integration**
2. Search for **ONVIF H265/H265+**
3. Enter your camera's IP address, port (usually 90), username, and password
4. Select the desired profiles to add as camera entities

### Requirements

- The camera must have ONVIF enabled and accessible
- The camera must advertise H.264, H.265, or H.265+ profiles in its GetProfiles response
- Home Assistant version 2024.1.0 or newer

## Notes on H.265

H.265 (HEVC) is a highly efficient video codec, but it has some limitations:

- **Browser Support:** H.265 is not widely supported in web browsers. You may need to use the Home Assistant mobile app (iOS/Android) for the best experience, as they have better native codec support.
- **Transcoding:** If you access the camera from a browser, Home Assistant (via FFmpeg) may need to transcode the H.265 stream to H.264 on the fly, which can be CPU intensive.

## Credits

This integration is a fork of the official Home Assistant ONVIF integration.
The codebase is maintained by the Home Assistant community.
