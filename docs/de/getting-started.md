# Erste Schritte

## Installation

1. Lade die neueste APK von der Releases-Seite (demnächst verfügbar)
2. Auf deinem Android-Gerät: "Installation aus unbekannten Quellen" aktivieren, falls nötig
3. APK installieren

## Erster Start

Beim ersten Öffnen der App werden Speicherberechtigungen benötigt:

1. Die App fragt nach **Dateizugriffsberechtigungen**
2. Erteile die Berechtigung, damit die App Fotos speichern und lesen kann
3. Unter Android 11+ musst du ggf. "Zugriff auf alle Dateien" in den Systemeinstellungen gewähren

## Kamera einrichten

### Schritt 1: FTP-Server starten

1. Öffne die App
2. Tippe auf die **FTP-Schaltfläche**, um den integrierten FTP-Server zu starten
3. Die App zeigt die **IP-Adresse** deines Geräts und den **Port** (Standard: 2121) an
4. Notiere dir diese – du brauchst sie für deine Kamera

### Schritt 2: Kamera konfigurieren

Jeder Kamerahersteller hat ein anderes Menü. Die allgemeinen Schritte sind:

1. Gehe in die **WLAN-/Netzwerkeinstellungen** deiner Kamera
2. Aktiviere **WLAN** und verbinde dich mit dem **selben Netzwerk** wie dein Gerät (oder verbinde dich direkt)
3. Finde die **FTP-Übertragungs-** oder **Bildübertragungs-Einstellungen**
4. Gib folgende Werte ein:
   - **FTP-Server / Host:** Die IP-Adresse deines Geräts (wird in der App angezeigt)
   - **Port:** `2121`
   - **Benutzername:** `anonymous` (oder leer lassen)
   - **Passwort:** (leer lassen)
   - **Passiver Modus:** Ja (empfohlen)
5. **Ordnerstruktur auf "nur Wurzel" einstellen** – nicht "wie in der Kamera" verwenden (denn dann werden Unterordner erstellt, die die App nicht erkennen kann)

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
DCIM/FTP Tethered Shooting
```
(voller Pfad: `/storage/emulated/0/DCIM/FTP Tethered Shooting`)

Du findest sie in jedem Dateimanager oder jeder Galerie-App.

## FTPS (Optional)

Für verschlüsselte Übertragungen unterstützt die App **FTPS (Explicit AUTH TLS)**. Die meisten Kameras, die FTPS unterstützen, funktionieren automatisch – keine zusätzliche Konfiguration auf der App-Seite nötig.

Details unter [FTPS / TLS](features/ftps.md).

## Weiterführende Themen

- [FTP-Server Details](features/ftp-server.md) – Erweiterte FTP-Konfiguration
- [Galerie & Bewertungen](features/gallery.md) – Galerie, Bewertungen und Filter nutzen
- [Fehlerbehebung](troubleshooting.md) – Häufige Probleme und Lösungen