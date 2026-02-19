# Projekt-Vision: Karstens Maschinen

Letzte Aktualisierung: 2026-02-19

---

## Kurzbeschreibung (für den Bekannten)

> **Was wir bauen:**
>
> Eine professionelle Website für deine Maschinen - besser als eBay, einfacher zu pflegen.
>
> **Wie es funktioniert:**
> - Du legst einmal alle Maschinentypen an die du handelst (Katalog)
> - Diese sind immer sichtbar mit "auf Anfrage"
> - Wenn du eine Maschine fertig repariert hast: Typ auswählen, Preis + Fotos eintragen, fertig
> - Der Kunde sieht dann: "2 Stück auf Lager" + kann direkt anfragen
> - Wenn verkauft: Ein Klick → weg. Der Katalog-Eintrag bleibt aber
>
> **Dein Aufwand:**
> - Einmalig: Katalog anlegen (machen wir zusammen vor, mit Beispieldaten)
> - Danach: Nur noch Lagermaschinen eintragen wenn du welche fertig hast (2-3 Min pro Maschine)
> - Anfragen kommen per E-Mail, du siehst sie auch im Admin-Bereich
>
> **Was du brauchst:**
> - Internet und einen Browser (Handy, Tablet oder PC)
> - Das war's

---

## Geschäftsziel

Professionelle Website für **Karstens Maschinen** - Verkauf von reparierten/generalüberholten Postbearbeitungsmaschinen an Geschäftskunden.

### Kernproblem

**Aktuelle Situation:**
- Maschinen werden aktuell über eBay verkauft
- eBay wirkt unprofessionell für B2B-Kunden
- eBay-Gebühren
- Kein größeres Sortiment darstellbar (nur was auf Lager ist)
- Keine eigene Marke/Präsenz

**Was fehlt:**
- Professionelle Präsentation der Maschinen
- Möglichkeit auch Maschinen zu zeigen die auf Anfrage beschaffbar sind
- Eigene Website = mehr Vertrauen bei Geschäftskunden
- Einfache Selbstverwaltung ohne Abhängigkeit von Dritten

### Lösung

Eine eigene Website mit:
1. **Produktkatalog**: Alle Maschinentypen die gehandelt werden (immer sichtbar)
2. **Lagerbestand**: Konkrete Maschinen die gerade verfügbar sind
3. **Anfrage-System**: Kunden können direkt anfragen, bekommen individuelles Angebot
4. **Ankauf-Formular**: Besucher können eigene Maschinen zum Verkauf anbieten
5. **Admin-Bereich**: Selbstständige Pflege ohne Programmierkenntnisse

---

## Geschäftsmodell

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  Defekte        │     │  Karstens       │     │  Geschäfts-     │
│  Maschinen      │────▶│  Maschinen      │────▶│  kunden         │
│  (Ankauf)       │     │  (Reparatur)    │     │  (Verkauf)      │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

- **Ankauf**: Defekte/alte Maschinen von Unternehmen
- **Reparatur**: Generalüberholung
- **Verkauf**: An Geschäftskunden (B2B)

---

## Das Katalog + Lager System

### Konzept

**Zwei Arten von Einträgen:**

| Typ | Beschreibung | Beispiel |
|-----|--------------|----------|
| **Katalog-Eintrag** | Maschinentyp den er generell handelt | "Pitney Bowes DI950" |
| **Lager-Maschine** | Konkrete Maschine die gerade da ist | "DI950, Bj. 2019, 2.450€" |

### Wie es zusammenspielt

```
KATALOG-EINTRAG: Pitney Bowes DI950
├── Allgemeine Beschreibung (was kann die Maschine)
├── Typische Specs (Geschwindigkeit, Formate)
├── Hersteller-/Beispielbild
├── Status: "Auf Anfrage verfügbar"
│
└── LAGER-MASCHINEN (verknüpft):
    ├── #1: Baujahr 2019, sehr gut, 2.450€, [eigene Fotos]
    ├── #2: Baujahr 2017, gut, 1.890€, [eigene Fotos]
    └── (wenn verkauft → verschwindet, Katalog bleibt)
```

### Was der Kunde sieht

