# Anzeigenchef — Showcase

> Architektur-Showcase einer Desktop-Anwendung zur strukturierten Verwaltung und Automatisierung von Kleinanzeigen-Workflows.

## Projektidee

Wiederkehrende Abläufe rund um Kleinanzeigen bestehen aus vielen einzelnen Schritten: Daten pflegen, Texte erstellen, Plattformen bedienen, Zustände überwachen und Fehler behandeln. Anzeigenchef bündelt diese Aufgaben in einer Desktop-Anwendung und verbindet lokale Datenhaltung, Browser-Automatisierung und KI-gestützte Inhaltserzeugung.

Dieses öffentliche Repository ist bewusst ein **Showcase**. Es dokumentiert Architektur, Datenfluss und technische Entscheidungen, ohne produktive Zugangsdaten oder private Nutzerdaten offenzulegen.

## Architekturüberblick

```text
┌──────────────────────────┐
│ Desktop-Oberfläche       │
│ CustomTkinter            │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│ Anwendungslogik          │
│ Jobs · Status · Regeln   │
└───────┬─────────┬────────┘
        │         │
        ▼         ▼
┌─────────────┐  ┌──────────────────┐
│ DataManager │  │ KI-Generatoren   │
│ lokale Daten│  │ OpenAI/ChatGPT   │
└─────────────┘  └──────────────────┘
        │
        ▼
┌──────────────────────────┐
│ Browser-Automatisierung  │
│ Playwright               │
└────────────┬─────────────┘
             ▼
      externe Plattformen
```

## Technische Schwerpunkte

- **Python** als zentrale Anwendungssprache
- **CustomTkinter** für die Desktop-Oberfläche
- **Playwright** für Browser-Automatisierung
- **JSON-basierte lokale Datenhaltung**
- **OpenAI/ChatGPT-Integration** für unterstützte Textgenerierung
- Nebenläufige Verarbeitung für längere Aufgaben
- Fehlerbehandlung, Retries und robuste Selektorlogik
- Backups und Trennung sensibler lokaler Daten vom öffentlichen Code

## Daten- und Kontrollfluss

```text
Benutzereingabe
      ↓
Validierung / Anwendungslogik
      ↓
lokaler Datensatz
      ├────────→ KI-Unterstützung → Textvorschlag
      │
      └────────→ Automationsauftrag
                         ↓
                    Playwright
                         ↓
                externe Plattform
                         ↓
                 Status / Fehler
                         ↓
                 lokale Rückmeldung
```

Wichtig ist dabei die Trennung zwischen **fachlichem Zustand** und **Browserzustand**. Ein fehlgeschlagener Browser-Schritt soll nicht automatisch bedeuten, dass der lokale Datensatz inkonsistent wird.

## Architekturentscheidungen

### Browser-Automatisierung als eigene Schicht
Die Plattforminteraktion ist von GUI und Datenhaltung getrennt. Dadurch können Selektoren, Abläufe und Fehlerbehandlung geändert werden, ohne die gesamte Anwendung neu zu strukturieren.

### Lokale Datenhoheit
Produktive Daten und Zugangsinformationen verbleiben lokal. Der öffentliche Showcase enthält keine Secrets oder persönlichen Datensätze.

### KI als unterstützende Komponente
KI-generierte Inhalte sind ein Baustein im Workflow und nicht die zentrale Systemwahrheit. Dadurch bleibt die Anwendung auch dann strukturell verständlich, wenn Modell oder Provider ausgetauscht werden.

### Fehlertoleranz
Browser-Automatisierung ist von externen Oberflächen abhängig. Deshalb gehören Timeouts, Retries, Statusrückgabe und kontrollierte Fehlerzustände zur Architektur und nicht nur zur Ausnahmebehandlung.

## Was dieses Projekt demonstriert

Anzeigenchef zeigt insbesondere die Integration unterschiedlicher technischer Verantwortlichkeiten in ein Gesamtsystem:

**Desktop UI → Anwendungslogik → persistente Daten → KI-Service → Browser-Automatisierung → externe Systeme**

Der architektonische Schwerpunkt liegt damit auf **Integration, klaren Komponentengrenzen, Zustandsmanagement und resilienten Automationsabläufen**.

## Inhalt dieses Showcases

- `README.md` — Projekt- und Architekturüberblick
- `ARCHITECTURE.md` — Komponenten, Datenflüsse und Designentscheidungen
- `examples/workflow.md` — anonymisiertes Beispiel eines Automationsablaufs

## Datenschutz

Produktive Daten, Zugangsdaten und interne Implementierungsdetails werden nicht veröffentlicht. Der Showcase beschreibt die technische Struktur und die daraus ableitbaren Engineering-Entscheidungen.

---

**Portfolio-Schwerpunkt:** Automation · AI Integration · System Integration · Resiliente Workflows
