# Fehlerbehebung

## Verbindungsprobleme

### Kamera kann sich nicht mit dem FTP-Server verbinden

1. **IP-Adresse prüfen** – Stelle sicher, dass du die in der App angezeigte IP-Adresse verwendest, nicht die mobile Daten-IP deines Geräts
2. **Selbes Netzwerk** – Gerät und Kamera müssen im selben WLAN-Netzwerk sein
3. **Portnummer** – Verwende Port `2121` (manche Kameras verwenden standardmäßig Port 21)
4. **Passiver Modus** – Aktiviere den passiven/erweiterten passiven Modus auf der Kamera
5. **Firewall** – Manche WLAN-Router blockieren FTP. Versuche eine direkte WLAN-Verbindung zwischen Gerät und Kamera

### Verbindung bricht während des Shootings ab

- Prüfe die WLAN-Signalstärke auf beiden Geräten
- Gehe näher an den WLAN-Router oder verwende eine direkte Verbindung
- Manche Kameras haben einen WLAN-Sleep-Timer – deaktiviere ihn in den Kameraeinstellungen
- Prüfe, ob der Energiesparmodus des Geräts stört

### Kamera meldet "Verbindung abgelehnt"

- Stelle sicher, dass der FTP-Server läuft (prüfe den FTP-Button-Status in der App)
- Überprüfe den Port: `2121`
- Versuche den FTP-Server neu zu starten (FTP-Button aus und wieder an)

## Foto-Übertragungsprobleme

### Fotos erscheinen nicht in der Galerie

1. **Warte einen Moment** – Die App prüft alle 1–5 Sekunden auf neue Dateien
2. **Zum Aktualisieren ziehen** – Erzwinge einen manuellen Sync
3. **Speicher prüfen** – Stelle sicher, dass die App Speicherberechtigungen hat
4. **Kamera-Einstellungen prüfen** – Überprüfe, ob die Kamera tatsächlich Dateien sendet (manche Kameras erfordern "Auto-Transfer" aktiviert)

### Fotos erscheinen, aber Thumbnails fehlen

- Thumbnails werden im Hintergrund generiert – warte ein paar Sekunden
- Bei sehr großen RAW-Dateien kann die Thumbnail-Generierung länger dauern
- Die App verwendet native Thumbnail-Generierung mit 500px Auflösung

### Kamera sendet Dateien, aber die App empfängt sie nicht

- Prüfe den FTP-Zielordner auf der Kamera – er sollte `/` (Wurzel) sein
- Überprüfe den Speicherpfad in der App: `DCIM/WiFi Tethered Shooting Studio`
- Prüfe die Android-Speicherberechtigungen (siehe unten)

## Berechtigungsprobleme

### "Speicherzugriff erforderlich" Meldung

1. Gehe zu Android **Einstellungen** → **Apps** → **WiFi Tethered Shooting Studio** → **Berechtigungen**
2. Aktiviere **Dateien und Medien** / **Speicher** Berechtigung
3. Unter Android 11+: Erteile **"Zugriff auf alle Dateien"** (MANAGE_EXTERNAL_STORAGE)
4. Starte die App neu

### Berechtigung nach Android-Update verweigert

- Android-Updates setzen manchmal Berechtigungen zurück
- Erteile die Speicherberechtigungen erneut in den Android-Einstellungen
- Auf manchen Geräten musst du die Berechtigung deaktivieren und wieder aktivieren

## FTPS-Probleme

### Kamera zeigt Zertifikatsfehler

- Akzeptiere das selbst-signierte Zertifikat – es wird lokal erzeugt und ist sicher
- Manche Kameras zeigen einen Fingerprint an – das ist normal bei selbst-signierten Zertifikaten

### Kamera unterstützt kein FTPS

- Das ist in Ordnung! Der Server greift automatisch auf plain FTP zurück
- Keine Konfiguration nötig – Übertragungen funktionieren in beiden Fällen

### FTPS-Verbindung schlägt fehl

- Versuche den "Auto"-FTP-Modus auf der Kamera, falls verfügbar
- Manche Kameras unterstützen nur Implicit FTPS (Port 990) – die App unterstützt derzeit nur Explicit FTPS

## Performance-Probleme

### App ist langsam bei vielen Fotos

- Die App verwendet virtuelles Scrollen und verzögertes Laden für Performance
- Thumbnails werden in einer lokalen Datenbank gecacht
- Cache-Bereinigung passiert automatisch (LRU-Bereinigung bei 10.000+ Einträgen)
- Bei sehr großen Shootings (1000+ Fotos): erwäge, alte Fotos regelmäßig zu löschen

### Gerät wird warm bei langen Shootings

- Das ist normal bei der Verarbeitung vieler Fotos
- Die App verwendet effiziente native Thumbnail-Generierung
- Erwäge, das Polling-Intervall im Durchsuchen-Modus zu reduzieren

## Brauchst du noch Hilfe?

- Durchsuche [bestehende Issues](../../issues) nach ähnlichen Problemen
- Erstelle einen [neuen Fehlerbericht](../../issues/new?template=bug-report.md)
- Gib dein Gerätemodell, die Android-Version und dein Kameramodell an