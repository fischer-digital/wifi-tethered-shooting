# Troubleshooting

## Connection Issues

### Camera can't connect to the FTP server

1. **Check IP address** – Make sure you're using the IP address shown in the app, not your device's mobile data IP
2. **Same network** – Device and camera must be on the same WLAN network
3. **Port number** – Use port `2121` (some cameras default to port 21)
4. **Passive mode** – Enable passive/extended passive mode on the camera
5. **Firewall** – Some WLAN routers block FTP. Try a direct WLAN connection between device and camera

### Connection drops during shooting

- Check WLAN signal strength on both devices
- Move closer to the WLAN router or use direct connection
- Some cameras have a WLAN sleep timer – disable it in camera settings
- Check if the device's battery saver mode is interfering

### Camera says "Connection refused"

- Make sure the FTP server is running (check the FTP button status in the app)
- Verify the port is `2121`
- Try restarting the FTP server (tap the FTP button off and on again)

## Photo Transfer Issues

### Photos don't appear in the gallery

1. **Wait a moment** – The app polls for new files every 1–5 seconds
2. **Pull to refresh** – Force a manual sync
3. **Check storage** – Ensure the app has storage permissions
4. **Check camera settings** – Verify the camera is actually sending files (some cameras require "Auto Transfer" to be enabled)

### Photos appear but thumbnails are missing

- Thumbnails are generated in the background – wait a few seconds
- For very large RAW files, thumbnail generation may take longer
- The app uses native thumbnail generation at 500px resolution

### Camera sends files but app doesn't receive them

- Check the FTP target folder on the camera – it should be `/` (root)
- Verify the storage path in the app: `/storage/emulated/0/ShootingStudio/`
- Check Android storage permissions (see below)

## Permission Issues

### "Storage access required" message

1. Go to Android **Settings** → **Apps** → **FTP Tethered Shooting** → **Permissions**
2. Enable **Files and media** / **Storage** permission
3. On Android 11+: Grant **"All files access"** (MANAGE_EXTERNAL_STORAGE)
4. Restart the app

### Permission denied after Android update

- Android updates sometimes reset permissions
- Re-grant storage permissions in Android settings
- On some devices, you need to disable and re-enable the permission

## FTPS Issues

### Camera shows certificate error

- Accept the self-signed certificate – it's generated locally and secure
- Some cameras show a fingerprint – this is normal for self-signed certificates

### Camera doesn't support FTPS

- This is fine! The server automatically falls back to plain FTP
- No configuration needed – transfers work either way

### FTPS connection fails

- Try setting the camera to "Auto" FTPS mode if available
- Some cameras only support Implicit FTPS (port 990) – the app currently supports Explicit FTPS only

## Performance Issues

### App is slow with many photos

- The app uses virtual scrolling and lazy loading for performance
- Thumbnails are cached in a local database
- Cache cleanup happens automatically (LRU eviction at 10,000+ entries)
- For very large shoots (1000+ photos), consider clearing old photos periodically

### Device gets warm during long shoots

- This is normal when processing many photos
- The app uses efficient native thumbnail generation
- Consider reducing the polling interval in browse mode

## Still Need Help?

- Search [existing issues](../../issues) for similar problems
- Open a [new bug report](../../issues/new?template=bug-report.md)
- Include your device model, Android version, and camera model