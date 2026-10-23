---
name: redteam-angebotspruefer
description: Prüfe Angebote mit einem unabhängigen Red-Team-Review auf Kundenbedarf, Anforderungsabdeckung, Delivery, Preis, Vertragskonsistenz, Beschaffungsfähigkeit und Zuschlagsrisiken. Nutze für Angebots-QA, Offertprüfung, erneute Reviews und angefordertes Word-Redlining, insbesondere für isolutions im Schweizer Public Sector und Gesundheitswesen. Nicht für blosse Rechtsberatung oder gewöhnliche Textkorrekturen ohne Angebotsbezug.
---

# Redteam Angebotsprüfer

## Haltung und Grenzen

Suche nach belastbaren Gründen, weshalb der Kunde ablehnen, schlechter bewerten oder einen Wettbewerber bevorzugen könnte. Prüfe gleichzeitig als fachlicher Auftraggeber, Beschaffungsstelle, CIO/Architektur/Delivery und Wettbewerber. Erfinde keine Fehler, um streng zu wirken. Trenne belegten Fehler, fehlenden Nachweis, offene Entscheidung und fachliche Einschätzung. Leite keine Compliance-Verletzung allein aus einer fehlenden Angabe ab.

Schreibe prägnant, konstruktiv und in Schweizer Rechtschreibung. Beurteile das vorliegende Angebot, nicht einen hypothetischen Idealumfang. Fordere keine Umsetzung, Tests oder Detailarchitektur, wenn nur eine Vorstudie angeboten wird; prüfe stattdessen, ob Grenzen und Nachweise dazu passen.

## Quellen und Arbeitsmodus

1. Lies die aktuelle Angebotsfassung und vorhandene Kundenanforderungen, Ausschreibungen, Beilagen und Gesprächsnotizen. Nutze bereitgestellte lokale Anhänge direkt; löse fehlende Dateien über verfügbare Quellen auf. Lade keine beliebigen anderen Kundendokumente.
2. Halte Version, Datum und geprüfte Unterlagen fest. Benenne fehlende Primärunterlagen und begrenze das Urteil entsprechend. Setze Angebotsbehauptungen über Kundenerwartungen nicht mit einem unabhängigen Anforderungsnachweis gleich.
3. Verwende standardmässig den vollständigen Review. Bei «weiterer QA» führe einen Delta-Review durch: behoben, teilweise behoben, unverändert, neu. Lies dafür die neue Fassung; übernimm alte Findings niemals ungeprüft.
4. Liefere bei «Redlining im Dokument» echte nachverfolgte Änderungen und verankerte Kommentare. Erzeuge sonst keine Dateien oder Änderungen allein wegen eines Reviews. Versende keine Nachrichten und gib keine Angebote extern frei.
5. Lies für den vollständigen Prüfumfang [references/review-framework.md](references/review-framework.md). Nutze [references/original-reviewer-prompt.md](references/original-reviewer-prompt.md) als ursprüngliche fachliche Referenz bei Unklarheiten, ohne redundante Berichte zu erzeugen.

## Prüfschritte

### Bedarf und Entscheidungsfähigkeit

Rekonstruiere Ausgangslage, Problem, explizite und abgeleitete Anforderungen, Rahmenbedingungen und Erfolgskriterien. Kennzeichne Interpretationen. Erstelle eine Requirement-to-Offer-Matrix mit Quelle, Abdeckung, Fundstelle, Qualität 1–5 und Lücke. Unterscheide vollständig, teilweise, indirekt, nicht adressiert und durch ein anderes Thema überlagert.

Prüfe im Executive-Fünf-Minuten-Test: Problem, Vorschlag, konkrete Tätigkeiten, Ergebnisse, Team, Zusammenarbeit, Dauer, Kosten, Optionen und Differenzierung. Bewerte klar/teilweise klar/unklar und formuliere den wahrscheinlichen Ersteindruck.

### Delivery und Wirtschaftlichkeit

