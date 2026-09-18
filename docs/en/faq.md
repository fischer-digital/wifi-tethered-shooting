# FAQ

## General / Allgemein

### What is FTP Tethered Shooting?
An Android app that turns your phone into a wireless tethered shooting station. Your camera sends photos via WLAN-FTP directly to your phone, where they appear in a live gallery.

### Does it require an internet connection?
No. Everything runs locally on your WLAN. You can even use a direct WLAN connection between your phone and camera without any router.

### Does it work with my camera?
The app works with any camera that supports WLAN-FTP transfer. This includes most modern cameras from Sony, Canon, Nikon, Fujifilm, and others. Check the [Camera Setup Guides](camera-setup/) for tested models.

### Is it free?
Check the releases page for pricing/licensing information.

### Does it upload my photos to the cloud?
No. All photos are stored locally on your Android device at `/storage/emulated/0/ShootingStudio/`.

---

## Connection / Verbindung

### What WLAN setup should I use?
**Recommended:** Both devices on the same studio WLAN. **Alternative:** Direct WLAN connection (camera as access point) or phone as mobile hotspot. See [FTP Server](features/ftp-server.md) for details.

### What port does it use?
Port **2121**. This is a non-standard port to avoid conflicts with other FTP services.

### Do I need a username and password?
No. The server uses anonymous access by default. No login required.

### Why does my camera default to port 21?
Some cameras default to the standard FTP port (21). Change it to **2121** in the camera's FTP settings.

---

## FTPS / Security

### Is FTPS required?
No. FTPS is optional. The server supports both plain FTP and FTPS simultaneously. Cameras that support FTPS will use it automatically; others fall back to plain FTP.

### Is my data secure?
With FTPS: data is encrypted in transit. Without FTPS: data is sent unencrypted (standard for local WLAN). For a local studio setup, plain FTP is generally sufficient.

### The camera shows a certificate warning
This is normal with self-signed certificates. Accept the certificate – it's generated locally on your device and provides encryption.

---

## Storage / Speicherung

### Where are photos saved?
```
/storage/emulated/0/ShootingStudio/
```
You can access this folder with any file manager or gallery app.

### Can I change the storage location?
Currently, the storage location is fixed. This ensures consistent behavior and compatibility with Android's storage permissions.

### How much storage do I need?
Depends on your camera's file sizes. A typical JPEG is 5–15 MB, a RAW file 25–60 MB. For a 500-photo shoot, plan for 5–30 GB.

---

## Troubleshooting

### The app crashes on startup
- Check that you've granted storage permissions
- Try clearing the app's cache in Android settings
- Restart your phone

### Photos transfer slowly
- Check WLAN signal strength
- Use 5 GHz WLAN if available (faster than 2.4 GHz)
- Avoid crowded WLAN channels
- Try direct connection without a router

### See also
- [Troubleshooting Guide](troubleshooting.md) for detailed solutions
- [Open an Issue](../../issues/new) if your problem isn't listed