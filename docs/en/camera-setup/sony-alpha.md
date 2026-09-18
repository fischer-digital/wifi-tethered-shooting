# Sony Alpha Series

**Status:** ✅ Working

**Tested models:** Sony A7 series, A7R series, A7S series, A9, A1 (WLAN-FTP capable models)
**Date tested:** 2026

---

## Prerequisites

- Sony Alpha camera with WLAN-FTP support (most models from A7III onwards)
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

### Step 3: Enable Auto Transfer

1. Navigate to: **Network** → **FTP Transfer Function**
2. Set **Auto Transfer** to **On**
3. Choose which file types to transfer (JPEG, RAW, or both)

### Step 4: Connect and Shoot

1. Start the FTP server in the app (tap the FTP button)
2. On the camera, go to: **Network** → **FTP Transfer Function** → **FTP Connect**
3. The camera connects to the device
4. Take photos – they transfer automatically to the app's gallery

## Tips

- **Direct Connection:** You can connect the camera directly to the device without a router. On the camera, create a WLAN access point, then connect the device to it.
- **RAW + JPEG:** If you shoot RAW+JPEG, you can configure which files to transfer in the FTP settings
- **Battery:** WLAN transfer uses more battery – consider using a battery grip for long shoots
- **FTPS:** Sony cameras support FTPS natively. The app's Explicit FTPS mode works seamlessly.

## Known Issues

- None reported for Sony Alpha cameras with this setup

## Screenshots

<!-- Add screenshots of Sony camera FTP menu here -->
<!-- Save to images/cameras/ and link -->
<!-- ![Sony FTP Settings](../../images/cameras/sony-alpha-ftp-settings.png) -->