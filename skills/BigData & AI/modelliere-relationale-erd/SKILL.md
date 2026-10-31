---
name: modelliere-relationale-erd
description: Erzeuge fachgebietsneutrale relationale ER-Diagramme im Tabellenstil mit Attributen, PK/FK/UNIQUE/NOT-NULL-Markierungen und Crow's-Foot-Verbindungen. Verwende bei Aufträgen wie ERD erstellen, Datenbankschema zeichnen oder Diagramm wie die Vorlage erzeugen, aus Anforderungen, SQL-DDL oder Bildern. Liefere eine gerenderte Grafik und editierbare Diagrammquelle. Analysiere und verbessere vorhandene Modelle bei ausdrücklichem Prüfauftrag. Verwende für reine konzeptionelle Chen-Modelle den Chen-Skill; führe keine Datenbankmigration oder produktive Änderung ohne eigenen Auftrag aus.
---

# Relationale ERD erzeugen

Arbeite unabhängig von Branche, Anwendung und Modellierungswerkzeug. Übernimm aus einem Beispieldiagramm die Modellierungsmuster, nicht dessen Domäne, Tabellenpräfixe oder unbewiesene Geschäftsregeln. Schreibe in Schweizer Rechtschreibung. Lies bei Integritätsfragen [references/integritaetsmuster.md](references/integritaetsmuster.md), bei der Qualitätskontrolle [references/prueffaelle.md](references/prueffaelle.md).

## Auftrag ausführen

Erstelle bei einem Erstellungsauftrag tatsächlich die Diagrammgrafik. Eine Analyse, textuelle Beschreibung, Constraint-Tabelle oder ein ungerenderter Codeblock allein erfüllt diesen Auftrag nicht. Leite das Modell ab, prüfe es intern und liefere zuerst das fertige ERD. Führe nur bei ausdrücklichem Analyseauftrag eine reine Analyse aus.

Lies vor dem Zeichnen [references/darstellungsstandard.md](references/darstellungsstandard.md). Nutze dessen Tabellenstil als Standard, wenn eine Darstellung wie die Vorlage gewünscht ist. Verwende die Vorlage als visuelle Referenz, nicht als feste fachliche Struktur.

## 1. Quelle und Modellierungsebene erfassen

Bestimme, ob ein konzeptionelles, logisches oder physisches Modell vorliegt. Tabellen mit PK/FK-Markierungen sind ein relationales Modell, kein Chen-Modell. Benenne die erkennbare Notation; behaupte ohne Beleg kein konkretes Werkzeug.

Lies bei Bildern Namen, Spalten, Schlüssel, Nullbarkeit, Eindeutigkeit und Beziehungsenden getrennt. Vergrössere unlesbare Ausschnitte, wenn nötig. Markiere fehlende Legende, undeutliche Linien und unbekannte Datentypen. Erfinde keine DDL aus Bildsymbolen. Eine nicht eingezeichnete Regel ist im Diagramm nicht nachgewiesen, aber nicht automatisch in der Datenbank abwesend.

Erstelle intern ein Inventar: Tabelle, Spalten, Primärschlüssel, weitere eindeutige Schlüssel, Fremdschlüssel mit Zielspalten, Nullbarkeit, Kardinalitäten, Beleg und Sicherheit. Trenne sichtbar belegte Eigenschaften, abgeleitete Folgen und fachliche Annahmen.

## 2. Anforderungen in Regeln übersetzen

Formuliere für jede Beziehung beide Leserichtungen mit Minimum und Maximum. Kläre Rollen bei mehreren Verbindungen zu derselben Tabelle. Frage nur bei modellentscheidenden Lücken; liefere sonst einen ausdrücklich als Vorschlag bezeichneten Entwurf. Trenne beobachtetes Ist-Modell von empfohlenem Soll-Modell.

Prüfe Entitätstypen, atomare Attribute, funktionale Abhängigkeiten und Wiederholungsgruppen. Behaupte eine Normalform nur mit den dafür nötigen Schlüsseln und Abhängigkeiten. Leite weder aus einer Spaltenliste noch einem Surrogatschlüssel automatisch 3NF ab. Behandle Import-/Staging-Tabellen gesondert; markiere ihre Rolle als Annahme, solange sie nicht belegt ist.

## 3. Schlüssel, Beziehungen und Integrität prüfen

- Prüfe jeden Primärschlüssel auf Identifikation, Stabilität und Gültigkeitsbereich. Ein zusammengesetzter Schlüssel macht die Kombination eindeutig, nicht jedes Feld einzeln.
- Prüfe FK-Spaltenzahl, Reihenfolge, Typverträglichkeit und eindeutigen Zielschlüssel. Datentypen bei fehlenden Angaben als offen behandeln.
- Leite Kind→Eltern-Maximum 1 aus dem Bezug auf einen eindeutigen Zielschlüssel ab. Leite die Mindestbeteiligung aus Nullbarkeit und der tatsächlichen FK-Semantik ab.
- Leite Eltern→Kind-Maximum 1 nur aus einem eindeutigen FK oder einer passenden funktionalen Abhängigkeit ab. Ohne diese Beschränkung sind mehrere Kinder möglich. Ein NOT-NULL-FK erzwingt kein Kind für jeden Elternsatz.
- Löse m:n im relationalen Modell mit Zuordnungstabellen auf. Prüfe Paar-Eindeutigkeit und Attribute der Zuordnung; ergänze keine redundante direkte Verbindung.
- Trenne besitzende und auswählende Rollen. Zwei unabhängige FKs garantieren nicht, dass eine ausgewählte Ressource dem auswählenden Eigentümer gehört. Prüfe bei entsprechender Geschäftsregel einen gemeinsamen zusammengesetzten FK.
- Prüfe rekursive Beziehungen auf Selbstbezug, Richtung, symmetrische Doppelungen und Status/Zeitraum nur gemäss Anforderungen. Gleiche Tabelle in zwei Rollen bedeutet nicht automatisch ungerichtete Beziehung.
- Prüfe Lookup-Tabellen, Beziehungseigenschaften, Wertebereiche und eindeutige Geschäftskennungen. Erfinde keine Prioritätsbereiche oder Löschkaskaden.
- Trenne deklarative Constraints von zusätzlichen Regeln: zeitliche Überschneidungen, Pflicht-Kinddatensätze, Kapazitäten, Summen und tabellenübergreifende Abhängigkeiten können weitere Mechanismen benötigen.

