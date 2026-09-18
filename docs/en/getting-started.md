# Getting Started

## Installation

1. Download the latest APK from the releases page (coming soon)
2. On your Android device, enable "Install from unknown sources" if prompted
3. Install the APK

## First Launch

When you open the app for the first time, you'll need to grant storage permissions:

1. The app will ask for **file access permissions**
2. Grant the permission so the app can save and read photos
3. On Android 11+, you may need to grant "All files access" via system settings

## Setting Up Your Camera

### Step 1: Start the FTP Server

1. Open the app
2. Tap the **FTP button** to start the built-in FTP server
3. The app will display your device's **IP address** and the **port** (default: 2121)
4. Note these down – you'll need them for your camera

### Step 2: Configure Your Camera

Each camera brand has a different menu structure. The general steps are:

1. Go to your camera's **network/WLAN settings**
2. Enable **WLAN** and connect to the **same network** as your device (or connect directly)
3. Find the **FTP transfer** or **image transfer** settings
4. Enter the following:
   - **FTP Server / Host:** Your device's IP address (shown in the app)
   - **Port:** `2121`
   - **Username:** `anonymous` (or leave blank)
   - **Password:** (leave blank)
   - **Passive Mode:** Yes (recommended)

> 👉 See the [Camera Setup Guides](camera-setup/) for model-specific instructions!

### Step 3: Take Photos

1. Take a photo with your camera
2. The camera sends it automatically via FTP to your device
3. The photo appears in the app's **live gallery**
4. Tap a photo to view it full-screen with EXIF data

## Storage Location

Photos are saved to:
```
/storage/emulated/0/ShootingStudio/
```

You can find them in any file manager or gallery app.

## FTPS (Optional)

For encrypted transfers, the app supports **FTPS (Explicit AUTH TLS)**. Most cameras that support FTPS will work automatically – no additional configuration needed on the app side.

See [FTPS / TLS](features/ftps.md) for details.

## Next Steps

- [FTP Server details](features/ftp-server.md) – Advanced FTP configuration
- [Gallery & Ratings](features/gallery.md) – Using the gallery, ratings, and filters
- [Troubleshooting](troubleshooting.md) – Common issues and solutions