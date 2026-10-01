# Beispielworkflow — Anzeige veröffentlichen

> Vereinfachtes und anonymisiertes Architekturbeispiel.

1. Nutzer wählt einen lokalen Datensatz.
2. Die Anwendungslogik prüft Pflichtfelder.
3. Optional wird ein Textvorschlag über die KI-Komponente erzeugt.
4. Der Nutzer bestätigt bzw. bearbeitet den Inhalt.
5. Ein Automationsjob wird erzeugt.
6. Playwright öffnet die Zielplattform und führt die definierten Schritte aus.
7. Erfolg oder Fehler werden strukturiert an die Anwendung zurückgegeben.
8. Der lokale Status wird erst nach einem definierten Ergebnis aktualisiert.

## Fehlerfall

Wenn sich beispielsweise ein externer Selektor geändert hat, bleibt der fachliche Datensatz erhalten. Der Job wechselt in einen Fehlerzustand und kann nach Anpassung oder manueller Prüfung erneut ausgeführt werden.
