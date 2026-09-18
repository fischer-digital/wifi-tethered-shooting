# Camera Setup Guides

Community-contributed setup guides for specific camera models.

## Tested Cameras

| Camera | Status | Guide |
|---|---|---|
| Sony Alpha Series | ✅ Working | [Setup Guide](sony-alpha.md) |
| Canon EOS R Series | 🔍 Untested | [Setup Guide](canon-eos-r.md) |
| Nikon Z Series | 🔍 Untested | [Setup Guide](nikon-z.md) |

## Contribute Your Camera

Has your camera been tested successfully? We'd love to add it to the list!

1. Copy the [TEMPLATE.md](TEMPLATE.md)
2. Fill in your camera-specific settings
3. Submit a Pull Request

See [CONTRIBUTING.md](../../../CONTRIBUTING.md) for details.

## General FTP Settings

For most cameras, these are the settings you'll need:

| Setting | Value |
|---|---|
| FTP Server / Host | Your device's IP (shown in the app) |
| Port | `2121` |
| Username | `camera` (default, adjustable in app settings) |
| Password | Auto-generated (shown in app, adjustable in settings) |
| Transfer Mode | Passive |
| Target Folder | `/` |

> **Important requirements:**
> - The camera must support **live FTP transfer during shooting** (sending photos automatically while you shoot)
> - Set the **folder structure to "root only"** (not "like in camera") to avoid subfolder issues
> - Configure the camera to send **JPG only** (not RAW)

> **Note:** Menu paths and exact terminology vary by manufacturer. See the individual camera guides for model-specific instructions.