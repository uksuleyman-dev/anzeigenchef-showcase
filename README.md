# Anzeigenchef 📰

> Desktop-App für professionelle Kleinanzeigen-Verwaltung

Eine leistungsstarke Python-Anwendung für die Automatisierung und Verwaltung von Kleinanzeigen-Postings über mehrere Plattformen hinweg.

## 🎯 Features

- **Multi-Plattform-Verwaltung**: Poste Anzeigen auf mehreren Portalen gleichzeitig
- **Browser-Automatisierung**: Automatische Datenerfassung und Posting
- **Lokale Datenverwaltung**: SQLite-basierte Anzeigenverwaltung
- **KI-Integration**: Intelligente Titel- und Beschreibungsgenerierung
- **Batch-Operationen**: Effiziente Verwaltung Hunderte von Anzeigen
- **Desktop-Interface**: Native Python GUI

## 🛠️ Tech Stack

- **Sprache**: Python 3.9+
- **GUI**: Python tkinter
- **Automation**: Selenium / Browser Automation
- **Datenbank**: SQLite
- **KI-Integration**: OpenAI API / Local Models
- **Plattformen**: Ebay Kleinanzeigen, JustHand, Facebook Marketplace, etc.

## 📦 Installation

```bash
# Repository klonen
git clone https://github.com/uksuleyman-dev/anzeigenchef.git
cd anzeigenchef

# Dependencies installieren
pip install -r requirements.txt

# Anwendung starten
python main.py
```

## 🚀 Nutzungsbeispiel

```python
from anzeigenchef import AnzeigenManager

# Manager initialisieren
manager = AnzeigenManager()

# Anzeige erstellen und posten
manager.post_listing(
    title="Möbelstück zu verkaufen",
    description="Gut erhalten, muss weg",
    platforms=["ebay-kleinanzeigen", "facebook"]
)
```

## 📊 Eigenschaften

| Feature | Status |
|---------|--------|
| Multi-Platform Posting | ✅ |
| Automatische Beschreibung | ✅ |
| Batch-Verwaltung | ✅ |
| Analytics | 🔄 In Entwicklung |

## 📝 Dokumentation

Siehe [DOKUMENTATION.md](./docs/dokumentation.md) für detaillierte Anleitungen.

## 🔗 Links

- **Hauptprojekt**: [anzeigenchef](https://github.com/uksuleyman-dev/anzeigenchef)
- **Autor**: [uksuleyman-dev](https://github.com/uksuleyman-dev)

---

*Entwickelt für effiziente und automatisierte Kleinanzeigen-Verwaltung.*