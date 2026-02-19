# Review Checklist

Nutze diese Checkliste für Self-Reviews und Code Reviews.

## Funktionalität

- [ ] Code erfüllt die Anforderungen des Tasks
- [ ] Edge Cases berücksichtigt
- [ ] Fehlerbehandlung vollständig
- [ ] Keine offensichtlichen Bugs

## Code-Qualität

- [ ] Code ist lesbar und verständlich
- [ ] Keine unnötige Komplexität
- [ ] DRY-Prinzip eingehalten
- [ ] SOLID-Prinzipien beachtet
- [ ] Keine Magic Numbers/Strings
- [ ] Sinnvolle Variablen- und Methodennamen

## Architektur

- [ ] Richtige Layer-Zuordnung (Controller/Service/Repository)
- [ ] Keine Business-Logik in Controllern
- [ ] DTOs statt Entities nach außen
- [ ] Constructor Injection verwendet

## Tests

- [ ] Tests vorhanden und sinnvoll
- [ ] Positive und negative Cases getestet
- [ ] Mocking korrekt eingesetzt
- [ ] Tests sind unabhängig voneinander

## Sicherheit

- [ ] Keine SQL-Injection möglich (JPA verwendet)
- [ ] Input-Validierung vorhanden
- [ ] Keine sensiblen Daten im Log
- [ ] Keine Credentials im Code

## Performance

- [ ] N+1 Query-Problem vermieden
- [ ] Pagination bei Listen
- [ ] Lazy Loading sinnvoll eingesetzt
- [ ] Keine unnötigen DB-Abfragen

## Dokumentation

- [ ] JavaDoc für öffentliche APIs
- [ ] Komplexe Logik kommentiert
- [ ] API-Dokumentation aktuell
