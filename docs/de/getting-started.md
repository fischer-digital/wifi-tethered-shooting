# Erste Schritte

## Installation

**Demnächst im Google Play Store:** Die App wird in Kürze im Google Play Store
zum Download bereitgestellt. Sobald sie dort veröffentlicht ist, findet sich
hier der direkte Link.

Alternativ ist auch eine manuelle Installation per APK möglich:

1. Lade die neueste APK herunter (Download-Link folgt)
2. Auf deinem Android-Gerät: "Installation aus unbekannten Quellen" aktivieren, falls nötig
3. APK installieren

## Erster Start

Beim ersten Öffnen der App werden Berechtigungen benötigt:

1. Die App fragt nach **Zugriff auf Fotos und Medien** (`READ_MEDIA_IMAGES`)
2. Erteile die Berechtigung, damit die App die empfangenen Fotos in der Galerie anzeigen kann

## Kamera einrichten

### Schritt 1: FTP-Server starten

1. Öffne die App
2. Tippe auf die **FTP-Schaltfläche**, um den integrierten FTP-Server zu starten
3. Die App zeigt die **IP-Adresse** deines Geräts und den **Port** (Standard: 2121) an
4. Notiere dir diese – du brauchst sie für deine Kamera

### Schritt 2: Kamera konfigurieren

Jeder Kamerahersteller hat ein anderes Menü. Die allgemeinen Schritte sind:

1. Gehe in die **WLAN-/Netzwerkeinstellungen** deiner Kamera
2. Aktiviere **WLAN** und verbinde dich mit dem **selben Netzwerk** wie dein Gerät (oder nutze den Hotspot deines Geräts – siehe [Sony Alpha Anleitung](camera-setup/sony-alpha.md#schritt-1b-unterwegs))
3. Finde die **FTP-Übertragungs-** oder **Bildübertragungs-Einstellungen**
4. Gib folgende Werte ein:
   - **FTP-Server / Host:** Die IP-Adresse deines Geräts (wird in der App angezeigt)
   - **Port:** `2121`
   - **Benutzername:** wie in der App angezeigt (Standard: `fischerdigital`)
   - **Passwort:** wie in der App angezeigt (wird automatisch generiert, kann in den Einstellungen geändert werden)
   - **Sicherheitsprotokoll / FTPS:** `Ein` (empfohlen – die App unterstützt FTPS nativ)
5. **Verzeichnishierarchie auf "Standard" einstellen** – nicht "wie in der Kamera" verwenden (denn dann werden Unterordner erstellt, die die App nicht erkennen kann)

> 👉 Siehe die [Kamera-Anleitungen](camera-setup/) für modellspezifische Anweisungen!

### Schritt 3: Dateitypen konfigurieren (Wichtig!)

> ⚠️ **Stelle deine Kamera so ein, dass nur JPG-Dateien per FTP übertragen werden.** Die App kann RAW-Dateien nicht anzeigen, und nur JPGs sind schnell genug über WLAN. Eine mittlere JPG-Qualität (z.B. 6M / Fein) reicht für die Live-Bewertung völlig aus – so bleibt die Übertragungsgeschwindigkeit hoch und der Speicherverbrauch gering. Deine RAW-Dateien verbleiben auf der Speicherkarte der Kamera und können später in deinem eigenen Workflow verarbeitet werden.

### Schritt 4: Fotos aufnehmen

1. Mache ein Foto mit deiner Kamera
2. Die Kamera sendet es automatisch per FTP an dein Gerät
3. Das Foto erscheint in der **Live-Galerie** der App
4. Tippe auf ein Foto, um es im Vollbildmodus mit EXIF-Daten anzuzeigen

## Speicherort

Fotos werden gespeichert unter:
```
DCIM/WiFi Tethered Shooting Studio
```
(voller Pfad: `/storage/emulated/0/DCIM/WiFi Tethered Shooting Studio`)

Du findest sie in jedem Dateimanager oder jeder Galerie-App.

## FTPS (Optional)

Für verschlüsselte Übertragungen unterstützt die App **FTPS (Explicit AUTH TLS)**. Die meisten Kameras, die FTPS unterstützen, funktionieren automatisch – keine zusätzliche Konfiguration auf der App-Seite nötig.

> ⚠️ **Hinweis:** Kameras (z.B. Sony) zeigen möglicherweise eine **"Root-Zertifikat-Fehler"**-Warnung an, da der FTP-Server lokal nur ein selbst signiertes SSL-Zertifikat verwenden kann. Die Übertragung ist trotzdem vollständig abgesichert – bestätige die Warnung mit "Verbinden".

Details unter [FTPS / TLS](features/ftps.md).

## Weiterführende Themen

- [FTP-Server Details](features/ftp-server.md) – Erweiterte FTP-Konfiguration
- [Galerie & Bewertungen](features/gallery.md) – Galerie, Bewertungen und Filter nutzen
- [Fehlerbehebung](troubleshooting.md) – Häufige Probleme und Lösungen