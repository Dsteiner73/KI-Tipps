# Prüffälle für neutrale ERD

## Dokumentauswahl
Dokument(document_id PK, case_id FK); Hauptdokument(case_id PK/FK, document_id FK UNIQUE NOT NULL). Prüfe mit Fall A, Fall B und einem Dokument von B, das A auswählt. Einfache FKs lassen dies zu. Eigentumskonsistenz ist nur dann ein Fehler, wenn die Regel gefordert ist, und muss durch einen passenden gemeinsamen Bezug oder weitere Mechanismen abgesichert werden.

## Projektrollen
Mitgliedschaft(person_id PK/FK, project_id PK/FK, role). Prüfe zwei Projekte derselben Person und zwei Personen desselben Projekts: beide zulässig. Dasselbe Paar mit anderer Rolle scheitert am Paar-PK. Falls mehrere Rollen je Paar fachlich erlaubt sein sollen, muss das Modell diese Anforderung ausdrücklich abbilden.

## Gerichtete und ungerichtete Verbindung
Abhängigkeit(a_id PK/FK, b_id PK/FK) und Partnerschaft(a_id PK/FK, b_id PK/FK) können dieselbe sichtbare Struktur haben, aber andere Semantik. Richtung nicht aus der Struktur allein erfinden. Selbstbezug und (a,b)/(b,a) getrennt prüfen.

## Historische Belegung
Ein Raum kann über die Zeit viele Belegungen haben. Keine 1:1-Beziehung aus der Regel ableiten, dass sich Belegungen nicht zeitlich überschneiden dürfen. Prüfe zeitliche Integrität gesondert.

## Unvollständiges Bild
Ein Bild zeigt FK-Markierungen ohne Datentypen und ohne FK-Zielspalten. Rekonstruiere nur erkennbare Beziehungen. Kennzeichne Typverträglichkeit, exakte FK-Definition und Löschverhalten als nicht verifiziert. Trenne Empfehlung von Befund.
