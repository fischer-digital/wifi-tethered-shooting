# Sony Alpha Series

**Status:** ✅ Working

**Tested models:** Sony A7 series, A7R series, A7S series, A9, A1 (WLAN-FTP capable models)
**Date tested:** 2026

---

## Prerequisites

- Sony Alpha camera with WLAN-FTP support (most models from A7III onwards – the A7II does not support live FTP transfer)
- Device and camera on the same WLAN network
- FTP Tethered Shooting app installed and running

## Camera Setup

### Step 1: Enable WLAN on the Camera

1. Press the **Menu** button
2. Navigate to: **Network** → **Wi-Fi Settings** → **WLAN**
3. Set to **On**
4. Connect to your studio WLAN network

### Step 2: Configure FTP Transfer

1. Navigate to: **Network** → **FTP Transfer Function** → **FTP Connection Setting**
2. Configure the following:

| Setting | Value |
|---|---|
| Server Name | `ShootingStudio` (or any name) |
| Host | `[Your device's IP – shown in the app]` |
| Port | `2121` |
| Directory | `/` |
| Username | `anonymous` |
| Password | *(leave blank)* |
| Passive Mode | **On** |
| FTPS | **Auto** (or On) |

> ⚠️ **Important:** Set the directory structure to **root only** (not "like in camera"). Otherwise the camera creates subfolders (e.g. `DCIM/date/...`) via FTP, and the app won't detect the files correctly.

### Step 3: Enable Auto Transfer & File Type

1. Navigate to: **Network** → **FTP Transfer Function**
2. Set **Auto Transfer** to **On**
3. **Set file type to JPG only** – do not transfer RAW files (see note below)

> ⚠️ **JPG only!** Configure the camera to send only JPG files via FTP. The app cannot display RAW files, and only JPGs transfer fast enough over WLAN. A medium JPG quality (e.g. 6M / Fine) is sufficient for live review. Your RAW files stay on the memory card for later processing.

### Step 4: Connect and Shoot

1. Start the FTP server in the app (tap the FTP button)
2. On the camera, go to: **Network** → **FTP Transfer Function** → **FTP Connect**
3. The camera connects to the device
4. Take photos – they transfer automatically to the app's gallery

## Tips

- **Direct Connection:** You can connect the camera directly to the device without a router. On the camera, create a WLAN access point, then connect the device to it.
- **JPG Quality:** Set JPG quality to medium (e.g. 6M) – this is sufficient for live review and keeps transfer speed fast. Avoid large/fine JPG sizes.
- **RAW stays on card:** Always keep RAW files on the camera's memory card. They are processed in your own workflow after the shoot.
- **Battery:** WLAN transfer uses more battery – consider using a battery grip for long shoots
- **FTPS:** Sony cameras support FTPS natively. The app's Explicit FTPS mode works seamlessly.

## Known Issues

- **Older models (A7II and below):** Do not support live FTP transfer during shooting. Only the A7III and newer models can send photos automatically while shooting.

## Screenshots

<!-- Add screenshots of Sony camera FTP menu here -->
<!-- Save to images/cameras/ and link -->
<!-- ![Sony FTP Settings](../../images/cameras/sony-alpha-ftp-settings.png) -->