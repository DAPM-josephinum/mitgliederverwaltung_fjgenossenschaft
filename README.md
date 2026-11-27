# Mitgliederverwaltung FJ Genossenschaft

Schulprojekt DAPM · HBLFA Francisco Josephinum Wieselburg · 30.11.2026 bis 26.3.2027

Webanwendung in C# (.NET 10, ASP.NET Core mit Blazor, SQLite), mit der die FJ Genossenschaft
Ein- und Austritte, Geschäftsanteile, Auswertungen für die Revision, Mitgliederinfos mit Kalender
und Geschenkkorb-Bestellungen verwaltet.

> **Stand:** AP-00 Vorbereitung. Es gibt noch keinen Code. Das Grundgerüst entsteht in AP-01.

## Wo steht was?

| Was | Wo |
|---|---|
| Backlog (Arbeitspakete, Aufgaben, Fehler) | [Issues](https://github.com/DAPM-josephinum/mitgliederverwaltung_fjgenossenschaft/issues) |
| Was als Nächstes dran ist | [Issues nach Milestone](https://github.com/DAPM-josephinum/mitgliederverwaltung_fjgenossenschaft/milestones?direction=asc&sort=due_date) |
| Offene Fragen an Genossenschaft, Lehrkraft, Schul-IT | [Issues mit `typ:offener-punkt`](https://github.com/DAPM-josephinum/mitgliederverwaltung_fjgenossenschaft/issues?q=is%3Aopen+label%3Atyp%3Aoffener-punkt) |
| Anforderungen F-01 bis F-42, N-01 bis N-08, S-01 bis S-09 | [docs/ANFORDERUNGEN.md](docs/ANFORDERUNGEN.md) |
| Testfälle T-01 bis T-18 | [docs/TESTFAELLE.md](docs/TESTFAELLE.md) |
| Wie wir arbeiten (Branches, Pull Requests, Review) | [docs/ARBEITSWEISE.md](docs/ARBEITSWEISE.md) |

Der Projektplan selbst (Word-Dokument) wird außerhalb von GitHub gepflegt. Ändert sich dort etwas
an Anforderungen, Paketen oder Terminen, wird es per Pull Request auch hier nachgezogen.

## Termine

| Datum | Termin | Milestone |
|---|---|---|
| 11.12.2026 | Plan freigegeben | Plan freigegeben |
| 12.2.2027 | Zwischenstand bei Gabriele Hofmarcher (Import, Ein- und Austritte, Ausgetretene) | Zwischenstand Hofmarcher |
| 12.3.2027 | Vorabnahme mit allen Funktionen | Vorabnahme Hofmarcher |
| 19.3.2027 | Abnahme (letzter Schultag vor Ostern) | Abnahme |
| 26.3.2027 | Projektende: Dokumentation und Präsentation | Projektende |

## Team

| Person | Rolle | Prüft Pull Requests von |
|---|---|---|
| Magdalena Stangl | Projektleitung, Entwicklung | Gobly-Heigl, Bsteh, Teufl, Kerschbaumer |
| Thomas Gobly-Heigl | Entwicklung | Stangl |
| Lukas Bsteh | Mitarbeit, Test | Stangl |
| Dominik Teufl | Mitarbeit, Test | Stangl |
| Dion Kerschbaumer | Mitarbeit, Test | – |

Fachliche Entscheidungen und Abnahme: Gabriele Hofmarcher (FJ Genossenschaft).
Plan besprochen und genehmigt von: Thomas Riegler.

## Starten

Folgt mit AP-01 (Grundgerüst).

## Datenschutz

Echte Klassenlisten, Mitgliederdaten und die Datenbankdatei kommen **nie** ins Repository.
Zum Entwickeln und Testen gibt es nur erfundene Beispieldaten. Siehe [docs/ARBEITSWEISE.md](docs/ARBEITSWEISE.md#datenschutz-im-repository).
