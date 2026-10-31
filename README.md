# KI-Tipps

Wiederverwendbare Arbeitsanweisungen für den praktischen Einsatz von KI. Die Sammlung von Dominik Steiner verbindet klare Abläufe, kritische Quellenprüfung und konkrete Verbesserungsvorschläge.

## Inhalt

| Skill | Zweck | Einstieg |
| --- | --- | --- |
| RedTeam-Dokumentenprüfer | Dokumente kritisch auf Zweck, Qualität, Konsistenz, Belege und Umsetzbarkeit prüfen | [Arbeitsanweisung](skills/redteam-dokumentenpruefer/SKILL.md) |

Der RedTeam-Dokumentenprüfer unterstützt unter anderem Angebote, Berichte, Konzepte, Strategien, Lehrmaterialien und Präsentationen. Er bestimmt zuerst Dokumenttyp, Zielgruppe und Zweck und richtet die Prüfung danach aus.

## So nutzt du die Sammlung

1. Öffne die verlinkte `SKILL.md` und lies die Arbeitsanweisung.
2. Stelle sie in deiner KI-Umgebung zusammen mit dem zu prüfenden Dokument bereit. Ob Skills direkt installiert oder aufgerufen werden können, hängt von der jeweiligen Umgebung ab.
3. Nenne Zweck, Zielgruppe, Version und die gewünschte Entscheidung. Stelle relevante Beilagen bereit.
4. Prüfe die Ergebnisse und setze die priorisierten Korrekturen um.

Bei eingerichtetem Skill kann ein Auftrag so aussehen:

> Nutze $redteam-dokumentenpruefer für das beigefügte Konzept. Zielgruppe ist die Geschäftsleitung. Prüfe insbesondere Entscheidungsgrundlage, Umsetzbarkeit und offene Annahmen. Gib die Prüfung im Chat aus.

Für eine überarbeitete Fassung:

> Führe einen Delta-Review durch. Vergleiche die neue Fassung mit den bisherigen Findings und kennzeichne, was behoben, teilweise behoben oder noch offen ist.

## Ergebnis des RedTeam-Reviews

- Freigabe-Dashboard mit einer qualitativen Skala von 1 bis 10 und NO-GO, CONDITIONAL GO oder GO; bei unzureichender Grundlage ohne erfundenen Zahlenwert.
- Priorisierte Schlüsselfindings mit Fundstellen, Auswirkungen und Korrekturen.
- Prüfdetails sowie Quellen- und Behauptungsprüfung nach CRAP: Currency, Reliability, Authority und Purpose.
- Abschliessender Korrekturvorschlag mit überprüfbaren Freigabebedingungen.

Die Standardausgabe erfolgt ausschliesslich im Chat. Eine Berichtsdatei oder ein Redlining wird nur auf ausdrücklichen Auftrag erstellt. Eine positive Bewertung ist keine fachliche oder rechtliche Garantie.

## Aufbau des Skills

| Datei oder Ordner | Inhalt |
| --- | --- |
| [SKILL.md](skills/redteam-dokumentenpruefer/SKILL.md) | Ablauf, Regeln und Ausgabeformat |
| [agents/openai.yaml](skills/redteam-dokumentenpruefer/agents/openai.yaml) | Metadaten für unterstützende KI-Umgebungen |
| [references/review-framework.md](skills/redteam-dokumentenpruefer/references/review-framework.md) | Prüfrahmen |
| [references/document-profiles.md](skills/redteam-dokumentenpruefer/references/document-profiles.md) | Dokumentbezogene Prüfmodule |
| [references/crap-test.md](skills/redteam-dokumentenpruefer/references/crap-test.md) | Quellen- und Faktenprüfung |
| [references/output-dashboard.md](skills/redteam-dokumentenpruefer/references/output-dashboard.md) | Freigabeskala und Ergebnisdarstellung |
| [references/original-reviewer-prompt.md](skills/redteam-dokumentenpruefer/references/original-reviewer-prompt.md) | Ergänzende Angebotsreferenz; aktuelle Ausgaberegeln stehen in SKILL.md |
| [assets/icon.svg](skills/redteam-dokumentenpruefer/assets/icon.svg) | Symbol |

## Weiterführende Sammlung

Die Skills für Chen-Modelle und relationale ER-Diagramme liegen im Repository **[BigData-AI](https://github.com/Dsteiner73/BigData-AI)** unter **Datenmodellierung (ERM)**. Sie wurden aus diesem Repository dorthin verschoben.

## Qualität und Weiterentwicklung

Fehler und Verbesserungsvorschläge können als Issue oder Pull Request eingereicht werden. Beschreibe den betroffenen Skill, das erwartete Verhalten und ein anonymisiertes Beispiel. Belege fachliche Änderungen möglichst mit passenden Primärquellen.

Verwende für öffentliche Beispiele fiktive oder anonymisierte Daten. Vertrauliche Dokumente gehören nicht in öffentliche Issues oder Pull Requests.

## Beiträge auf dominikai.social

Auf **[dominikai.social](https://dominikai.social)** publiziere ich persönliche Beiträge und Reflexionen zu **künstlicher Intelligenz und Leadership**. Die Website ergänzt die Arbeitsanweisungen auf GitHub um meine Gedanken und Einordnungen zu diesen Themen.

## Über die Sammlung

Persönliche Arbeitsmaterialien von Dominik Steiner. Die Inhalte stellen keine offiziellen Positionen von Arbeitgebern, Behörden oder Organisationen dar.

Stand der Übersicht: 31. Oktober 2026.