```
┌─────────────────────────────────────────────────────────────────┐
│                    Pitney Bowes DI950                           │
│                    Kuvertiermaschine                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  [Bild]  Hochleistungs-Kuvertiermaschine für mittlere bis      │
│          große Postmengen. Verarbeitet bis zu 3.500 Briefe     │
│          pro Stunde.                                            │
│                                                                 │
│  ════════════════════════════════════════════════════════════  │
│                                                                 │
│  🟢 AKTUELL 2 AUF LAGER:                                       │
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ [Foto]  Baujahr 2019 │ Sehr gut │ 2.450 €              │   │
│  │         Komplett generalüberholt, neue Rollen           │   │
│  │                                    [ Anfragen ]         │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ [Foto]  Baujahr 2017 │ Gut │ 1.890 €                   │   │
│  │         Technisch einwandfrei, optische Gebrauchsspuren │   │
│  │                                    [ Anfragen ]         │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  ────────────────────────────────────────────────────────────  │
│  Keine passende dabei? Wir können diese Maschine auch          │
│  auf Anfrage für Sie besorgen.    [ Allgemeine Anfrage ]       │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Workflow im Admin

**Einmalig: Katalog anlegen**
```
1. "Neuer Katalog-Eintrag"
2. Name: Pitney Bowes DI950
3. Kategorie: Kuvertiermaschine
4. Allgemeine Beschreibung
5. Typische Preisspanne: ab 1.500€
6. Fertig → ist jetzt "auf Anfrage" sichtbar
```

**Regelmäßig: Lagermaschine eintragen (wenn eine fertig repariert ist)**
```
1. "Neue Lagermaschine"
2. Basiert auf: [Pitney Bowes DI950 ▼]  ← Dropdown, wählt Katalog-Eintrag
   → Name, Kategorie, Basis-Beschreibung werden übernommen!
3. Nur noch eingeben:
   - Baujahr: 2019
   - Zustand: Sehr gut
   - Preis: 2.450€
   - Besonderheiten: "Neue Rollen, komplett überholt"
   - Fotos hochladen
4. Speichern → sofort online, Kunde sieht "1 auf Lager"
```

**Wenn verkauft:**
```
1. Lagermaschine öffnen
2. Status: "Verkauft"
3. Speichern → verschwindet aus Anzeige
   (Katalog-Eintrag "Pitney Bowes DI950" bleibt aber mit "auf Anfrage")
```

### Vorteile dieses Systems

| Für den Bekannten | Für den Kunden |
|-------------------|----------------|
| Katalog nur einmal anlegen | Sieht alle Maschinen die es gibt |
| Lagermaschine in 2-3 Min eintragen | Sieht sofort was auf Lager ist |
| Wenig Tipparbeit (erbt vom Katalog) | Kann konkrete Maschine anfragen |
| Verkauft = 1 Klick | Oder allgemein anfragen |
| Katalog bleibt immer vollständig | Professioneller Eindruck |

---

## Zielgruppe

### Käufer (Primär)
- **Kleine/mittlere Unternehmen** mit Postversand
- **Behörden und Ämter**
- **Vereine und Organisationen**
- **Steuerberater, Anwaltskanzleien** (viel Briefverkehr)

**Warum Gebraucht kaufen?**
- Deutlich günstiger als Neugeräte
- Generalüberholt = zuverlässig
- Für gelegentliche Nutzung reicht gebraucht

### Verkäufer (Sekundär)
- Unternehmen die alte Maschinen loswerden wollen
- Firmen die auf neuere Modelle umsteigen

### Administrator
- Der Bekannte selbst
- Muss Maschinen selbst pflegen können

---

## Funktionsumfang

### Für Kunden (öffentliche Website)

**Muss (MVP):**
- [ ] Startseite mit Firmenvorstellung
- [ ] Produktkatalog (alle Maschinentypen)
- [ ] Lagerbestand-Anzeige (was gerade da ist)
- [ ] Filterung nach Kategorie
- [ ] Suchfunktion
- [ ] Produktdetailseite mit Lagermaschinen
- [ ] **Anfrage-Button** bei jeder Maschine (Lager + Katalog)
- [ ] **Allgemeines Kontaktformular**
- [ ] **Ankauf-Formular** (eigene Maschine anbieten)
- [ ] Impressum & Datenschutz
- [ ] Responsive Design (Handy, Tablet, Desktop)

**Nice-to-have (später):**
- [ ] Merkliste / Favoriten
- [ ] "Neu eingetroffen" Badge
- [ ] FAQ-Bereich

### Für Admin (geschützter Bereich)

**Muss (MVP):**
- [ ] Login (einfach, ein Admin-Account)
- [ ] **Katalog-Einträge verwalten** (Maschinentypen)
- [ ] **Lagermaschinen verwalten** (konkrete Maschinen)
- [ ] **Kategorien verwalten**
- [ ] **Anfragen einsehen** (Produkt + Kontakt + Ankauf)
- [ ] Anfragen als "bearbeitet" markieren
- [ ] Fotos hochladen (Drag & Drop)

**Nice-to-have (später):**
- [ ] Dashboard mit Statistiken
- [ ] Lagermaschine duplizieren
- [ ] E-Mail-Benachrichtigung bei neuer Anfrage

---

## Datenfelder

### Katalog-Eintrag (Maschinentyp)

| Feld | Pflicht | Beschreibung |
|------|---------|--------------|
| Name | Ja | z.B. "Pitney Bowes DI950" |
| Kategorie | Ja | z.B. Kuvertiermaschine |
| Hersteller | Ja | z.B. Pitney Bowes |
| Beschreibung | Ja | Allgemeine Infos zur Maschine |
| Bild | Ja | Hersteller-/Beispielbild |
| Preisspanne | Optional | z.B. "ab 1.500€" |
| Technische Daten | Optional | Geschwindigkeit, Formate, etc. |

### Lagermaschine (konkret)

| Feld | Pflicht | Beschreibung |
|------|---------|--------------|
| Katalog-Eintrag | Ja | Verknüpfung zum Typ |
| Baujahr | Ja | z.B. 2019 |
| Zustand | Ja | Sehr gut / Gut / Gebraucht |
| Preis | Ja | Konkreter Preis in € |
| Fotos | Ja | Eigene Fotos dieser Maschine |
| Besonderheiten | Optional | Was ist besonders an dieser |
| Status | Ja | Auf Lager / Reserviert / Verkauft |

---

## Produktkategorien (Vorschlag)

*⚠️ Mit Bekanntem klären*

1. **Kuvertiermaschinen** (Falzen + Kuvertieren)
2. **Frankiermaschinen** (Porto drucken)
3. **Adressdrucker** (Umschläge bedrucken)
4. **Falzmaschinen** (nur Falzen)
5. **Brieföffner** (automatisches Öffnen)
6. **Zubehör & Verbrauchsmaterial**

---

## Vorbefüllung mit Beispieldaten

### Strategie

```
1. Wir recherchieren typische Maschinen (Pitney Bowes, Neopost, etc.)
2. Wir legen Katalog-Einträge an mit:
   - Namen
   - Allgemeinen Beschreibungen
   - Herstellerbildern (oder Platzhaltern)
   - Typischen Specs
