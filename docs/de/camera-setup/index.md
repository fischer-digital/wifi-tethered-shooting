# Kamera-Anleitungen

Von der Community beigetragene Einrichtungsanleitungen für spezifische Kameramodelle.

## Getestete Kameras

| Kamera | Status | Anleitung |
|---|---|---|
| Sony Alpha Serie | ✅ Funktioniert | [Anleitung](sony-alpha.md) |
| Canon EOS R Serie | 🔍 Nicht getestet | [Anleitung](canon-eos-r.md) |
| Nikon Z Serie | 🔍 Nicht getestet | [Anleitung](nikon-z.md) |

## Deine Kamera beisteuern

Wurde deine Kamera erfolgreich getestet? Wir freuen uns, sie zur Liste hinzuzufügen!

1. Kopiere die [TEMPLATE.md](TEMPLATE.md)
2. Fülle die kamera-spezifischen Einstellungen aus
3. Erstelle einen Pull Request

Siehe [CONTRIBUTING.md](../../../CONTRIBUTING.md) für Details.

## Allgemeine FTP-Einstellungen

Für die meisten Kameras sind dies die benötigten Einstellungen:

| Einstellung | Wert |
|---|---|
| FTP-Server / Host | IP deines Geräts (wird in der App angezeigt) |
| Port | `2121` |
| Benutzername | `camera` (Standard, in App-Einstellungen änderbar) |
| Passwort | Automatisch generiert (wird in der App angezeigt, in Einstellungen änderbar) |
| Übertragungsmodus | Passiv |
| Zielordner | `/` |

> **Wichtige Voraussetzungen:**
> - Die Kamera muss **live FTP-Transfer während des Shootings** unterstützen (Fotos automatisch beim Auslösen senden)
> - Die **Ordnerstruktur auf "nur Wurzel"** einstellen (nicht "wie in der Kamera"), um Probleme mit Unterordnern zu vermeiden
> - Die Kamera so einstellen, dass nur **JPG übertragen** wird (kein RAW)

> **Hinweis:** Menüpfade und exakte Bezeichnungen variieren je nach Hersteller. Siehe die einzelnen Kamera-Anleitungen für modellspezifische Anweisungen.