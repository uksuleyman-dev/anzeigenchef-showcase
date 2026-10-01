# Architektur — Anzeigenchef

## Zielbild

Anzeigenchef trennt Darstellung, fachlichen Zustand, Persistenz, KI-Funktionen und externe Browser-Interaktion. Dadurch können einzelne Komponenten verändert werden, ohne dass jede Änderung das Gesamtsystem betrifft.

## Komponenten

### Desktop UI
CustomTkinter bildet die Interaktionsschicht. Die Oberfläche startet Aktionen und visualisiert Status, soll aber keine plattformspezifische Automationslogik enthalten.

### Anwendungslogik
Koordiniert Benutzeraktionen, Validierung, Jobs und Zustandsübergänge. Sie bildet die Grenze zwischen UI, Daten und externen Diensten.

### DataManager
Verantwortlich für lokale strukturierte Daten, Laden/Speichern sowie Sicherungsmechanismen. Produktive sensible Daten bleiben außerhalb des öffentlichen Showcases.

### KI-Integration
Erzeugt unterstützende Inhalte aus strukturierten Eingaben. Modellzugriff und Prompting werden als austauschbarer Dienst betrachtet.

### Browser-Automatisierung
Playwright kapselt Interaktionen mit externen Plattformen. Selektoren, Timeouts, Retries und Fehlerzustände liegen an dieser Systemgrenze.

## Beispiel für einen Zustandsübergang

```text
ENTWURF
  ↓
VALIDIERT
  ↓
BEREIT_ZUR_AUTOMATION
  ↓
IN_BEARBEITUNG
  ├──→ ERFOLGREICH
  └──→ FEHLER → RETRY / MANUELLE_PRÜFUNG
```

## Qualitätsziele

- Änderungen externer Webseiten lokal begrenzen
- Keine Secrets im Repository
- Datenverlust bei Automationsfehlern vermeiden
- Fehler für Nutzer nachvollziehbar machen
- Komponenten unabhängig test- und austauschbar halten
- Lang laufende Aufgaben von der UI entkoppeln

## Trade-offs

Browser-Automatisierung ermöglicht Integration ohne eigene Plattform-API, erhöht aber die Abhängigkeit von UI-Änderungen. Lokale Persistenz verbessert Datenhoheit und Einfachheit, erfordert jedoch eigene Backup- und Konsistenzmechanismen. KI erhöht Produktivität bei Textaufgaben, darf aber nicht zur unkontrollierten Quelle des fachlichen Zustands werden.
