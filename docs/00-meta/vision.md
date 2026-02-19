# Projekt-Vision: Karstens Maschinen

Letzte Aktualisierung: 2026-02-19

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
1. **Produktkatalog**: Alle Maschinen übersichtlich präsentiert
2. **Zwei Verfügbarkeitstypen**: "Auf Lager" (sofort) + "Auf Anfrage" (beschaffbar)
3. **Anfrage-System**: Kunden können direkt anfragen, bekommen individuelles Angebot
4. **Ankauf-Formular**: Besucher können eigene Maschinen zum Verkauf anbieten
5. **Admin-Bereich**: Selbstständige Pflege der Maschinen ohne Programmierkenntnisse

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
- **Reparatur**: Generalüberholung durch den Bekannten
- **Verkauf**: An Geschäftskunden (B2B)

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
- Muss Maschinen selbst pflegen können (hinzufügen, bearbeiten, löschen)

---

## Funktionsumfang

### Für Kunden (öffentliche Website)

**Muss (MVP):**
- [ ] Startseite mit Firmenvorstellung
- [ ] Produktkatalog mit allen Maschinen
- [ ] Filterung nach Kategorie
- [ ] Suchfunktion
- [ ] Produktdetailseite (Fotos, Beschreibung, Preis, technische Daten)
- [ ] Verfügbarkeitsstatus: "Auf Lager" / "Auf Anfrage"
- [ ] **Anfrage-Button** bei jeder Maschine
- [ ] **Allgemeines Kontaktformular**
- [ ] **Ankauf-Formular** (eigene Maschine anbieten)
- [ ] Impressum & Datenschutz
- [ ] Responsive Design (Handy, Tablet, Desktop)

**Nice-to-have (später):**
- [ ] Merkliste / Favoriten
- [ ] Ähnliche Produkte anzeigen
- [ ] FAQ-Bereich
- [ ] Blog/News (z.B. neue Maschinen eingetroffen)

### Für Admin (geschützter Bereich)

**Muss (MVP):**
- [ ] Login (einfach, nur ein Admin-Account)
- [ ] **Maschinen verwalten**:
  - Hinzufügen (Name, Beschreibung, Preis, Kategorie, Fotos, Status)
  - Bearbeiten
  - Löschen
  - Status ändern (Auf Lager / Auf Anfrage / Verkauft / Versteckt)
- [ ] **Kategorien verwalten** (hinzufügen, bearbeiten, löschen)
- [ ] **Anfragen einsehen** (Produktanfragen + Kontaktanfragen + Ankauf-Anfragen)
- [ ] Anfragen als "bearbeitet" markieren

**Nice-to-have (später):**
- [ ] Dashboard mit Statistiken (Anfragen pro Woche, beliebteste Maschinen)
- [ ] Mehrere Fotos pro Maschine mit Sortierung
- [ ] Maschine duplizieren (für ähnliche Modelle)
- [ ] Export der Anfragen als CSV

---

## Datenfelder pro Maschine

**Pflichtfelder:**
| Feld | Beschreibung |
|------|--------------|
| Name/Titel | z.B. "Pitney Bowes DI950" |
| Kategorie | z.B. Kuvertiermaschine |
| Beschreibung | Freitext, was kann die Maschine |
| Preis | In Euro (oder "Auf Anfrage") |
| Status | Auf Lager / Auf Anfrage / Verkauft |
| Hauptbild | Mindestens ein Foto |

**Optionale Felder:**
| Feld | Beschreibung |
|------|--------------|
| Hersteller | z.B. Pitney Bowes, Neopost, Francotyp |
| Modell | Genaue Modellbezeichnung |
| Baujahr | Wann hergestellt |
| Zustand | Sehr gut / Gut / Gebraucht |
| Technische Daten | Geschwindigkeit, Formate, etc. |
| Weitere Fotos | Galerie |

---

## Produktkategorien (Vorschlag)

*Basierend auf aufpost.de und gängigen Maschinen:*

1. **Kuvertiermaschinen** (Falzen + Kuvertieren)
   - z.B. Pitney Bowes DI950, Neopost DS-75

2. **Frankiermaschinen** (Porto drucken)
   - z.B. Pitney Bowes SendPro, Francotyp PostBase

3. **Adressdrucker** (Umschläge bedrucken)
   - z.B. für Etiketten oder Direktdruck

