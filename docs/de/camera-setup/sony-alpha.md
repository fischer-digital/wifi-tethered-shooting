# Sony Alpha Serie

**Status:** ✅ Funktioniert

**Getestete Modelle:** Sony A7-Serie, A7R-Serie, A7S-Serie, A9, A1 (WLAN-FTP-fähige Modelle)
**Getestet:** 2026

---

## Voraussetzungen

- Sony Alpha Kamera mit WLAN-FTP-Unterstützung (die meisten Modelle ab A7III – ältere Modelle unterstützen ggf. keinen live FTP-Transfer)
- Gerät und Kamera im selben WLAN-Netzwerk
- FTP Tethered Shooting App installiert und gestartet

## Kamera einrichten

### Schritt 1: WLAN an der Kamera aktivieren

1. Drücke die **Menu**-Taste
2. Navigiere zu: **Netzwerk** → **WLAN-Einstellungen** → **WLAN**
3. Auf **Ein** setzen
4. Mit deinem Studio-WLAN-Netzwerk verbinden

### Schritt 2: FTP-Übertragung konfigurieren

1. Navigiere zu: **Netzwerk** → **FTP-Übertragungsfunktion** → **FTP-Verbindungseinstellung**
2. Folgendes konfigurieren:

| Einstellung | Wert |
|---|---|
| Servername | `ShootingStudio` (oder beliebiger Name) |
| Host | `[IP deines Geräts – wird in der App angezeigt]` |
| Port | `2121` |
| Verzeichnis | `/` |
| Benutzername | `camera` (Standard, in App-Einstellungen änderbar) |
| Passwort | Automatisch generiert (wird in der App angezeigt, in Einstellungen änderbar) |
| Passiver Modus | **Ein** |
| FTPS | **Auto** (oder Ein) |

> ⚠️ **Wichtig:** Stelle die Ordnerstruktur auf **nur Wurzel** ein (nicht "wie in der Kamera"). Sonst erstellt die Kamera Unterordner (z.B. `DCIM/Datum/...`) per FTP, und die App erkennt die Dateien nicht korrekt.

### Schritt 3: Auto-Transfer aktivieren & Dateityp einstellen

1. Navigiere zu: **Netzwerk** → **FTP-Übertragungsfunktion**
2. **Auto-Transfer** auf **Ein** setzen
3. **Dateityp auf Nur JPG einstellen** – keine RAW-Dateien übertragen (siehe Hinweis unten)

> ⚠️ **Nur JPG!** Stelle die Kamera so ein, dass nur JPG-Dateien per FTP gesendet werden. Die App kann RAW-Dateien nicht anzeigen, und nur JPGs sind schnell genug über WLAN. Eine mittlere JPG-Qualität (z.B. 6M / Fein) reicht für die Live-Bewertung. Deine RAW-Dateien verbleiben auf der Speicherkarte.

### Schritt 4: Verbinden und fotografieren

1. Starte den FTP-Server in der App (FTP-Button tippen)
2. Auf der Kamera: **Netzwerk** → **FTP-Übertragungsfunktion** → **FTP-Verbinden**
3. Die Kamera verbindet sich mit dem Gerät
4. Fotografiere – die Bilder werden automatisch in die Galerie der App übertragen

## Tipps

- **Direktverbindung:** Du kannst die Kamera direkt mit dem Gerät verbinden ohne Router. Erstelle auf der Kamera einen WLAN-Access-Point und verbinde das Gerät damit.
- **JPG-Qualität:** Stelle die JPG-Qualität auf mittel (z.B. 6M) ein – das reicht für die Live-Bewertung und hält die Übertragungsgeschwindigkeit hoch. Vermeide große/feine JPG-Größen.
- **RAW bleibt auf der Karte:** Belasse immer die RAW-Dateien auf der Speicherkarte der Kamera. Sie werden nach dem Shooting in deinem eigenen Workflow verarbeitet.
- **Akku:** WLAN-Übertragung verbraucht mehr Akku – erwäge einen Akkugriff für lange Shootings
- **FTPS:** Sony-Kameras unterstützen FTPS nativ. Der Explicit-FTP-Modus der App funktioniert nahtlos.

## Bekannte Probleme

- **Ältere Modelle:** Manche älteren Sony Alpha Modelle (z.B. A7II und früher) unterstützen möglicherweise keinen live FTP-Transfer während des Shootings. Nur Modelle ab A7III wurden bisher bestätigt.

## Screenshots

<!-- Screenshots des Sony Kamera-FTP-Menüs hier einfügen -->
<!-- Speichere in images/cameras/ und verlinke -->
<!-- ![Sony FTP-Einstellungen](../../images/cameras/sony-alpha-ftp-einstellungen.png) -->