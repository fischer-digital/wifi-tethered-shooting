# FTP Server

## Overview

The app includes a built-in FTP server that runs on your Android device. Your camera connects to this server via WLAN and sends photos directly to your device.

## Technical Details

| Property | Value |
|---|---|
| Protocol | FTP (with optional FTPS) |
| Default Port | `2121` |
| Authentication | Username + password (shown in app) |
| Transfer Mode | Passive |
| Storage Path | `DCIM/WiFi Tethered Shooting Studio` |

## Starting the Server

1. Open the app
2. Tap the **FTP button** (the button shows the current status: off / on / warning)
3. The server starts and displays your device's IP address
4. The button changes to indicate the server is running

## FTP Server Status Indicators

| Indicator | Meaning |
|---|---|
| Off | Server is not running |
| On (green) | Server is running and accepting connections |
| Warning | Connection issue detected |

## Network Configuration

### Same WLAN (Recommended)

The simplest setup: connect both your device and camera to the same WLAN network (e.g. your studio WLAN).

- Device gets IP from WLAN router
- Camera gets IP from WLAN router
- Enter device's IP in camera FTP settings

### Direct WLAN / Camera Access Point

Some cameras can create their own WLAN access point. In this case:

1. Enable the camera's WLAN access point
2. Connect your device to the camera's WLAN
3. Find the device's IP in the camera's network (usually shown in the app)
4. Use that IP as the FTP server address

> **Note:** When connected to a camera's WLAN, you won't have internet access. This is normal.

### Mobile Hotspot

Alternatively, your device can act as a hotspot:

1. Enable mobile hotspot on your device
2. Connect the camera to the device's hotspot
3. The camera will get an IP from the device
4. Use the device's gateway IP (usually `192.168.43.1` or similar) as the FTP server

## Passive Mode Port Range

The server uses passive mode for data connections. This means the camera initiates all connections, which works well behind firewalls and NAT.

## Troubleshooting

If the camera can't connect:

1. **Verify IP address** – Make sure you're using the correct IP shown in the app
2. **Check network** – Device and camera must be on the same network
3. **Firewall** – Some WLAN routers block FTP traffic; try direct connection
4. **Port** – Ensure port `2121` is used (some cameras default to port 21)
5. **Passive mode** – Enable passive mode on the camera

See [Troubleshooting](../troubleshooting.md) for more solutions.