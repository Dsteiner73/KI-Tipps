---
name: erstelle-chen-erm
description: Erstelle, erkläre und prüfe Entity-Relationship-Modelle in Chen-Notation aus Textaufgaben, Geschäftsregeln oder fotografierten Klassenarbeiten. Verwende für Chen-ERM, Musterlösungen, Unterrichtsbeispiele und Feedback zu Entitäten, Attributen, Identifikatoren, Beziehungen und Min-Max-Beteiligungen. Nicht für ausschliesslich relationale Tabellen, SQL oder Crow's-Foot-Diagramme.
---

# ER-Modelle nach Chen

Schreibe präzise in Schweizer Rechtschreibung. Trenne Vorgaben, Annahmen und offene Fragen. Nutze bei Unterrichtsfällen [references/prueffaelle.md](references/prueffaelle.md).

## Fachliches Modell ableiten

1. Lies die vollständige Aufgabenstellung. Übernimm bei Fotos nur lesbare Inhalte und kennzeichne unlesbare Stellen. Bewerte ausschliesslich sichtbare Ergebnisse.
2. Bestimme Entitätstypen im Singular. Trenne Typen (Produkt) von Instanzen (Produkt 1). Ergänze keine Entitäten allein wegen erwähnter Beispiele.
3. Ordne Attribute fachlich zu. Wähle stabile Identifikatoren. Kennzeichne ergänzte Attribute als Vorschläge. Prüfe den Gültigkeitsbereich von Nummern: Eine Positionsnummer innerhalb einer Bestellung ist allein kein globaler Schlüssel.
4. Benenne Beziehungen mit passenden Verben. Formuliere jede Beziehung in beiden Leserichtungen als Geschäftsregel.
5. Bestimme für jede beteiligte Entität separat Minimum und Maximum ihrer Beziehungsteilnahmen. Leite Werte aus dem Text ab. Frage bei entscheidenden Widersprüchen gezielt nach; arbeite bei kleinen Lücken mit ausdrücklich genannten Annahmen weiter. Setze unbekannte Minima nicht stillschweigend auf 0 oder 1.
6. Prüfe mit Gegenbeispielen: mehrere Aufträge pro Fahrzeug, derselbe Artikel in verschiedenen Bestellungen, Person in mehreren Kursen, historische Ausleihen eines Exemplars.

## Zeichenregeln

- Zeichne Entitätstypen als Rechtecke, Beziehungen als Rauten und Attribute als Ellipsen. Verbinde Attribute mit ihrer Entität oder der Beziehung, deren Eigenschaft sie beschreiben.
- Unterstreiche Schlüsselattribute. Unterstreiche bei zusammengesetzten Schlüsseln alle Bestandteile und erläutere die Kombination. Unterstreiche nicht pauschal jede Nummer.
- Verwende standardmässig Chen mit Min-Max-Erweiterung: `(0,n)`, `(1,n)`, `(0,1)`, `(1,1)`. Erkläre die Konvention in einer kurzen Legende.
- Platziere `(min,max)` direkt an der zugehörigen Entität auf der Verbindung zur Raute. Der Wert bezeichnet die Zahl der Beziehungsteilnahmen GENAU DIESER Entität. Beispiel: Fahrzeug `(0,n)` — betrifft — `(1,1)` Serviceauftrag bedeutet: Ein Fahrzeug kann null bis viele Aufträge haben; jeder Auftrag betrifft genau ein Fahrzeug.
- Vermische diese Angaben nicht mit den anders gelesenen 1:n-Markierungen klassischer Chen-Kardinalitäten. Falls ausdrücklich 1:n verlangt wird, benenne diese Variante und ergänze Mindestbeteiligungen separat. Verwende für klassische Chen-Darstellung totale Teilnahme gegebenenfalls als Doppellinie, konsistent mit der Legende.
- Verwende keine Pfeilspitzen, Crow's-Foot-Enden, Tabellenkästen mit Attributlisten oder FK-Linien als Chen-Ersatz.
- Lasse konzeptionelle m:n-Beziehungen zu. Löse sie nur bei fachlichem Bedarf durch eine eigene Entität auf, etwa Buchung mit Datum, Status und eigener Identität. Vermeide eine redundante direkte m:n-Beziehung, wenn Buchung dieselbe Zuordnung vollständig beschreibt.
- Verwende bei Bedarf doppelte Rechtecke für schwache Entitäten, doppelte Rauten für identifizierende Beziehungen und gestrichelt unterstrichene Teilschlüssel. Kennzeichne mehrwertige Attribute mit Doppelellipse, abgeleitete mit gestrichelter Ellipse und zusammengesetzte mit untergeordneten Attributellipsen. Erläutere die Identifikation schwacher Entitäten über Eigentümer und Teilschlüssel, statt technische Fremdschlüssel in das konzeptionelle Modell zu kopieren.

## Exakte Grafik erstellen

Erzeuge präzise Diagramme deterministisch als SVG, etwa mit Graphviz oder expliziten Vektorformen. Verwende keine generative Bild-KI für verbindliche Fachdiagramme. Mermaid-ER-Diagramme verwenden keine Chen-Notation; liefere sie nicht als Chen-Ersatz.

Halte Beschriftungen als Text und Linien sowie Formen als Vektoren. Verwende weissen Hintergrund, dunkle Konturen und höchstens dezente Farben für Symboltypen. Platziere Attribute aussen. Verhindere Kreuzungen, verdeckte Texte und abgeschnittene Elemente. Zeichne Linien ohne Pfeilspitzen. Ergänze Titel und kurze Legende.

Liefere standardmässig eine sichtbare PNG-Vorschau und die editierbare SVG-Datei; ergänze PDF bei Druckbedarf oder ausdrücklichem Wunsch. Folge den verfügbaren Speicherregeln. Rendere und prüfe visuell jedes Symbol, jede Beschriftung, Schlüsselunterstreichung und Min-Max-Endzuordnung. Ist Rendering nicht möglich, sage dies knapp und behaupte keine Sichtprüfung.

## Abgabe und Prüfung

Liefere Diagramm und editierbare Datei, danach eine kompakte Tabelle mit der Geschäftsregel in beiden Leserichtungen, einschliesslich Minimum und Maximum. Nenne notwendige Annahmen und zusätzliche Regeln, etwa zeitliche Überschneidungsverbote.

Prüfe vor Abgabe: Aufgabenabdeckung, korrekte Symbole, Schlüssel, beide Richtungen, belegte Mindestbeteiligungen, keine unnötigen Beziehungen, richtig zugeordnete Beziehungsattribute und lesbare Grafik.

Bei Klassenarbeiten: Nenne einen konkret sichtbaren gelungenen Aspekt, dann die wichtigste Korrektur mit Begründung und eine Reflexionsfrage. Trenne fachliche Fehler von Notationsfehlern. Vergib ohne Auftrag und Bewertungsraster keine Note. Leite aus Gruppenarbeiten keinen gesicherten individuellen Lernerfolg ab.
