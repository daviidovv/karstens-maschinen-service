# ADR-001: Datenbank-Wahl

**Datum:** 2026-02-19
**Status:** Accepted

## Kontext

Für das Karstens Maschinen Service Projekt muss eine Datenbank gewählt werden, die die Anforderungen eines B2B E-Commerce Systems erfüllt.

## Optionen

### Option 1: PostgreSQL
- **Pro**: Bewährt, robust, gute Spring Boot Integration, JSON-Support, kostenlos
- **Contra**: Etwas komplexer als MySQL in der Konfiguration

### Option 2: MySQL
- **Pro**: Weit verbreitet, einfach
- **Contra**: Weniger Features als PostgreSQL

### Option 3: MongoDB
- **Pro**: Flexibles Schema, gut für unstrukturierte Daten
- **Contra**: Nicht ideal für relationale Daten, JPA nicht nutzbar

## Entscheidung

**PostgreSQL 16** wird verwendet.

Gründe:
- Konsistenz mit dem Foodtruck-Projekt (gleiche Erfahrung)
- Hervorragende Spring Boot/JPA Integration
- Robuste Transaktionsunterstützung
- JSON-Support für flexible Produktattribute
- Kostenlos und Open Source

## Konsequenzen

- Flyway wird für Migrationen verwendet
- Docker Compose enthält PostgreSQL-Container
- JPA/Hibernate als ORM
- Testcontainers für Integration Tests
