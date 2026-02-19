# API Contracts

Letzte Aktualisierung: 2026-02-19

## Status

**Noch nicht definiert** - Wird bei Implementation der jeweiligen Features erstellt.

## Base URL

```
/api/v1
```

## Geplante Endpoints

### Produkte

```
GET    /api/v1/products              # Alle Produkte (mit Pagination)
GET    /api/v1/products/{id}         # Einzelnes Produkt
GET    /api/v1/products/category/{id} # Produkte einer Kategorie
POST   /api/v1/products              # Produkt erstellen (Admin)
PUT    /api/v1/products/{id}         # Produkt aktualisieren (Admin)
DELETE /api/v1/products/{id}         # Produkt löschen (Admin)
```

### Kategorien

```
GET    /api/v1/categories            # Alle Kategorien
GET    /api/v1/categories/{id}       # Einzelne Kategorie
POST   /api/v1/categories            # Kategorie erstellen (Admin)
PUT    /api/v1/categories/{id}       # Kategorie aktualisieren (Admin)
DELETE /api/v1/categories/{id}       # Kategorie löschen (Admin)
```

### Anfragen

```
POST   /api/v1/inquiries             # Anfrage erstellen
GET    /api/v1/inquiries             # Alle Anfragen (Admin)
GET    /api/v1/inquiries/{id}        # Einzelne Anfrage (Admin)
PATCH  /api/v1/inquiries/{id}/status # Status ändern (Admin)
```

### Gebrauchtmaschinen

```
GET    /api/v1/used-machines         # Alle Gebrauchtmaschinen
GET    /api/v1/used-machines/{id}    # Einzelne Gebrauchtmaschine
POST   /api/v1/used-machines         # Erstellen (Admin)
PUT    /api/v1/used-machines/{id}    # Aktualisieren (Admin)
DELETE /api/v1/used-machines/{id}    # Löschen (Admin)
```

## Response Format

### Erfolg
```json
{
  "data": { ... },
  "message": "Success"
}
```

### Fehler (RFC 7807)
```json
{
  "type": "https://api.karstens-maschinen.de/errors/validation-error",
  "title": "Validation Failed",
  "status": 400,
  "detail": "Die Eingabedaten sind ungültig",
  "instance": "/api/v1/products",
  "timestamp": "2026-02-19T15:30:00Z",
  "errors": [
    {
      "field": "name",
      "message": "Name darf nicht leer sein"
    }
  ]
}
```

## HTTP Status Codes

| Code | Bedeutung |
|------|-----------|
| 200 | OK - GET, PUT, PATCH erfolgreich |
| 201 | Created - POST erfolgreich |
| 204 | No Content - DELETE erfolgreich |
| 400 | Bad Request - Validierungsfehler |
| 401 | Unauthorized - Nicht authentifiziert |
| 403 | Forbidden - Keine Berechtigung |
| 404 | Not Found - Ressource nicht gefunden |
| 500 | Internal Server Error |
