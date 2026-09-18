# FTPS / TLS Encryption

## Overview

The app supports **FTPS (FTP over TLS)** for encrypted file transfers. This means photos are transmitted securely between your camera and phone, protecting against eavesdropping on the WLAN.

## How It Works

The server uses **Explicit FTPS (AUTH TLS)**:

1. Camera connects to the server on the same port (2121) – unencrypted
2. Camera sends `AUTH TLS` command
3. Server responds and the connection upgrades to TLS encryption
4. All subsequent data (photos, commands) is transmitted encrypted

### Why Explicit Mode?

- **Backward compatible:** Cameras that don't support TLS simply ignore `AUTH TLS` and continue with plain FTP
- **Single port:** No need for a second port or separate listener
- **Zero configuration:** Works automatically – no toggle needed in the app

## TLS Configuration

| Property | Value |
|---|---|
| Mode | Explicit FTPS (AUTH TLS) |
| Port | Same as FTP: `2121` |
| Minimum TLS version | TLSv1.2 |
| Certificate | Self-signed RSA-2048 |
| Certificate validity | 10 years |
| Certificate storage | BKS keystore in app's private storage |

## Camera Compatibility

| Camera Type | FTPS Support | Behavior |
|---|---|---|
| FTPS-capable cameras | ✅ Full | Connects with TLS encryption |
| Non-TLS cameras | ✅ Full | Falls back to plain FTP automatically |
| Unknown | ✅ Full | Try it – the server handles both modes |

Most modern cameras with WLAN-FTP support also support FTPS. The Explicit mode ensures maximum compatibility.

## Self-Signed Certificate

The app generates a **self-signed certificate** on first server start. This is standard for local/LAN FTP servers and works with virtually all cameras.

Some cameras may display a certificate warning or fingerprint verification prompt. You can safely accept the certificate – it's generated locally on your device.

## Security Considerations

- FTPS encrypts the **data in transit** (photos, commands)
- The self-signed certificate provides encryption but not identity verification
- For a local WLAN setup, this provides adequate security against casual eavesdropping
- The certificate is stored only on your device

## Troubleshooting

**Camera doesn't use TLS:**
- This is normal for older cameras – they fall back to plain FTP
- No action needed; the transfer still works

**Certificate error on camera:**
- Accept the self-signed certificate on the camera
- Some cameras show a fingerprint – you can verify it matches the one shown in the app (future feature)

**Connection fails after enabling FTPS on camera:**
- Try "Auto" mode on the camera if available
- The server handles both plain FTP and FTPS simultaneously