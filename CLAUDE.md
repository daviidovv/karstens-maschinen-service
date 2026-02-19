# CLAUDE.md - Karstens Maschinen Service

## Projekt

**Was:** B2B E-Commerce Webanwendung für Postbearbeitungsmaschinen (ähnlich aufpost.de)

**Tech-Stack:** Java 21, Spring Boot 4, PostgreSQL 16, React (geplant), TypeScript, Vite, Tailwind CSS

**Architektur:** Monolith mit Schichtentrennung (Controller → Service → Repository)

## Wichtige Pfade

```
src/main/java/de/karstensmaschinen/service/  # Backend
src/main/resources/db/migration/              # Flyway Migrationen
frontend/src/                                 # React Frontend (noch zu erstellen)
```

## Befehle

```bash
mvn spring-boot:run          # Backend starten
mvn test                     # Backend Tests
docker compose up -d         # PostgreSQL starten
```

## Coding-Standards

**Backend:**
- Constructor Injection (KEIN @Autowired auf Feldern)
- @Transactional(readOnly=true) auf Service-Klasse, @Transactional auf schreibenden Methoden
- Entities NIE direkt nach außen → immer DTOs
- UUID als ID-Typ

**Tests:**
- Naming: `methodName_scenario_expectedBehavior()`
- Arrange-Act-Assert Pattern

## Verhalten

- **Fragen stellen:** Bei Unklarheiten IMMER nachfragen
- **Tests sind Pflicht:** Kein Feature ohne Tests
- **Sprache:** Dokumentation Deutsch, Code/Kommentare Englisch
