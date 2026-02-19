# System-Übersicht

Letzte Aktualisierung: 2026-02-19

## Architektur

```
┌─────────────────────────────────────────────────────────────┐
│                        Frontend                              │
│                   (React + TypeScript)                       │
│                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐         │
│  │   Kunde     │  │   Admin     │  │  Produkt-   │         │
│  │   Portal    │  │   Panel     │  │  Katalog    │         │
│  └─────────────┘  └─────────────┘  └─────────────┘         │
└─────────────────────────────────────────────────────────────┘
                            │
                            │ REST API (JSON)
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                        Backend                               │
│                (Spring Boot 4 + Java 21)                     │
│                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐         │
│  │ Controller  │──│   Service   │──│ Repository  │         │
│  │   Layer     │  │   Layer     │  │   Layer     │         │
│  └─────────────┘  └─────────────┘  └─────────────┘         │
└─────────────────────────────────────────────────────────────┘
                            │
                            │ JDBC
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                      PostgreSQL 16                           │
└─────────────────────────────────────────────────────────────┘
```

## Komponenten

### Frontend
- **Technologie**: React 18 + TypeScript + Vite
- **Styling**: Tailwind CSS
- **State Management**: React Query (Server State)

### Backend
- **Technologie**: Spring Boot 4.0.1 + Java 21
- **API**: REST (JSON)
- **Security**: Spring Security
- **Validation**: Bean Validation

### Datenbank
- **Technologie**: PostgreSQL 16
- **Migration**: Flyway
- **ORM**: JPA/Hibernate

## Deployment

<!-- TODO: In späterem Task definieren -->
- Containerisierung mit Docker
- CI/CD Pipeline (Jenkins/GitHub Actions)