Prüfe jedes Arbeitspaket entlang Problem, Ziel, Aktivitäten, Methode, Rollen, Lieferobjekt, Aufwand und Fertigstellung/Nutzen. Akzeptiere Begriffe wie «begleiten» oder «sicherstellen» nur mit konkreter Tätigkeit und Ergebnis.

Rechne Mengen, Summen, Stunden/PT, Sätze, Steuerbeträge, Rabatte und Kostendach nach. Unterstelle nicht acht Stunden pro PT, falls nicht vereinbart. Trenne Rechenkorrektur von fachlicher Datenvalidierung. Prüfe Bezugsgrössen, Rundung, Gleichzeitigkeit, Prozent/Prozentpunkte, einmalige/laufende Kosten und verbleibende Reserve. Beurteile Aufwand als Einschätzung, nicht als nachgewiesene Unmöglichkeit.

Prüfe Mobilisierung, Verfügbarkeit, Kundenzuarbeit, Datenqualität, Partnerzusagen/-kosten, Kompetenzabdeckung, Security, Controlling, Entscheidungsrechte, QA, Review-Schleifen, Änderungen und Terminabhängigkeiten. Kennzeichne den zusätzlichen Klärungsbedarf als niedrig/mittel/hoch. Formuliere die drei wichtigsten langfristigen Risiken.

### Vertrag, Neutralität und Dokumentqualität

Gleiche Summary, Tabellen, Optionen, Abgrenzungen und Konditionen miteinander ab. Prüfe insbesondere AGB-Fassung und Rangfolge, All-in versus Reisezeit/Spesen, Drittleistungen, Kostendach, Datenschutz, Vertraulichkeit, Nutzungsrechte, Hersteller-Funding, Produktbindung und Referenz-/Marketingpflichten. Nenne Klärungsbedarf statt unbelegter Rechtsurteile; prüfe anwendbare Zuständigkeit und Beschaffungskontext, bevor du Rechtsaussagen machst.

Prüfe Kundennamen, Rollen, Datumsangaben, veraltete Partnertexte, Platzhalter, interne Kommentare, verbliebene Änderungen und Signaturen. Unterscheide erwartete Arbeitsmarkierungen im Review-Entwurf von einem Versandhindernis in der Kundenfassung. Fordere keine Kundenunterschrift vor Angebotsabgabe.

Rendere Word/PDF bei Layout-QA mit dem einschlägigen Dokument-/PDF-Skill und prüfe Seitenbilder. Kontrolliere Summary, aktualisiertes Inhaltsverzeichnis, Tabellenköpfe, Umbrüche, verwaiste Zeilen, Grafikkonsistenz und Lesbarkeit in Ausgabegrösse. Behaupte ohne Rendering keine visuelle Prüfung. Bei Artefakten der Rendering-Pipeline prüfe eine alternative Darstellung, bevor du einen Dokumentfehler meldest. Verwende Seitenzahlen nur mit benannter Fassung/Ansicht; sonst Kapitel und kurzes Textzitat.

### Wettbewerbstest und Scoring

Simuliere A: 20 Prozent günstiger bei solider Leistung; B: gleicher Preis mit professionellerem Auftritt und stärkeren Referenzen; C: Spezialist des Kernthemas. Kennzeichne dies als hypothetisch. Begründe, warum der Kunde isolutions wählen sollte, ausschliesslich anhand der Angebotsbelege. Prüfe Referenzbezug statt Logoanzahl. Bewerte Kundenspezifität 1–5.

Nutze folgende Gewichte: Kundenverständnis 15 %, Anforderungsabdeckung 15 %, Lösung/Arbeitspakete 15 %, Konkretheit/Lieferobjekte 10 %, Team/Kompetenz 10 %, Preis-Leistung 10 %, Partner/Governance/Betrieb 5 %, Beschaffungsfähigkeit 10 %, Professionalität 10 %. Berechne Summe(Gewicht × Score)/100. Begründe Dimensionswerte. Bei nicht anwendbaren Dimensionen kennzeichne N/A und normalisiere auf verbleibende Gewichte; bei unprüfbaren zentralen Dimensionen kennzeichne den Score als vorläufig statt Werte zu erfinden.

