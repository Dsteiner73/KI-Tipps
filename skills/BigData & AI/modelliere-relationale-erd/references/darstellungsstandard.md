# Darstellungsstandard für erzeugte ERD

## Visueller Standard
- Weisser Hintergrund; helle Tabellenflächen; feine, einheitliche blauviolette Konturen und Verbindungslinien.
- Rechteckige Tabellenkästen, leicht gerundete Ecken optional. Tabellenname zentriert in einer separaten Kopfzeile, horizontale Trennlinie darunter.
- Attribute linksbündig in eigenen Zeilen; Spaltenbreite anhand längster Beschriftung berechnen. Tabellen dürfen unterschiedlich hoch sein.
- Schlüsselattribute fett und mit eindeutigen Textmarkierungen versehen: «PK», «FK» oder «PK, FK». Symbole dürfen ergänzen, aber keine unlesbaren Unicode-Zeichen verwenden.
- Weitere Constraints unmittelbar am Attribut: «NOT NULL», «UNIQUE». UK und UNIQUE als dasselbe Konzept erklären, nicht zwei verschiedene Regeln suggerieren.
- Zusammengesetzte PKs an allen beteiligten Attributen markieren und im Modell gemeinsam definieren. Zusammengesetzte FKs und mehrspaltige UNIQUE-Regeln mit Gruppennamen wie FK1(a,b) bzw. UQ1(a,b) eindeutig erläutern.
- Datentypen nur bei belegten Angaben oder als kenntlich gemachte Entwurfswahl anzeigen. Präfixe wie tbl nur bei Nutzerwunsch oder bestehender Konvention übernehmen.
- Verwende lesbare serifenlose Schrift, z.B. 14–16 px für Attribute und 16–18 px für Tabellenköpfe; passe Leinwand und Exportauflösung an die Modellgrösse an.

## Beziehungen
- Zeichne orthogonale Linien ohne gewöhnliche Richtungspfeile. Vermeide Linien durch Kästen und Texte.
- Setze die Crow's-Foot-Symbole ausreichend nahe am zugehörigen Tabellenende, jedoch ausserhalb des Kastens. Halte Platz für die Symbole frei.
- Genau eins: zwei kurze parallele Querstriche; null oder eins: Kreis und Querstrich; null bis viele: Kreis und Krähenfuss; eins bis viele: Querstrich und Krähenfuss.
- Zeichne Symbole als Vektorlinien und Kreise, nicht als frei schwebende Satzzeichen. Richte sie nach der Richtung des ersten/letzten Liniensegments aus.
- Beispiel: Kind.parent_id NOT NULL FK auf Eltern.id ohne UNIQUE im Kind: am Elternende genau eins, am Kindende null bis viele, sofern kein verpflichtendes Kind je Elternsatz vorgegeben ist.
- Beispiel: Erweiterung.parent_id PK/FK auf Eltern.id: am Elternende genau eins, am Erweiterungsende null oder eins, sofern Existenz der Erweiterung nicht zusätzlich vorgeschrieben ist.
- Beschrifte Rollen oder Beziehungen bei Bedarf in freien Bereichen. Führe Selbstreferenzen aussen um die Tabelle; trenne zwei Rollen auf derselben Zieltabelle geometrisch und mit Namen.
- Kennzeichne identifizierende vs. nicht identifizierende Beziehungen nur bei expliziter, konsistenter Legende. Im Zweifel einheitliche Linien statt unbegründeter Stricharten verwenden.

## Abgabe
Liefere die Grafik selbst, nicht nur einen Plan oder Code. Standard: PNG-Vorschau, editierbares SVG und strukturierte Modellquelle. Ergänze PDF nur für Druck oder auf Wunsch. Halte die Grafik fachgebietsneutral; nutze konkrete fachliche Begriffe aus dem jeweiligen Auftrag.

## Prüfkriterium
Jede FK-Beziehung der Modellquelle muss genau im Diagramm nachvollziehbar sein; doppelte Darstellungen desselben FK vermeiden. Kardinalitäten und Constraints müssen zusammenpassen. Eine optisch passende Grafik darf keine fachlich ungesicherte Regel als gesichert ausgeben.
