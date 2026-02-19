# Mandatory Context - Karstens Maschinen Service

> **Hinweis:** Dies ist eine Referenzdatei mit detaillierten Tech-Informationen.
> Für den täglichen Workflow: siehe `CLAUDE.md` im Root-Verzeichnis.

Letzte Aktualisierung: 2026-02-19

---

## Tech-Stack

### Backend
- **Java**: 21
- **Spring Boot**: 4.0.1
- **Datenbank**: PostgreSQL 16
- **Build Tool**: Maven 3.9+
- **Migration Tool**: Flyway

### Frontend (geplant)
- **Framework**: React 18+
- **Language**: TypeScript 5+
- **Build Tool**: Vite 5+
- **Package Manager**: npm
- **Styling**: Tailwind CSS 3+
- **HTTP Client**: Axios 1.6+
- **State Management**: React Query (TanStack Query) 5+
- **Routing**: React Router 6+

### Testing

**Backend:**
- JUnit 5 (Jupiter)
- Mockito 5+
- AssertJ
- Testcontainers (PostgreSQL)
- Spring Boot Test

**Frontend:**
- Vitest (Unit Tests)
- React Testing Library

### DevOps & Tools
- **Containerisierung**: Docker & Docker Compose
- **API Dokumentation**: SpringDoc OpenAPI (Swagger UI)
- **Versionskontrolle**: Git + GitHub

---

## Spring Boot Module

### Produktive Dependencies
```xml
- spring-boot-starter-web (REST API)
- spring-boot-starter-data-jpa (Datenbankzugriff)
- spring-boot-starter-validation (Bean Validation)
- spring-boot-starter-security (Security)
- spring-boot-starter-actuator (Health Checks & Monitoring)
- spring-boot-starter-flyway (DB Migrations)
- flyway-database-postgresql (PostgreSQL Support)
- postgresql (PostgreSQL JDBC Driver)
- lombok (Code-Generierung)
```

### Test Dependencies
```xml
- spring-boot-starter-test
- spring-boot-starter-security-test
- h2 (In-Memory DB für Tests)
- testcontainers (Container-basierte Integration Tests)
```

---

## Package-Struktur

### Backend (Java)
```
de.karstensmaschinen.service
├── controller          # REST Controller
├── service            # Business Logic
├── repository         # Data Access Layer (JPA Repositories)
├── entity             # JPA Entities
├── dto                # Data Transfer Objects
│   ├── request        # Request DTOs
│   └── response       # Response DTOs
├── mapper             # Entity ↔ DTO Mapper
├── exception          # Custom Exceptions
├── config             # Configuration Classes
└── security           # Security Configuration
```

### Frontend (React + TypeScript) - geplant
```
src/
├── components/        # React Components
│   ├── ui/           # Reusable UI Components
│   └── features/     # Feature-spezifische Components
├── pages/            # Page Components (Routen)
├── hooks/            # Custom React Hooks
├── services/         # API Services (Axios)
├── types/            # TypeScript Types & Interfaces
└── utils/            # Utility Functions
```

---

## Coding-Constraints

### Backend (Java)

**Dependency Injection:**
- Constructor Injection (IMMER)
- Field Injection (@Autowired auf Feldern) VERBOTEN

**Lombok:**
- @Data, @Builder, @NoArgsConstructor, @AllArgsConstructor für DTOs und Entities
- @Slf4j für Logging
- @SneakyThrows VERBOTEN
- @Cleanup VERBOTEN

**Validation:**
- @Validated auf allen Controllern
- Bean Validation Annotations auf DTOs (@NotNull, @NotBlank, @Email, @Size, etc.)

**Transactions:**
- @Transactional(readOnly = true) auf Service-Klassen-Ebene
- @Transactional (ohne readOnly) auf schreibenden Methoden
- Transactions NIEMALS in Controllern

**Entities:**
- IMMER Audit-Felder (createdAt, updatedAt)
- UUID als ID-Typ (nicht Long/Integer)
- Business-Logik in Entities VERBOTEN

**DTOs:**
- Separate Request und Response DTOs
- Entities NIEMALS direkt nach außen geben
- Mapper-Klassen für Entity ↔ DTO Konvertierung

---

## API-Standard

### Base URL
```
/api/v1
```

### Content Type
```
Content-Type: application/json
```

### HTTP-Status-Codes

**Erfolg:**
- `200 OK` - GET, PUT, PATCH erfolgreich
- `201 Created` - POST erfolgreich, Ressource erstellt
- `204 No Content` - DELETE erfolgreich

**Client-Fehler:**
- `400 Bad Request` - Validierungsfehler
- `401 Unauthorized` - Nicht authentifiziert
- `403 Forbidden` - Keine Berechtigung
- `404 Not Found` - Ressource nicht gefunden
- `422 Unprocessable Entity` - Business-Regel-Verletzung

**Server-Fehler:**
- `500 Internal Server Error` - Unerwarteter Serverfehler

---

## Qualitäts-Gates

### Backend
- Test-Coverage: Min. 80%
- Keine Compiler-Warnings
- Alle Tests müssen grün sein
- Flyway-Migrationen rückwärtskompatibel

### Frontend
- Test-Coverage: Min. 70%
- ESLint Errors: 0
- TypeScript Errors: 0
- Build erfolgreich (Vite)

---

## Naming Conventions

### Backend (Java)

**Klassen:**
- Controller: `*Controller` (z.B. `ProductController`)
- Service: `*Service` (z.B. `ProductService`)
- Repository: `*Repository` (z.B. `ProductRepository`)
- Entity: Kein Suffix (z.B. `Product`)
- DTO Request: `*Request` (z.B. `CreateProductRequest`)
- DTO Response: `*Response` (z.B. `ProductResponse`)
- Mapper: `*Mapper` (z.B. `ProductMapper`)
- Exception: `*Exception` (z.B. `ProductNotFoundException`)

**Methoden:**
- CRUD: `create*`, `get*`, `update*`, `delete*`
- Finder: `findBy*`, `findAllBy*`
- Boolean: `is*`, `has*`, `can*`

---

## Environment Variables

### Backend (application.properties / .env)
```
# Database
DB_USERNAME=postgres
DB_PASSWORD=postgres
DB_HOST=localhost
DB_PORT=5432
DB_NAME=karstens_maschinen

# Server
SERVER_PORT=8080
```

### Frontend (.env)
```bash
VITE_API_BASE_URL=http://localhost:8080/api/v1
VITE_APP_TITLE=Karstens Maschinen
```
