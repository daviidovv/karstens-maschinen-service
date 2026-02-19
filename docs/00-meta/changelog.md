# Changelog

## Zweck dieser Datei
Chronik der wichtigen Projektänderungen. Gibt Überblick über die Entwicklung.

## Verwendung
- **Wann ausfüllen**: Nach jedem Major Milestone, Feature oder wichtiger Änderung
- **Wann referenzieren**: Bei Reviews, Retrospektiven, Status-Updates
- **Wann aktualisieren**: Wöchentlich oder nach größeren Changes

## Was du mit dem LLM machst
```
Prompt: "Aktualisiere den Changelog in /docs/00-meta/changelog.md mit folgenden Änderungen:

[Beschreibung was passiert ist]"
```

## Format

Gruppiere nach Datum und Kategorie:

```markdown
## YYYY-MM-DD

### [Kategorie] (z.B. Features, Datenbank, Architektur, Bugfixes)
- [Änderung 1]
- [Änderung 2]

### [Kategorie 2]
- [Änderung 3]
```

## Kategorien-Vorschläge
- **Features**: Neue Funktionalität
- **Datenbank**: Schema-Änderungen
- **Architektur**: Strukturelle Änderungen
- **Bugfixes**: Behobene Fehler
- **Refactoring**: Code-Verbesserungen
- **Dependencies**: Library-Updates
- **Dokumentation**: Doku-Updates
- **Tests**: Test-Verbesserungen
- **Performance**: Performance-Optimierungen
- **Security**: Sicherheits-Verbesserungen

## Was gehört rein?
JA:
- Neue Features
- Breaking Changes
- Wichtige Bugfixes
- Architekturänderungen
- Major Refactorings
- Dependency-Updates

NEIN:
- Typo-Fixes
- Code-Formatierung
- Triviale Änderungen

---

## 2026-02-19

### Projekt-Setup
- Projekt initialisiert mit Spring Boot 4.0.1
- Dokumentationsstruktur erstellt
- Git-Repository aufgesetzt und nach GitHub gepusht
