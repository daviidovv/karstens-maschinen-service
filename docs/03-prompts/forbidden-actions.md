# Forbidden Actions - Karstens Maschinen Service

> **Hinweis:** Dies ist eine Referenzdatei mit allen Verboten.
> Für den täglichen Workflow: siehe `CLAUDE.md` im Root-Verzeichnis.

Letzte Aktualisierung: 2026-02-19

---

## Code-Änderungen

**VERBOTEN ohne explizite Erlaubnis:**

- **Package-Umbenennung**: `de.karstensmaschinen.service` darf NICHT geändert werden
- **API-Breaking-Changes**: Bestehende REST-Endpoints dürfen nicht geändert/gelöscht werden
- **Dependencies hinzufügen**: Neue Maven/npm Dependencies nur nach Genehmigung
- **Refactoring > 3 Klassen**: Größere Refactorings müssen angekündigt werden
- **Löschen von bestehendem Code**: Keine Code-Deletion ohne Begründung
- **Java-Version ändern**: Java 21 ist festgelegt
- **Spring Boot Version ändern**: 4.0.1 ist festgelegt (Patches erlaubt)

---

## Architektur

**VERBOTEN ohne ADR (Architecture Decision Record):**

- **REST → GraphQL**: API-Style darf nicht geändert werden
- **Neue Layer einführen**: Layered Architecture (Controller→Service→Repository) darf nicht erweitert werden
- **Datenbank wechseln**: PostgreSQL 16 ist gesetzt
- **ORM wechseln**: JPA/Hibernate darf nicht durch andere ORMs ersetzt werden
- **Microservices**: System ist monolithisch, keine Aufteilung ohne ADR
- **Frontend-Framework ändern**: React ist gesetzt (wenn Frontend implementiert)

---

## Qualität

**NIEMALS:**

- **Tests löschen**: Bestehende Tests dürfen NICHT entfernt werden
- **Test-Coverage senken**: Min. 80% (Backend) / 70% (Frontend) muss gehalten werden
- **Validierungen entfernen**: Bean Validation darf nicht geschwächt werden
- **Security-Features deaktivieren**: Spring Security darf nicht umgangen werden
- **Compiler-Warnings ignorieren**: Alle Warnings müssen behoben werden
- **Code ohne Tests committen**: Jede Änderung braucht Tests

---

## Datenbank

**VERBOTEN ohne Erlaubnis:**

- **Bestehende Flyway-Migrationen ändern**: V1__*, V2__* etc. sind immutable
- **Breaking Schema Changes**: Spalten/Tabellen löschen nur mit Migration-Strategie
- **Daten löschen**: DELETE-Statements nur mit expliziter Genehmigung
- **Schema-Änderungen ohne Flyway**: Alle DB-Changes müssen über Flyway-Migrationen laufen
- **ID-Typ ändern**: UUID ist gesetzt, keine Long/Integer IDs

---

## Anti-Patterns

**NIEMALS verwenden:**

### Backend (Java/Spring Boot)

- **Field Injection**: `@Autowired` auf Feldern ist VERBOTEN
  - **Stattdessen**: Constructor Injection IMMER verwenden

- **Entities nach außen exponieren**: Entities dürfen NIEMALS in Controller-Signaturen erscheinen
  - **Stattdessen**: DTOs (Request/Response) verwenden

- **Business Logic in Controllern**: Controller nur für HTTP-Handling
  - **Stattdessen**: Business Logic in Services

- **God Classes**: Klassen > 500 Zeilen
  - **Stattdessen**: Aufteilen in kleinere Klassen

- **Lombok @SneakyThrows**: Versteckt Exceptions
  - **Stattdessen**: Explizites Exception Handling

- **@Transactional in Controllern**: Transactions gehören in Services
  - **Stattdessen**: @Transactional auf Service-Ebene

- **Hardcoded Credentials**: Passwörter/Keys im Code
  - **Stattdessen**: application.properties mit Environment Variables

### Frontend (React/TypeScript)

- **`any` Type überall**: TypeScript-Vorteile werden zunichte gemacht
  - **Stattdessen**: Explizite Interfaces/Types

- **Redux für alles**: Redux ist zu komplex für dieses Projekt
  - **Stattdessen**: React Query (Server State) + useState (UI State)

- **Class Components**: Nur Functional Components
  - **Stattdessen**: Functional Components mit Hooks

- **Fetch API direkt**: Keine rohen fetch()-Calls
  - **Stattdessen**: Axios + React Query

---

## Dokumentation

**NIEMALS:**

- **ADRs löschen**: Architecture Decision Records sind Historie
- **Abgeschlossene Tasks ändern**: `/docs/04-tasks/completed/` ist immutable
- **Definition of Done ignorieren**: Alle Tasks müssen DoD erfüllen
- **Changelog nicht pflegen**: Jeder größere Change muss in changelog.md

---

## Projektspezifische Verbote

### B2B-Shop-spezifisch

- **B2C-Features**: Keine Endkunden-Features (Widerrufsrecht, etc.)
  - **Warum**: Nur B2B-Kunden

- **Zahlungsintegration in MVP**: Kein Payment-Gateway
  - **Warum**: Zahlung auf Rechnung, nicht online

---

## Erweitern bei Problemen!

**Wenn das LLM etwas Falsches macht:**
1. Füge es hier als verbotene Aktion hinzu
2. Erkläre WARUM es verboten ist
3. Füge Datum hinzu wann Problem auftrat
4. Das verhindert, dass es wieder passiert

**Format:**
```markdown
- **[Aktion]**: [Kurzbeschreibung]
  - **Warum**: [Begründung]
  - **Problem aufgetreten am**: [Datum]
  - **Stattdessen**: [Alternative]
```
