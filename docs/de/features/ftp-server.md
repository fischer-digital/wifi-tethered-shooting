# FTP-Server

## Übersicht

Die App enthält einen integrierten FTP-Server, der auf deinem Android-Gerät läuft. Deine Kamera verbindet sich per WLAN mit diesem Server und sendet Fotos direkt an dein Gerät.

## Technische Details

| Eigenschaft | Wert |
|---|---|
| Protokoll | FTP (mit optionalem FTPS) |
| Standardport | `2121` |
| Authentifizierung | Anonym (kein Login erforderlich) |
| Übertragungsmodus | Passiv |
| Speicherpfad | `/storage/emulated/0/ShootingStudio/` |

## Server starten

1. Öffne die App
2. Tippe auf die **FTP-Schaltfläche** (die Schaltfläche zeigt den aktuellen Status: aus / an / Warnung)
3. Der Server startet und zeigt die IP-Adresse deines Geräts an
4. Die Schaltfläche ändert sich, um anzuzeigen, dass der Server läuft

## FTP-Server Statusanzeigen

| Anzeige | Bedeutung |
|---|---|
| Aus | Server läuft nicht |
| An (grün) | Server läuft und akzeptiert Verbindungen |
| Warnung | Verbindungsproblem erkannt |

## Netzwerkkonfiguration

### Selbes WLAN (empfohlen)

Die einfachste Einrichtung: Verbinde dein Gerät und deine Kamera mit demselben WLAN-Netzwerk (z.B. dein Studio-WLAN).

- Gerät bekommt IP vom WLAN-Router
- Kamera bekommt IP vom WLAN-Router
- IP des Geräts in den FTP-Einstellungen der Kamera eingeben

### Direktes WLAN / Kamera-Access-Point

Manche Kameras können einen eigenen WLAN-Access-Point erstellen. In diesem Fall:

1. Aktiviere den WLAN-Access-Point der Kamera
2. Verbinde dein Gerät mit dem WLAN der Kamera
3. Ermittle die IP des Geräts im Netzwerk der Kamera (wird in der App angezeigt)
4. Verwende diese IP als FTP-Server-Adresse

> **Hinweis:** Wenn du mit dem WLAN der Kamera verbunden bist, hast du keinen Internetzugang. Das ist normal.

### Mobiler Hotspot

Alternativ kann dein Gerät als Hotspot dienen:

1. Aktiviere den mobilen Hotspot auf deinem Gerät
2. Verbinde die Kamera mit dem Hotspot des Geräts
3. Die Kamera erhält eine IP vom Gerät
4. Verwende die Gateway-IP des Geräts (meist `192.168.43.1` oder ähnlich) als FTP-Server

## Passiver Modus Port-Bereich

Der Server verwendet den passiven Modus für Datenverbindungen. Das bedeutet, dass die Kamera alle Verbindungen initiiert, was gut hinter Firewalls und NAT funktioniert.

## Fehlerbehebung

Wenn sich die Kamera nicht verbinden kann:

1. **IP-Adresse prüfen** – Stelle sicher, dass du die korrekte IP verwendest, die in der App angezeigt wird
2. **Netzwerk prüfen** – Gerät und Kamera müssen im selben Netzwerk sein
3. **Firewall** – Manche WLAN-Router blockieren FTP-Verkehr; versuche eine direkte Verbindung
4. **Port** – Stelle sicher, dass Port `2121` verwendet wird (manche Kameras verwenden standardmäßig Port 21)
5. **Passiver Modus** – Aktiviere den passiven Modus auf der Kamera

Siehe [Fehlerbehebung](../troubleshooting.md) für weitere Lösungen.