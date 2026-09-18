# FAQ

## Allgemein

### Was ist FTP Tethered Shooting?
Eine Android-App, die dein Gerät in eine kabellose Tethering-Station verwandelt. Deine Kamera sendet Fotos per WLAN-FTP direkt an dein Gerät, wo sie in einer Live-Galerie erscheinen.

### Brauche ich eine Internetverbindung?
Nein. Alles läuft lokal in deinem WLAN. Du kannst sogar eine direkte WLAN-Verbindung zwischen Gerät und Kamera ohne Router verwenden.

### Funktioniert es mit meiner Kamera?
Die App funktioniert mit jeder Kamera, die **live WLAN-FTP-Übertragung während des Shootings** unterstützt (d.h. die Kamera sendet jedes Foto automatisch direkt nach dem Auslösen). Nicht alle Kameras mit WLAN-FTP-Unterstützung können das – zum Beispiel unterstützt die Sony A7III live FTP-Transfer, ältere Modelle wie die A7II jedoch möglicherweise nicht. Siehe die [Kamera-Anleitungen](camera-setup/) für getestete Modelle.

### Ist es kostenlos?
Den aktuellen Preis findest du im [Google Play Store](https://play.google.com/store/apps/details?id=de.fischerdigital.shootingstudio).

### Werden meine Fotos in die Cloud hochgeladen?
Nein. Alle Fotos werden lokal auf deinem Android-Gerät gespeichert unter `DCIM/FTP Tethered Shooting`.

---

## Verbindung

### Welches WLAN-Setup soll ich verwenden?
**Empfohlen:** Beide Geräte im selben Studio-WLAN. **Alternative:** Direkte WLAN-Verbindung (Kamera als Access Point) oder Gerät als mobiler Hotspot. Details unter [FTP-Server](features/ftp-server.md).

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
DCIM/FTP Tethered Shooting
```
(voller Pfad: `/storage/emulated/0/DCIM/FTP Tethered Shooting`)
Du kannst diesen Ordner mit jedem Dateimanager oder jeder Galerie-App erreichen.

### Kann ich den Speicherort ändern?
Der Speicherort ist derzeit festgelegt. Das gewährleistet konsistentes Verhalten und Kompatibilität mit den Android-Speicherberechtigungen.

### Kann ich RAW-Dateien übertragen?
Nein. Die App unterstützt nur JPG-Dateien. RAW-Dateien können nicht angezeigt werden und sind zu groß für eine schnelle WLAN-Übertragung. Stelle deine Kamera so ein, dass nur JPGs per FTP gesendet werden – eine mittlere Qualität (z.B. 6M) reicht für die Live-Bewertung. RAW-Dateien verbleiben auf der Speicherkarte der Kamera und können nach dem Shooting in deinem eigenen Workflow verarbeitet werden.

### Wie viel Speicherplatz brauche ich?
Hängt von den JPG-Dateigrößen deiner Kamera ab. Bei mittlerer JPG-Qualität (z.B. 6M) ist eine typische Datei 2–5 MB. Für ein 500-Fotos-Shooting plane 1–3 GB ein.

---

## Fehlerbehebung

### Die App stürzt beim Start ab
- Prüfe, ob du Speicherberechtigungen erteilt hast
- Versuche den App-Cache in den Android-Einstellungen zu löschen
- Starte dein Gerät neu

### Fotos werden langsam übertragen

- Stelle sicher, dass nur **JPG übertragen** wird – RAW-Dateien sind zu langsam über WLAN
- Reduziere die JPG-Qualität auf mittel (z.B. 6M) für schnellere Übertragungen
- Prüfe die WLAN-Signalstärke
- Verwende 5 GHz WLAN falls verfügbar (schneller als 2,4 GHz)
- Vermeide überfüllte WLAN-Kanäle
- Versuche eine direkte Verbindung ohne Router

### Siehe auch
- [Fehlerbehebungs-Anleitung](troubleshooting.md) für detaillierte Lösungen
- [Issue erstellen](../../issues/new) falls dein Problem nicht aufgeführt ist