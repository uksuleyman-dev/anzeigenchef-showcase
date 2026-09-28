# Anzeigenchef – Showcase

## Überblick
**Anzeigenchef** ist eine Python-basierte Desktop-Anwendung zur Verwaltung und Automatisierung von Kleinanzeigen-Prozessen.

Das Projekt verbindet Benutzeroberfläche, lokale Datenhaltung, Browser-Automatisierung und KI-gestützte Textgenerierung in einer Anwendung.

## Technischer Schwerpunkt
- Python 3.10+
- CustomTkinter für die Desktop-GUI
- Playwright für Browser-Automatisierung
- Lokale JSON-Datenhaltung
- OpenAI-/ChatGPT-Integration für Textgenerierung
- Strukturierte Trennung von Datenhaltung, Automation, GUI und Generator-Komponenten
- Logging, Fehlerbehandlung und Screenshots bei Automationsfehlern
- Lokale Backups bei Datenänderungen
- Umgang mit Zugangsdaten außerhalb des Quellcodes

## Architektur
Die Anwendung trennt ihre Hauptverantwortlichkeiten in mehrere Komponenten:

- **DataManager** – Laden, Speichern und Sichern lokaler Daten
- **BrowserAutomation** – browsergestützte Automatisierung
- **OpenAITextGenerator / ChatGPTWebGenerator** – KI-gestützte Textgenerierung
- **KleinanzeigenManagerApp** – Benutzeroberfläche und Anwendungslogik

### Vereinfachter Datenfluss
1. Benutzerinteraktion über die Desktop-GUI
2. Laden und Speichern strukturierter Daten
3. Generierung bzw. Aufbereitung von Inhalten
4. Ausführung von Browser-Automatisierungen
5. Status-, Fehler- und Protokollausgabe

## Was das Projekt zeigt
- Praktische Python-Entwicklung
- Integration mehrerer technischer Komponenten
- Schnittstellen- und Datenflussdenken
- Browser-Automatisierung
- KI-Integration
- Strukturierte Fehlerbehandlung
- Eigenständige Konzeption und Umsetzung einer vollständigen Anwendung

## Hinweis
Dieses Repository ist ein **Showcase**. Der vollständige Produktivcode und sensible Konfigurationsdaten bleiben privat.
