# FTPS / TLS-Verschlüsselung

## Übersicht

Die App unterstützt **FTPS (FTP über TLS)** für verschlüsselte Dateiübertragungen. Das bedeutet, dass Fotos sicher zwischen deiner Kamera und deinem Smartphone übertragen werden und vor Mitlesen im WLAN geschützt sind.

## So funktioniert es

Der Server verwendet **Explicit FTPS (AUTH TLS)**:

1. Kamera verbindet sich mit dem Server auf demselben Port (2121) – unverschlüsselt
2. Kamera sendet den `AUTH TLS`-Befehl
3. Server antwortet und die Verbindung wird auf TLS-Verschlüsselung umgestellt
4. Alle nachfolgenden Daten (Fotos, Befehle) werden verschlüsselt übertragen

### Warum Explicit-Modus?

- **Abwärtskompatibel:** Kameras, die TLS nicht unterstützen, ignorieren einfach `AUTH TLS` und setzen plain FTP fort
- **Ein Port:** Kein zweiter Port oder separater Listener nötig
- **Null-Konfiguration:** Funktioniert automatisch – kein Schalter in der App nötig

## TLS-Konfiguration

| Eigenschaft | Wert |
|---|---|
| Modus | Explicit FTPS (AUTH TLS) |
| Port | Derselbe wie FTP: `2121` |
| Minimale TLS-Version | TLSv1.2 |
| Zertifikat | Self-signed RSA-2048 |
| Zertifikatsgültigkeit | 10 Jahre |
| Zertifikatsspeicher | BKS-Keystore im privaten Speicher der App |

## Kamera-Kompatibilität

| Kameratyp | FTPS-Unterstützung | Verhalten |
|---|---|---|
| FTPS-fähige Kameras | ✅ Voll | Verbindet mit TLS-Verschlüsselung |
| Nicht-TLS-Kameras | ✅ Voll | Fällt automatisch auf plain FTP zurück |
| Unbekannt | ✅ Voll | Ausprobieren – der Server beherrscht beide Modi |

Die meisten modernen Kameras mit WLAN-FTP-Unterstützung unterstützen auch FTPS. Der Explicit-Modus sorgt für maximale Kompatibilität.

## Self-Signed-Zertifikat

Die App erzeugt beim ersten Serverstart ein **selbst-signiertes Zertifikat**. Das ist Standard für lokale/LAN-FTP-Server und funktioniert mit praktisch allen Kameras.

Manche Kameras zeigen eine Zertifikatswarnung oder einen Fingerprint-Bestätigungsdialog an. Du kannst das Zertifikat bedenkenlos akzeptieren – es wird lokal auf deinem Gerät erzeugt.

## Sicherheitsaspekte

- FTPS verschlüsselt die **Daten während der Übertragung** (Fotos, Befehle)
- Das selbst-signierte Zertifikat bietet Verschlüsselung, aber keine Identitätsverifizierung
- Für ein lokales WLAN-Setup bietet dies angemessene Sicherheit gegen Gelegenheits-Mitlesen
- Das Zertifikat wird nur auf deinem Gerät gespeichert

## Fehlerbehebung

**Kamera nutzt kein TLS:**
- Das ist normal bei älteren Kameras – sie greifen auf plain FTP zurück
- Kein Handlungsbedarf; die Übertragung funktioniert trotzdem

**Zertifikatsfehler auf der Kamera:**
- Akzeptiere das selbst-signierte Zertifikat auf der Kamera
- Manche Kameras zeigen einen Fingerprint an – du kannst ihn mit dem in der App angezeigten vergleichen (zukünftiges Feature)

**Verbindung schlägt fehl nach Aktivierung von FTPS auf der Kamera:**
- Versuche den "Auto"-Modus auf der Kamera, falls verfügbar
- Der Server behandelt plain FTP und FTPS gleichzeitig