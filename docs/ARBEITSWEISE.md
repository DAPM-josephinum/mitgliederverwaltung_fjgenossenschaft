# Arbeitsweise

Wie wir im Projekt mit GitHub arbeiten (Projektplan, Kapitel 9 und 10).

## Kurzfassung

1. Nächstes offenes Issue mit `typ:aufgabe` nehmen und dich als **Assignee** eintragen.
2. Branch anlegen, Name steht im Issue: `ap03-2-import-logik-mit-tests`.
3. Kleine Commits mit verständlicher Nachricht auf Deutsch.
4. Pull Request gegen `main`, Vorlage ausfüllen, `Closes #<Issue>` hineinschreiben.
5. Prüfende Person anfragen (Tabelle unten). GitHub Actions muss grün sein.
6. Nach der Genehmigung mergt die Person, die den Pull Request erstellt hat (Squash).

Niemand arbeitet direkt auf `main`.

## Backlog

Das Backlog sind die [Issues](https://github.com/DAPM-josephinum/mitgliederverwaltung_fjgenossenschaft/issues). Die Art erkennt man am Label `typ:…`:

| Label | Was | Beispiel |
|---|---|---|
| `typ:arbeitspaket` | Ein Arbeitspaket aus dem Plan (AP-00 bis AP-14). Hat „Fertig, wenn“ und die Testfälle. Wird geschlossen, wenn alle Unter-Issues erledigt und die Funktionstests bestanden sind. | `AP-03: Personen und Klassenlisten-Import (F-01 bis F-06, F-15, F-36)` |
| `typ:aufgabe` | Ein Pull Request aus dem Paket. Unter-Issue des Arbeitspakets. | `AP-03.2: Import-Logik mit Tests (F-01, F-02, …)` |
| `typ:offener-punkt` | Eine Frage aus Kapitel 14, die vor oder während eines Pakets geklärt werden muss. Antwort ins Issue, dann schließen. | `O-01: Welche Angaben stehen auf der Beitrittserklärung?` |
| `Fehler` | Fehler aus Funktionstest oder Betrieb. Vorlage „Fehler“ verwenden. | `Fehler: Import bricht bei leerer Zeile ab` |
| `rückmeldung` | Rückmeldung von Gabriele Hofmarcher (Zwischenstand, Vorabnahme). | |

Weitere Labels:

| Label | Bedeutung |
|---|---|
| `ap:00` … `ap:14` | Zu welchem Arbeitspaket gehört das Issue. Filter: `label:ap:03` |
| `prio:muss` / `prio:kann` | Muss- oder Kann-Anforderung. Wenn es eng wird, fallen `prio:kann` zuerst weg. |
| `klärt:hofmarcher`, `klärt:lehrkraft`, `klärt:schul-it`, `klärt:team` | Wer einen offenen Punkt beantwortet. Fragen an Frau Hofmarcher werden gesammelt geschickt: `is:open label:klärt:hofmarcher` |
| `good first issue` | Gut für Teammitglieder mit wenig Zeit (AP-11 Geschenkkörbe). |

**Milestones** sind die fünf Termine aus Kapitel 11. Jedes Arbeitspaket und jede Aufgabe hängt am Termin, zu dem sie fertig sein muss.

**Abhängigkeiten** („Braucht“ im Plan) sind in GitHub als *blocked by* eingetragen: Ein Arbeitspaket ist blockiert, solange die Pakete und offenen Punkte, die es braucht, nicht geschlossen sind.

Nützliche Filter (Suchfeld in Issues):

```
is:open label:typ:aufgabe no:assignee milestone:"Zwischenstand Hofmarcher"
is:open assignee:@me
is:open label:typ:offener-punkt label:klärt:hofmarcher
is:open label:Fehler
```

Die Pakete sind nicht fest auf Personen verteilt: Wer frei ist, nimmt das nächste offene Issue, dessen Arbeitspaket nicht mehr blockiert ist.

## Branches und Commits

- Pro Aufgaben-Issue ein Branch, Name steht im Issue: `ap<Paket>-<Nr>-<kurzer-titel>`, z. B. `ap03-2-import-logik-mit-tests`.
- Für Fehler: `fehler-<issue>-<kurz>`, z. B. `fehler-57-import-leere-zeile`.
- Für Doku oder Repo-Pflege: `ap00-<kurz>` bzw. `ap14-<kurz>`.
- Commits klein halten, Nachricht auf Deutsch im Imperativ: `Jahrgang aus Klasse ableiten`.

## Pull Requests

Jeder Pull Request geht gegen `main`, braucht **eine Genehmigung** und eine **grüne Prüfung** (ab AP-01.3).

| Pull Request von | Prüft |
|---|---|
| Thomas Gobly-Heigl, Lukas Bsteh, Dominik Teufl, Dion Kerschbaumer | Magdalena Stangl |
| Magdalena Stangl | Thomas Gobly-Heigl, Lukas Bsteh oder Dominik Teufl |

Die prüfende Person liest den Code, probiert die Funktion nach der Anleitung „Wie testen?“ aus und genehmigt oder schreibt Kommentare.
Nach der Genehmigung mergt die Person, die den Pull Request erstellt hat. Gemergt wird mit **Squash**, damit `main` pro Aufgabe einen Commit hat.

Ein Pull Request ist fertig, wenn (Checkliste in der Vorlage):

- die Anforderungen aus dem Issue erfüllt sind
- Build und Tests grün sind
- neue Fachlogik einen automatischen Test hat
- Datenbankänderungen eine Migration haben
- keine Passwörter, Schlüssel oder echten Schülerdaten im Code stehen
- eine zweite Person ihn genehmigt hat

## Tests

Nach dem letzten gemergten Pull Request eines Pakets spielen Bsteh, Teufl und Kerschbaumer die Testfälle des Pakets aus [TESTFAELLE.md](TESTFAELLE.md) durch.
Fehler kommen als Issue mit der Vorlage „Fehler“ ins Backlog, das Ergebnis in die Spalte „Ergebnis“ der Testfall-Liste.

## Offene Punkte

Bis eine Frage beantwortet ist, arbeitet das Team mit dem Vorschlag aus dem Plan.
Kommt eine Antwort: ins Issue schreiben (wer, wann, was), Issue schließen, und falls sich Anforderungen ändern, `docs/ANFORDERUNGEN.md` per Pull Request anpassen.

## Datenschutz im Repository

- Echte Klassenlisten, Beitrittserklärungen und die Datenbankdatei kommen nie ins Repository. Die `.gitignore` sperrt `*.db`, `*.sqlite` und alle `.xlsx` außer in Ordnern `Testdaten/`.
- In `Testdaten/` liegen nur **erfundene** Personen.
- Passwörter, Mail-Zugang und Push-Schlüssel stehen in einer lokalen Konfigurationsdatei (N-06), nie im Code.
- Ist doch etwas Echtes auf GitHub gelandet: sofort Magdalena Stangl Bescheid geben. Ein neuer Commit, der die Datei löscht, reicht nicht, weil sie in der Historie bleibt.
