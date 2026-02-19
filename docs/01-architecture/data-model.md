# Datenmodell

Letzte Aktualisierung: 2026-02-19

## Status

**Noch nicht implementiert** - Wird in TASK-001 (Projekt-Foundation) definiert.

## Geplante Entitäten

<!-- TODO: In Task "Datenmodell definieren" ausarbeiten -->

### Product (Produkt)
- `id` (UUID, PK)
- `name` (VARCHAR)
- `description` (TEXT)
- `category_id` (UUID, FK)
- `price` (DECIMAL) - optional, für Anfrage
- `image_url` (VARCHAR)
- `active` (BOOLEAN)
- `created_at` (TIMESTAMP)
- `updated_at` (TIMESTAMP)

### Category (Kategorie)
- `id` (UUID, PK)
- `name` (VARCHAR)
- `description` (TEXT)
- `parent_id` (UUID, FK, nullable) - für Unterkategorien
- `sort_order` (INT)
- `active` (BOOLEAN)

### Inquiry (Anfrage)
- `id` (UUID, PK)
- `product_id` (UUID, FK, nullable)
- `company_name` (VARCHAR)
- `contact_person` (VARCHAR)
- `email` (VARCHAR)
- `phone` (VARCHAR)
- `message` (TEXT)
- `status` (VARCHAR) - NEW, IN_PROGRESS, COMPLETED
- `created_at` (TIMESTAMP)
- `updated_at` (TIMESTAMP)

### UsedMachine (Gebrauchtmaschine)
- `id` (UUID, PK)
- `name` (VARCHAR)
- `description` (TEXT)
- `category_id` (UUID, FK)
- `condition` (VARCHAR) - EXCELLENT, GOOD, FAIR
- `year_of_manufacture` (INT)
- `price` (DECIMAL)
- `available` (BOOLEAN)
- `created_at` (TIMESTAMP)
- `updated_at` (TIMESTAMP)

## ER-Diagramm

<!-- TODO: Erstellen wenn Datenmodell finalisiert -->
```
[Wird in späterem Task erstellt]
```
