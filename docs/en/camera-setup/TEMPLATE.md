# Camera Setup Template

> **Instructions:** Copy this file, rename it to your camera model (e.g. `sony-a7rv.md`), fill in the details, and submit a Pull Request.

---

## [Camera Brand] [Camera Model]

**Status:** ✅ Working / ⚠️ Working with limitations / ❌ Not working / 🔍 Untested

**Firmware version tested:** [version]
**App version tested:** [version]
**Date tested:** [YYYY-MM]
**Tested by:** [your name / GitHub username]

---

### Prerequisites

- Camera with WLAN-FTP capability
- Device and camera on the same WLAN network (or direct WLAN connection)
- FTP Tethered Shooting app installed and running

### Camera Settings

#### WLAN Setup

1. Go to: `[Menu path]`
2. Enable WLAN: Yes
3. Connection type: `[Infrastructure / Direct / Access Point]`

#### FTP Settings

Navigate to: `[Menu path]`

| Setting | Value |
|---|---|
| FTP Server / Host | `[your device's IP, shown in app]` |
| Port | `2121` |
| Username | `anonymous` |
| Password | *(leave blank)* |
| Transfer mode | `Passive` |
| FTPS / TLS | `Yes` / `No` / `Auto` |
| Auto Transfer | `On` / `Off` |
| Target folder | `/` (root) |

### Step-by-Step

1. **[Step 1]**
2. **[Step 2]**
3. **[Step 3]**
4. ...

### Known Issues / Limitations

- [ ] [Describe any issues]
- [ ] [Or write "None known"]

### Tips

- [Tip 1]
- [Tip 2]

### Screenshots

<!-- Add screenshots of your camera's FTP settings menu -->
<!-- Save screenshots to images/cameras/ and link them here -->

![Camera FTP Settings](../../images/cameras/camera-model-ftp-settings.png)

### Additional Notes

[Any other observations, workarounds, or helpful information]