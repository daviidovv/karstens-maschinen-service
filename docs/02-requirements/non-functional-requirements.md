# Nicht-funktionale Anforderungen

Letzte Aktualisierung: 2026-02-19

## Performance

- **Seitenladezeit**: < 3 Sekunden
- **API-Response**: < 500ms (95. Perzentil)

## Verfügbarkeit

- **Uptime**: 99%
- **Geplante Wartung**: außerhalb Geschäftszeiten

## Sicherheit

- **HTTPS**: Pflicht
- **Passwörter**: Verschlüsselt gespeichert (bcrypt)
- **SQL-Injection**: Verhindert durch JPA
- **XSS**: Verhindert durch React

## Skalierbarkeit

- **Gleichzeitige Nutzer**: Min. 100
- **Datenbankgröße**: Min. 10.000 Produkte

## Wartbarkeit

- **Test-Coverage Backend**: Min. 80%
- **Dokumentation**: Alle APIs dokumentiert
- **Code-Standards**: Einheitlich (siehe code-standards.md)

## Kompatibilität

- **Browser**: Chrome, Firefox, Safari, Edge (aktuelle Versionen)
- **Mobile**: Responsive Design (Mobile First)

## Rechtliches

- **DSGVO**: Vollständig konform
- **Impressum**: Pflichtangaben
- **B2B**: Kein Widerrufsrecht für Geschäftskunden