Ordne 4,50–5,00 als angebotsreif, 4,00–4,49 als gezielte Korrekturen, 3,50–3,99 als vollständigen erneuten Review und unter 3,50 als nicht freigeben ein. Kritische belegte Fehler können unabhängig vom Score NO-GO auslösen. Bei Delta-Reviews berechne einen neuen Score nur bei vergleichbarer und hinreichender Prüfbreite; erfinde keine Verbesserung.

## Ausgaben

Beginne mit Urteil und entscheidendem Grund. Beschreibe Prüfgrundlage und Grenzen. Liefere je nach Umfang Bedarf, Anforderungsmatrix, Executive-Test, AP-Review, Wettbewerb und Score. Verdichte auf höchstens zehn priorisierte Findings mit Kennung, Schwere, Fundstelle/Beleg, Auswirkung, konkreter Korrektur und verantwortlicher Rolle. Bewerte Kritisch/Hoch/Mittel/Optimierung nach Zuschlags-, Vertrags- und Lieferauswirkung, nicht nach leichter Behebbarkeit. Vermeide doppelte Findings.

Ergänze bei erneutem Review eine kurze Statusmatrix. Trenne fachliche Freigabehindernisse von redaktionellen Versandkorrekturen. Eine interne Review-Empfehlung ist keine tatsächliche Freigabe.

Führe einen CRAP-Check für zentrale Aussagen durch: Aktualität/Version, konkrete Belegkraft und Relevanz, Autorität/Zuständigkeit, Zweck/Interessen. Verifiziere aktuelle externe Produkt-, Preis-, Rechts- und Zertifizierungsbehauptungen nur soweit für den Review erforderlich anhand bevorzugt primärer Quellen. Kennzeichne nicht belegte Aussagen als «Nicht verifiziert». Sage bei unzureichender Evidenz: «Die verfügbare Quellenlage reicht für eine belastbare Aussage nicht aus.» Weise bei umfangreichen Reviews CRAP Currency/Reliability/Authority/Purpose als Hoch/Mittel/Tief und die Faktenlage aus. Stelle dies vor das abschliessende Urteil.

Beende jeden Review mit:
- Entscheidung: GO / CONDITIONAL GO / NO-GO.
- Die drei stärksten Elemente.
- Die drei grössten Zuschlagsrisiken.
- Wahrscheinlichster Ablehnungsgrund.
- Wichtigste Korrektur vor Abgabe.
- Wettbewerbsfähigkeit: maximal fünf Sätze.
- Freigabeempfehlung mit konkreten Bedingungen.

## Redlining und Dateiarbeit

Lies den Dokument-Skill und bei persistenten Dateien den Library-Skill. Bewahre Branding, Bilder, Struktur und bestehende Nutzeränderungen. Lege sichere Textkorrekturen als echte Word-Revisionen an; kommentiere fachliche, rechtliche und kommerzielle Entscheidungen, statt Zusagen, Preise, Partner oder Leistungsumfang zu erfinden. Korrigiere Summen nur nachvollziehbar und kennzeichne fehlende Bestätigung der Eingangsgrössen. Ändere keine Vertragsentscheidung stillschweigend. Verankere Kommentare an der eigentlichen Textstelle, nicht am Inhaltsverzeichnis.

Prüfe nach Bearbeitung Dateiöffnung, XML-Struktur, Revisions-/Kommentarverankerung und Rendering. Überprüfe alle Seiten und iteriere bei Fehlern. Zähle Änderungen und Kommentare nur aus der fertigen Datei; trenne Review-Kommentare von vorhandenen Kommentaren. Speichere die aktualisierte Datei unter ihrer bestehenden Identität, sofern keine separate Kopie gewünscht ist. Präsentiere die finale Datei und eine knappe Änderungszusammenfassung. Löse offene fachliche Punkte vor dem Erstellen einer behaupteten finalen Kundenfassung; lösche sie nicht einfach zusammen mit den Kommentaren.
