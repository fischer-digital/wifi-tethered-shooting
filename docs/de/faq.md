# FAQ

## Allgemein

### Was ist FTP Tethered Shooting?
Eine Android-App, die dein Smartphone in eine kabellose Tethering-Station verwandelt. Deine Kamera sendet Fotos per WLAN-FTP direkt an dein Smartphone, wo sie in einer Live-Galerie erscheinen.

### Brauche ich eine Internetverbindung?
Nein. Alles läuft lokal in deinem WLAN. Du kannst sogar eine direkte WLAN-Verbindung zwischen Smartphone und Kamera ohne Router verwenden.

### Funktioniert es mit meiner Kamera?
Die App funktioniert mit jeder Kamera, die WLAN-FTP-Übertragung unterstützt. Dazu gehören die meisten modernen Kameras von Sony, Canon, Nikon, Fujifilm und anderen. Siehe die [Kamera-Anleitungen](camera-setup/) für getestete Modelle.

### Ist es kostenlos?
Infos zu Preis/Lizenz findest du auf der Releases-Seite.

### Werden meine Fotos in die Cloud hochgeladen?
Nein. Alle Fotos werden lokal auf deinem Android-Gerät gespeichert unter `/storage/emulated/0/ShootingStudio/`.

---

## Verbindung

### Welches WLAN-Setup soll ich verwenden?
**Empfohlen:** Beide Geräte im selben Studio-WLAN. **Alternative:** Direkte WLAN-Verbindung (Kamera als Access Point) oder Smartphone als mobiler Hotspot. Details unter [FTP-Server](features/ftp-server.md).

### Welchen Port benutzt die App?
Port **2121**. Das ist ein nicht-standardisierter Port, um Konflikte mit anderen FTP-Diensten zu vermeiden.

### Brauche ich einen Benutzernamen und ein Passwort?
Nein. Der Server verwendet standardmäßig anonymen Zugang. Kein Login erforderlich.

### Warum verwendet meine Kamera standardmäßig Port 21?
Manche Kameras verwenden den Standard-FTP-Port (21). Ändere ihn auf **2121** in den FTP-Einstellungen der Kamera.

---

## FTPS / Sicherheit

### Ist FTPS erforderlich?
Nein. FTPS ist optional. Der Server unterstützt gleichzeitig plain FTP und FTPS. Kameras, die FTPS unterstützen, verwenden es automatisch; andere greifen auf plain FTP zurück.

### Sind meine Daten sicher?
Mit FTPS: Daten sind während der Übertragung verschlüsselt. Ohne FTPS: Daten werden unverschlüsselt gesendet (Standard für lokales WLAN). Für ein lokales Studio-Setup ist plain FTP im Allgemeinen ausreichend.

### Die Kamera zeigt eine Zertifikatswarnung
Das ist normal bei selbst-signierten Zertifikaten. Akzeptiere das Zertifikat – es wird lokal auf deinem Gerät erzeugt und bietet Verschlüsselung.

---

## Speicherung

### Wo werden Fotos gespeichert?
```
/storage/emulated/0/ShootingStudio/
```
Du kannst diesen Ordner mit jedem Dateimanager oder jeder Galerie-App erreichen.

### Kann ich den Speicherort ändern?
Der Speicherort ist derzeit festgelegt. Das gewährleistet konsistentes Verhalten und Kompatibilität mit den Android-Speicherberechtigungen.

### Wie viel Speicherplatz brauche ich?
Hängt von den Dateigrößen deiner Kamera ab. Ein typisches JPEG ist 5–15 MB, eine RAW-Datei 25–60 MB. Für ein 500-Fotos-Shooting plane 5–30 GB ein.

---

## Fehlerbehebung

### Die App stürzt beim Start ab
- Prüfe, ob du Speicherberechtigungen erteilt hast
- Versuche den App-Cache in den Android-Einstellungen zu löschen
- Starte dein Smartphone neu

### Fotos werden langsam übertragen
- Prüfe die WLAN-Signalstärke
- Verwende 5 GHz WLAN falls verfügbar (schneller als 2,4 GHz)
- Vermeide überfüllte WLAN-Kanäle
- Versuche eine direkte Verbindung ohne Router

### Siehe auch
- [Fehlerbehebungs-Anleitung](troubleshooting.md) für detaillierte Lösungen
- [Issue erstellen](../../issues/new) falls dein Problem nicht aufgeführt ist