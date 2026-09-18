# Kamera-Anleitung Vorlage

> **Anleitung:** Kopiere diese Datei, benenne sie nach deinem Kameramodell (z.B. `sony-a7rv.md`), fülle die Details aus und erstelle einen Pull Request.

---

## [Kamerahersteller] [Kameramodell]

**Status:** ✅ Funktioniert / ⚠️ Funktioniert mit Einschränkungen / ❌ Funktioniert nicht / 🔍 Nicht getestet

**Getestete Firmware-Version:** [Version]
**Getestete App-Version:** [Version]
**Getestet am:** [MM-JJJJ]
**Getestet von:** [Name / GitHub-Benutzername]

---

### Voraussetzungen

- Kamera mit WLAN-FTP-Funktion
- Gerät und Kamera im selben WLAN-Netzwerk (oder direkte WLAN-Verbindung)
- FTP Tethered Shooting App installiert und gestartet

### Kamera-Einstellungen

#### WLAN-Einrichtung

1. Gehe zu: `[Menüpfad]`
2. WLAN aktivieren: Ja
3. Verbindungstyp: `[Infrastructure / Direct / Access Point]`

#### FTP-Einstellungen

Navigiere zu: `[Menüpfad]`

| Einstellung | Wert |
|---|---|
| FTP-Server / Host | `[IP deines Geräts, wird in der App angezeigt]` |
| Port | `2121` |
| Benutzername | `camera` (Standard, in App-Einstellungen änderbar) |
| Passwort | Automatisch generiert (wird in der App angezeigt, in Einstellungen änderbar) |
| Übertragungsmodus | `Passiv` |
| FTPS / TLS | `Ja` / `Nein` / `Auto` |
| Auto-Transfer | `Ein` / `Aus` |
| Zielordner | `/` (Wurzel) |

> ⚠️ **Stelle die Ordnerstruktur auf "nur Wurzel" ein** (nicht "wie in der Kamera"). Sonst erstellt die Kamera Unterordner per FTP und die App erkennt die Dateien nicht korrekt.

#### Dateityp-Einstellungen

> ⚠️ **Stelle die Kamera so ein, dass nur JPG übertragen wird.** RAW-Dateien können von der App nicht angezeigt werden und sind zu langsam für die WLAN-Übertragung.

| Einstellung | Wert |
|---|---|
| Zu übertragender Dateityp | **Nur JPG** |
| JPG-Qualität / -Größe | **Mittel – Fein, max. ~6M** (reicht für Live-Bewertung) |

**Hinweis:** RAW-Dateien verbleiben auf der Speicherkarte der Kamera. Verarbeite sie nach dem Shooting in deinem eigenen Workflow.

### Schritt-für-Schritt

1. **[Schritt 1]**
2. **[Schritt 2]**
3. **[Schritt 3]**
4. ...

### Bekannte Probleme / Einschränkungen

- [ ] [Beschreibe Probleme]
- [ ] [Oder schreibe "Keine bekannt"]

### Tipps

- [Tipp 1]
- [Tipp 2]

### Screenshots

<!-- Füge Screenshots der FTP-Einstellungen deiner Kamera hinzu -->
<!-- Speichere Screenshots in images/cameras/ und verlinke sie hier -->

![Kamera-FTP-Einstellungen](../../images/cameras/kameramodell-ftp-einstellungen.png)

### Zusätzliche Anmerkungen

[Weitere Beobachtungen, Workarounds oder hilfreiche Informationen]