Nutze Gegenbeispiele mit minimalen Datensätzen: doppelte Zuordnung, falscher Eigentümer, fehlendes Elternobjekt, NULL im FK, Selbstbezug und umgekehrtes Paar. Benenne jeweils, ob der Fehler durch nachgewiesene Constraints verhindert wird oder offen bleibt.

## 4. Diagramm verbindlich erzeugen

Verwende standardmässig den Tabellenstil aus references/darstellungsstandard.md: rechteckige Tabellenkästen, separate Kopfzeile, Attributzeilen, Schlüsselmarkierungen und echte Crow's-Foot-Endsymbole. Zeichne keine Chen-Rauten und keine dekorative Illustration.

Erzeuge als Standard ein editierbares SVG und eine gerenderte PNG-Vorschau. Verwende deterministische Vektorformen, etwa direktes SVG oder ein geeignetes Diagrammwerkzeug. Liefere zusätzlich die strukturierte Modellquelle, zum Beispiel JSON oder bei Bedarf DBML. Verwende Mermaid nur auf Wunsch oder wenn dessen Stil den Auftrag erfüllt; bei «wie die Vorlage» ersetzt ein Mermaid-Codeblock nicht das exportierte ERD. Verwende keine generative Bild-KI für präzise Schemagrafiken.

Setze zuerst Tabellen und Abmessungen, danach die Beziehungen. Verbinde FKs mit den zugehörigen Zieltabellen, möglichst an passenden Zeilen. Führe Linien rechtwinklig durch freie Korridore. Verwende Kreis, Strich und Krähenfuss als Vektorsymbole; erkläre 0..1, 1, 0..n und 1..n in einer Legende. Werte am Beziehungsende bezeichnen die mögliche Zahl von Instanzen AN DIESEM Ende für eine Instanz am anderen Ende. Verwechsle dies nicht mit Chen-Min-Max-Teilnahmen an der eigenen Entität.

Ordne Kerntabellen zentral, Lookups am Rand und Zuordnungstabellen zwischen ihren Eltern an. Halte Rollen bei rekursiven und parallelen Verbindungen explizit auseinander. Zeige unbekannte Datentypen als unbekannt oder lasse sie aus. Kennzeichne vorgeschlagene Typen als Vorschläge. Zeichne keine unbewiesene Kardinalität als gesichert; nenne eine nötige Entwurfsannahme kurz ausserhalb der Grafik.

Rendere SVG zu PNG und prüfe visuell: vollständige Tabellen und Attribute, PK/FK/UK-Zuordnung, Endsymbole in korrekter Richtung, zusammengesetzte Schlüssel, eindeutige Linienverläufe, lesbare Beschriftungen und keine abgeschnittenen Elemente. Korrigiere Fehler vor der Abgabe. Verwende keine Platzhalter, wenn die Angaben die Erstellung erlauben. Ist Rendering technisch blockiert, liefere das SVG, benenne die Einschränkung und behaupte keine Sichtprüfung. Folge den verfügbaren Artefakt- und Speicherregeln.

## 5. Ergebnis liefern

Beginne bei Erstellungsaufträgen mit der sichtbaren PNG-Grafik und Links zur editierbaren SVG- und Modellquelle. Ergänze nur notwendige Annahmen, eine kurze Legende und nicht dargestellte Integritätsregeln. Beginne bei Analyseaufträgen mit Modelltyp und wichtigstem Befund. Liefere bei Analyse eine knappe Tabelle mit Befund, Beleg/Sicherheit, Auswirkung und Verbesserung. Liefere bei Erstellung Diagramm, editierbare Quelle und Geschäftsregeln in beiden Richtungen. Priorisiere tatsächliche Integritätsrisiken vor Namenskonventionen oder Layout.

Nenne offene Geschäftsregeln gezielt. Bezeichne fehlende Bildnachweise als nicht nachgewiesen statt als bestätigten Implementierungsfehler. Gib SQL nur bei Bedarf aus; benenne Zielsystem und Version, prüfe aktuelle offizielle Dokumentation und führe nichts produktiv aus. Behaupte bestandene Ausführungstests nur nach tatsächlicher Ausführung.

Prüfe Quellen auf Aktualität, konkrete Aussageabdeckung, Autorität und Zweck. Verwende Bildbefunde als Bildbefunde; externe Dokumentation belegt technische Semantik, nicht die fachliche Absicht des abgebildeten Modells.
