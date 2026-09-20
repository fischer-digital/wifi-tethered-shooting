# Sony Alpha Serie

**Status:** ✅ Funktioniert

**Getestete Modelle:** Sony A7III
**noch nicht getestete Modelle:** Sony A7-Serie, A7R-Serie, A7S-Serie, A9, A1 (WLAN-FTP-fähige Modelle)
**Getestet:** 2026

---

## Voraussetzungen

- Sony Alpha Kamera mit WLAN-FTP-Unterstützung (die meisten Modelle ab A7III – ältere Modelle unterstützen ggf. keinen live FTP-Transfer)
- Gerät und Kamera im selben WLAN-Netzwerk
- FTP Tethered Shooting App installiert und gestartet

## Kamera einrichten

### Schritt 1a: WLAN an der Kamera aktivieren

1. Drücke die **Menu**-Taste
2. Navigiere zu: **Netzwerk2** → **Wi-Fi-Einstellungen** → **Zugriffspunkt-Einstellungen**

### Schritt 1a: im Studio oder mit mobilem Router

1. Mit deinem Studio-WLAN-Netzwerk oder Deinem mobilen Router verbinden

### Schritt 1b: unterwegs

1. Hotspot an Deinem Andoid-Gerät aktivieren (Einstellungen merken)
2. Kamera mit deinem Hotspot verbinden
3. In der App unter FTP-Settings die "Hotspot auf dem Gerät verlangen/überwachen" aktivieren

### Schritt 1c: Tips zu IP-Adresse

1. Bei Verwendung eines (eigenen) Routers kann/sollte die IP des Android-Gerätes fixiert werden...dann wird unter Schritt 2 immer die gleiche IP-Adresse benötigt.
2. Bei Verwendung des Hotspots im Gerät wird häufig eine andere IP vom Gerät verwendet (unter anderem abhängig davon, ob das Gerät gerade in einem WLAN eingebucht ist). Das lässt sich leider nicht verhindern und führt zum Konfigurationsbedarf in der APP.

### Schritt 2: FTP-Übertragung konfigurieren

1. Navigiere zu: **Netzwerk1** → **FTP-Übertrag.funkt.** → **Server-Einstellung**

![Server-Auswahl](../../../images/cameras/sony-01-server-selection.png)

2. Einen freien Serverslot wählen und konfigurieren:

![Server-Detail](../../../images/cameras/sony-02-server-detail.png)

3. **Ziel-Einstellungen** öffnen und folgendes konfigurieren:

![Ziel-Einstellungen](../../../images/cameras/sony-03-ftp-target-settings.png)

| Einstellung | Wert |
|---|---|
| Hostname | `[IP deines Geräts – wird in der App angezeigt]` |
| Sicherheitsprotokoll | `Ein` |
| RootZertifikat-Fehler | `Verbinden` |
| Port | `2121` (wird in der App angezeigt) |

4. **Verzeichnis-Einstellungen** öffnen:

![Verzeichnis-Einstellungen](../../../images/cameras/sony-04-ftp-directory-settings.png)

| Einstellung | Wert |
|---|---|
| Verz. bestimmen | *(leer lassen)* |
| Verzeich.hierarchie | `Standard` |
| Gleicher Dateiname | `Überschreiben` |

> ⚠️ **Wichtig:** Stelle die Verzeichnishierarchie unbedingt auf **Standard** ein (nicht "Gleiche wie Kamera"). Sonst erstellt die Kamera Unterordner (z.B. `DCIM/Datum/...`) per FTP, und die App erkennt die Dateien nicht.

5. **BenutzerInfo-Einstellungen** öffnen:

![Benutzer-Info](../../../images/cameras/sony-05-ftp-credentials.png)

| Einstellung | Wert |
|---|---|
| Benutzer | `fischerdigital` (Standard, in App-Einstellungen änderbar) |
| Passwort | Automatisch generiert (wird in der App angezeigt, in Einstellungen änderbar) |

6. Diesen "Server" auswählen (orangener Punkt)
7. mit **OK** bestätigen

### Schritt 3: Auto-Transfer aktivieren & Dateityp einstellen

1. Navigiere zu: **Netzwerk1** → Tab 3 → **Autom. Übertragung**

![Auto-Transfer](../../../images/cameras/sony-06-auto-transfer.png)

2. Auf **Ein** setzen
3. **RAW+J. ÜbertragZiel** → `Nur JPEG` setzen

> ⚠️ **Nur JPG!** Stelle die Kamera so ein, dass nur JPG-Dateien per FTP gesendet werden. Die App kann RAW-Dateien nicht anzeigen, und nur JPGs sind schnell genug über WLAN. Eine mittlere JPG-Qualität (z.B. 6M / Fein) reicht für die Live-Bewertung. Deine RAW-Dateien verbleiben auf der Speicherkarte.

4. Navigiere zu: **Qualität/Bildgröße1** (1/14)

![Qualität/Bildgröße](../../../images/cameras/sony-07-image-quality.png)

5. **Dateiformat** → `RAW & JPEG` oder `JPEG` (je nach sonstigem Shooting-Workflow)
6. **JPEG-Qualität** und **JPEG-Bildgröße**: Hier nur die Empfehlung, dass 6M und "Standard" ein guter Kompromiss aus Qualität und Tempo sind

### Schritt 4: Verbinden und fotografieren

1. Starte den FTP-Server in der App (FTP-Button tippen)
2. Auf der Kamera - Navigiere zu: **Netzwerk1** → **FTP-Funktion** -> **Ein** setzen
3. Die Kamera verbindet sich mit dem Gerät. Wenn alles korrekt steht unten: **Verbunden** und der Anzeigename des Servers und des WLAN
> ⚠️ Dort steht auch (Root-Zertifikat-Fehler). Der FTP-Server kann lokal nur ein selbst erstelltet SSL-Zert nutzen. Die Üebrtragung ist aber uneingeschränkt abgesichert.
4. Fotografiere – die Bilder werden automatisch in die Galerie der App übertragen

## Tipps

- **Direktverbindung:** Du kannst die Kamera direkt mit dem Gerät verbinden ohne Router. Erstelle auf der Kamera einen WLAN-Access-Point und verbinde das Gerät damit.
- **JPG-Qualität:** Stelle die JPG-Qualität auf mittel (z.B. 6M) ein – das reicht für die Live-Bewertung und hält die Übertragungsgeschwindigkeit hoch. Vermeide große/feine JPG-Größen.
- **RAW bleibt auf der Karte:** Belasse immer die RAW-Dateien auf der Speicherkarte der Kamera. Sie werden nach dem Shooting in deinem eigenen Workflow verarbeitet.
- **Akku:** WLAN-Übertragung verbraucht mehr Akku – erwäge einen Akkugriff für lange Shootings
- **FTPS:** Sony-Kameras unterstützen FTPS nativ. Der Explicit-FTP-Modus der App funktioniert nahtlos. Das ist and er Kamera der Schalter "Sicherheitsprotokoll". Es geht in einem sicheren WLAN (also nicht öffentlichen) auch ohne, bringt aber nur kaum merklichen Performance-Vorteil

## Bekannte Probleme

- **Ältere Modelle:** Manche älteren Sony Alpha Modelle (z.B. A7II und früher) unterstützen möglicherweise keinen live FTP-Transfer während des Shootings. Nur Modelle ab A7III wurden bisher bestätigt.

