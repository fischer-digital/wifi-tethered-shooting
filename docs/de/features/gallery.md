# Galerie & Bewertungen

## Live-Galerie

Die Galerie der App zeigt alle von deiner Kamera empfangenen JPG-Fotos in einer schnellen, optimierten Rasteransicht.

> **Hinweis:** Es werden nur JPG-Dateien unterstützt. RAW-Dateien werden nicht angezeigt und sollten nicht für den FTP-Transfer konfiguriert werden.

### So funktioniert es

1. Deine Kamera sendet ein Foto per FTP
2. Die App erkennt die neue Datei automatisch (Polling alle 1–5 Sekunden)
3. Ein Thumbnail wird generiert und im Raster angezeigt
4. Tippe auf ein Foto für die Vollbildansicht mit Details

### Auto-Sync

| Modus | Polling-Intervall | Verhalten |
|---|---|---|
| Live (Standard) | 1 Sekunde | Neue Fotos erscheinen fast sofort |
| Durchsuchen | 5 Sekunden | Weniger häufige Prüfungen, besser zum Durchblättern |

Wenn im Live-Modus ein neues Foto eintrifft, wird es automatisch im Vollbildmodus angezeigt.

## Rasteransicht

### Performance-Optimierungen

- **Virtuelles Scrollen** – Nur sichtbare Fotos werden gerendert
- **Intelligentes Caching** – Thumbnails werden in einer lokalen Datenbank gecacht für sofortiges Neuladen
- **Platzhalter-Bilder** – Kleine Platzhalter werden angezeigt während Thumbnails laden
- **Verzögertes Laden** – Bilder werden geladen, wenn sie in den sichtbaren Bereich kommen

### Foto-Informationen

Jede Fotokarte zeigt:
- Thumbnail-Bild
- Sterne-Bewertung (wenn "Datei-Infos anzeigen" aktiviert ist)
- Tippen für Vollbildansicht

## Vollbildansicht

Tippe auf ein Foto, um es im Vollbildmodus zu öffnen:

- **EXIF-Daten** – Kameramodell, Objektiv, Blende, Verschlusszeit, ISO, Orientierung
- **Sterne-Bewertung** – Bewerte Fotos von ⭐ bis ⭐⭐⭐⭐⭐ direkt in der App
- **Wisch-Navigation** – Blättere durch Fotos

## Sterne-Bewertungen

Bewerte deine Fotos von ⭐ bis ⭐⭐⭐⭐⭐ direkt in der App.

- Bewertungen werden lokal in der Datenbank der App gespeichert
- Nützlich für schnelle Auswahl während eines Shootings
- Filtern und Sortieren nach Bewertung

## Sortierung

Fotos sind standardmäßig mit dem **neuesten zuerst** sortiert. Wenn während eines Live-Shootings ein neues Foto eintrifft, erscheint es oben im Raster.

## Dateispeicherung

| Eigenschaft | Wert |
|---|---|
| Speicherort | `DCIM/WiFi Tethered Shooting Studio` |
| Dateibenennung | Verwendet den originalen Kamera-Dateinamen |
| Cache | SQLite-Datenbank für Thumbnails, EXIF, Bewertungen |
| Cache-Bereinigung | Automatische LRU-Bereinigung (>10.000 Einträge) |

## Thumbnail-Generierung

Thumbnails werden nativ für Geschwindigkeit generiert:

- **Auflösung:** 500px (längste Kante)
- **Drehung:** Automatisch basierend auf EXIF-Orientierung (alle 8 Orientierungen unterstützt)
- **Format:** JPEG
- **Speicherung:** Lokale SQLite-Datenbank