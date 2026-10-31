# Neutrale Integritätsmuster

## Beziehungstabelle
Für ObjektA und ObjektB kann Zuordnung(a_id, b_id, eigenschaft) den gemeinsamen Schlüssel (a_id,b_id) tragen. Beide FK-Spalten sind dann durch den PK verpflichtend. Ein Surrogatschlüssel ersetzt bei fachlich eindeutigen Paaren nicht UNIQUE(a_id,b_id). Bei historisch wiederholbaren Zuordnungen muss die fachliche Identifikation erweitert werden.

## Optionale 1:1-Erweiterung
Erweiterung.objekt_id als PK und FK erlaubt höchstens eine Erweiterung je Objekt. Jedes vorhandene Erweiterungsobjekt gehört genau einem Objekt. Die Existenz eines Erweiterungsdatensatzes für jedes Objekt wird dadurch nicht garantiert.

## Eigentum und Auswahl
Annahme: Ressource(resource_id PK, owner_id FK) gehört einem Eigentümer. Auswahl(owner_id PK/FK, resource_id NOT NULL/FK UNIQUE) wählt pro Eigentümer höchstens eine Ressource; jede Ressource wird höchstens einmal ausgewählt. Die beiden FKs allein garantieren NICHT, dass der Eigentümer der Auswahl auch Eigentümer der Ressource ist.

Wenn diese Übereinstimmung fachlich gefordert ist, kann ein deklaratives Muster sein:
- UNIQUE(owner_id, resource_id) auf Ressource als referenzierter Zielschlüssel.
- Zusammengesetzter FK Auswahl(owner_id, resource_id) → Ressource(owner_id, resource_id).
- NOT NULL für alle erforderlichen Teilspalten.
Bewahre den Eigentümer-FK der Auswahl, falls fachlich nötig. Prüfe die Ziel-DBMS-Syntax. Verändere nicht unbemerkt die Geschäftsregel, ob dieselbe Ressource mehrfach auswählbar sein darf.

## Rekursive Zuordnung
Verbindung(source_id, target_id), beide FKs auf Objekt, PK(source_id,target_id): verhindert exakte doppelte gerichtete Paare. Verhindert weder (x,x) noch das zusätzliche Paar (y,x).
- Gerichtete Beziehung: Gegenrichtung kann zulässig und fachlich verschieden sein.
- Ungerichtete Beziehung: Falls jedes Paar genau einmal gelten soll, kanonische Ordnung verwenden, z.B. source_id < target_id bei geordneten IDs. Dies verhindert gleichzeitig Selbstbezüge. Alternativ Datenbank-spezifische normalisierte Paar-Eindeutigkeit prüfen.
- CHECK(source_id <> target_id) verhindert nur Selbstbezug, keine umgekehrten Doppelungen.
Bestätigung, Status oder zeitliche Gültigkeit nur bei belegtem Bedarf hinzufügen.

## Nullbarkeit und Mindestbeteiligung
Ein einfacher NULL-fähiger FK erlaubt fehlende Zuordnung; NOT NULL plus FK verlangt einen Elternsatz für jedes Kind. Dies erzwingt kein Kind für jeden Elternsatz. Bei zusammengesetzten FKs partielle NULL-Belegung und MATCH-Semantik prüfen; nicht aus einer einzelnen NOT-NULL-Spalte vollständige Pflichtzuordnung ableiten.

## Grenzen von Constraints
UNIQUE mit NULL-Werten ist DBMS-abhängig. Ein CHECK ist kein universeller Mechanismus für Regeln über andere Zeilen oder Tabellen. Explizite DBMS-Constraints, Transaktionslogik oder Trigger erst nach Zielsystemklärung vorschlagen. Lösch-/Änderungsregeln aus Lebenszyklus und Anforderungen ableiten.

## Technische Referenz
PostgreSQL 18, Kapitel 5.5 Constraints: https://www.postgresql.org/docs/18/ddl-constraints.html
Geprüft am 31.10.2026 als Primärquelle für PK, UNIQUE, FK, NOT NULL, CHECK und zusammengesetzte Schlüssel. Nicht ohne Prüfung auf andere DBMS übertragen; die Quelle belegt keine fachlichen Geschäftsregeln.