4. **Falzmaschinen** (nur Falzen, kein Kuvertieren)

5. **Brieföffner** (automatisches Öffnen von Post)

6. **Zubehör & Verbrauchsmaterial**
   - Tintenpatronen, Siegelflüssigkeit, Umschläge

**⚠️ KLÄREN: Welche Kategorien will der Bekannte wirklich?**

---

## Beispiel-Maschinen (zum Start)

*Diese können wir vorab recherchieren und eintragen, der Bekannte passt dann Preise/Details an:*

| Maschine | Kategorie | Hersteller |
|----------|-----------|------------|
| Pitney Bowes DI950 | Kuvertiermaschine | Pitney Bowes |
| Neopost DS-75 | Kuvertiermaschine | Neopost |
| Neopost DS-200 | Kuvertiermaschine | Neopost |
| Frama Matrix F32 | Frankiermaschine | Frama |
| Francotyp PostBase Mini | Frankiermaschine | Francotyp |
| Pitney Bowes SendPro C | Frankiermaschine | Pitney Bowes |

**Vorteil dieser Strategie:**
- Website sieht von Anfang an "voll" aus
- Bekannter muss nur anpassen, nicht von Null anfangen
- Wir lernen welche Felder wirklich gebraucht werden

---

## Nicht-Ziele (MVP)

**Explizit NICHT im ersten Release:**

- ❌ **Kein Warenkorb / Online-Kauf** - Nur Anfragen, Verkauf persönlich/telefonisch
- ❌ **Keine Zahlungsabwicklung** - Zahlung auf Rechnung, nicht über Website
- ❌ **Keine Kundenkonten** - Kunden müssen sich nicht registrieren
- ❌ **Keine Bewertungen/Reviews** - Zu komplex für MVP
- ❌ **Kein Newsletter** - Später optional
- ❌ **Keine mobile App** - Responsive Website reicht
- ❌ **Keine eBay-Integration** - Manuell parallel pflegen oder eBay aufgeben

---

## Technische Umsetzung

### Idee: Beispieldaten vorausfüllen

```
1. Wir recherchieren typische Maschinen (Pitney Bowes, Neopost, etc.)
2. Wir füllen Kategorien + Beispiel-Maschinen ein
3. Der Bekannte loggt sich ein und passt an:
   - Preise setzen
   - Beschreibungen anpassen
   - Status ändern (Auf Lager / Auf Anfrage)
   - Eigene Fotos hochladen
   - Maschinen löschen die er nicht will
   - Neue hinzufügen
```

**Das ist gut umsetzbar weil:**
- Admin-Bereich ist sowieso geplant
- Bearbeiten ist einfacher als neu anlegen
- Website sieht von Tag 1 professionell aus
- Bekannter sieht sofort wie es aussehen wird

---

## Erfolgskriterien

### Für den Bekannten
- [ ] Kann selbstständig Maschinen hinzufügen/bearbeiten
- [ ] Bekommt Anfragen per E-Mail
- [ ] Website sieht professioneller aus als eBay
- [ ] Weniger Aufwand als eBay-Listings pflegen

### Für Kunden
- [ ] Finden schnell was sie suchen
- [ ] Können einfach anfragen
- [ ] Sehen alle verfügbaren + beschaffbaren Maschinen

### Technisch
- [ ] Mobile-optimiert
- [ ] Schnelle Ladezeiten
- [ ] DSGVO-konform
- [ ] Einfacher Admin-Bereich

---

## Offene Fragen (fürs Gespräch)

Siehe separate Datei: `docs/04-tasks/backlog/TASK-001-vision-ausarbeiten.md`

---

## Zusammenfassung

**In einem Satz:** Professionelle Website für den Verkauf von reparierten Postbearbeitungsmaschinen mit selbstverwaltetem Admin-Bereich.

**Kernfunktionen:**
1. Produktkatalog mit "Auf Lager" + "Auf Anfrage"
2. Anfrage-Formular pro Produkt
3. Ankauf-Formular für Verkäufer
4. Admin-Bereich zur Selbstverwaltung

**USP (Unique Selling Point):**
- Generalüberholte Maschinen = günstiger als neu
- Professionelle Präsentation = Vertrauen
- Größeres Sortiment = auch Maschinen die beschaffbar sind
