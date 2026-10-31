# Fachliche Prüffälle

Übernimm diese Beispielregeln nur bei passender Aufgabenstellung. Min-Max-Werte beziehen sich auf die Teilnahme der unmittelbar genannten Entität.

## Werkstatt
Vorgabe: Jeder Serviceauftrag betrifft genau ein Fahrzeug und eine Fachperson. Fahrzeuge und Fachpersonen dürfen ohne Auftrag bestehen und mehrere Aufträge haben.
- Fahrzeug `(0,n)` — betrifft — `(1,1)` Serviceauftrag.
- Fachperson `(0,n)` — betreut — `(1,1)` Serviceauftrag.
- Beispielattribute: FahrzeugNr (Schlüssel), Kontrollschild; AuftragsNr (Schlüssel), Datum; PersonalNr (Schlüssel), Name.
- Keine zusätzliche direkte Fahrzeug–Fachperson-Beziehung erfinden.

## Bestellung
Vorgabe: Kunde darf ohne Bestellung bestehen. Jede Bestellung gehört einem Kunden und hat mindestens eine Position. Jede Position gehört genau einer Bestellung und verweist auf einen Artikel. Artikel dürfen ohne Positionen bestehen.
- Kunde `(0,n)` — tätigt — `(1,1)` Bestellung.
- Bestellung `(1,n)` — enthält — `(1,1)` Bestellposition.
- Artikel `(0,n)` — erscheint in — `(1,1)` Bestellposition.
- Menge gehört zur Position. Artikel–Position ist insgesamt 1:n, nicht 1:1.
- Bei globaler PositionsID ist eine starke Entität möglich. Bei Positionsnummer nur innerhalb der Bestellung: schwache Entität mit Positionsnummer als Teilschlüssel, identifizierender Beziehung und Identifikation durch Bestellung plus Positionsnummer.
- Mehrfaches Auftreten desselben Artikels innerhalb einer Bestellung ist ohne weitere Regel weder verboten noch vorgeschrieben.

## Kursbuchung
Vorgabe: Jede Buchung verbindet genau einen Teilnehmer und einen Kurs. Beide dürfen ohne Buchung existieren.
- Teilnehmer `(0,n)` — tätigt — `(1,1)` Buchung.
- Kurs `(0,n)` — hat — `(1,1)` Buchung.
- Attribute der Buchung: BuchungsNr (Schlüssel), Datum, Status.
- Keine redundante direkte Teilnehmer–Kurs-Beziehung ergänzen. Eindeutigkeit des Paars nicht ohne Vorgabe behaupten.

## Ausleihe
Vorgabe: Jede Ausleihe verbindet ein Mitglied und ein Exemplar. Beide dürfen ohne Ausleihen bestehen. Historische Ausleihen bleiben erhalten.
- Mitglied `(0,n)` — tätigt — `(1,1)` Ausleihe.
- Exemplar `(0,n)` — ist Gegenstand von — `(1,1)` Ausleihe.
- Trenne Titel und physisches Exemplar. Historisch sind mehrere Ausleihen desselben Exemplars möglich.
- Zeitlich überlappende Ausleihen zu verbieten ist eine zusätzliche Regel, kein Grund für 1:1.

## Häufige Fehlannahmen
- Kunde und Lieferant können überlappende Rollen eines Geschäftspartners sein. Disjunkte Rollen brauchen eine Vorgabe.
- Kundenklasse kann Attribut oder Entitätstyp sein. Regeln klären, bevor Beziehungen gesetzt werden.
- Untersuche Retouren an bestellten Positionen, wenn ursprüngliche Bestellung und retournierte Menge relevant sind. Ergänze erst nach Klärung der Regeln.
- Ein fachliches Minimum von einer Position pro Bestellung lässt sich nicht allein mit einem einfachen Fremdschlüssel erzwingen. Trenne konzeptionelles Modell und technische Umsetzung.