3. Der Bekannte:
   - Schaut sich alles an
   - Löscht was er nicht handelt
   - Passt Beschreibungen an
   - Fügt seine Lagermaschinen hinzu
```

### Beispiel-Maschinen für Katalog

| Maschine | Kategorie | Hersteller |
|----------|-----------|------------|
| Pitney Bowes DI950 | Kuvertiermaschine | Pitney Bowes |
| Pitney Bowes Relay 1000 | Kuvertiermaschine | Pitney Bowes |
| Neopost DS-75 | Kuvertiermaschine | Neopost |
| Neopost DS-200 | Kuvertiermaschine | Neopost |
| Francotyp PostBase Mini | Frankiermaschine | Francotyp |
| Frama Matrix F32 | Frankiermaschine | Frama |
| Pitney Bowes SendPro C | Frankiermaschine | Pitney Bowes |

---

## Nicht-Ziele (MVP)

**Explizit NICHT im ersten Release:**

- ❌ **Kein Warenkorb / Online-Kauf**
- ❌ **Keine Zahlungsabwicklung** (Zahlung auf Rechnung)
- ❌ **Keine Kundenkonten**
- ❌ **Keine Bewertungen/Reviews**
- ❌ **Kein Newsletter**
- ❌ **Keine mobile App**
- ❌ **Keine eBay-Integration**

---

## Erfolgskriterien

### Für den Bekannten
- [ ] Kann selbstständig Katalog pflegen
- [ ] Kann Lagermaschinen in < 3 Min eintragen
- [ ] Bekommt Anfragen per E-Mail
- [ ] Website sieht professioneller aus als eBay

### Für Kunden
- [ ] Sehen alle Maschinentypen (Katalog)
- [ ] Sehen was auf Lager ist
- [ ] Können einfach anfragen

### Technisch
- [ ] Mobile-optimiert
- [ ] Schnelle Ladezeiten
- [ ] DSGVO-konform
- [ ] Einfacher Admin-Bereich

---

## Offene Fragen

Siehe: `docs/04-tasks/backlog/TASK-001-vision-ausarbeiten.md`

---

## Zusammenfassung

**In einem Satz:** Professionelle Website mit Produktkatalog + Lagerbestand, wo der Bekannte selbst Maschinen pflegen kann.

**Das Besondere:**
- Katalog = alle Maschinentypen (immer sichtbar, "auf Anfrage")
- Lager = konkrete Maschinen (erscheinen automatisch beim Katalog-Eintrag)
- Wenig Aufwand: Lagermaschine erbt vom Katalog, nur Preis/Fotos/Zustand eingeben
