# Testfälle

Getestet wird auf drei Ebenen (Projektplan, Kapitel 12):

1. **Automatische Tests** bei jedem Pull Request (GitHub Actions).
2. **Funktionstests** durch Bsteh, Teufl und Kerschbaumer, sobald der letzte Pull Request eines Pakets gemergt ist. Fehler kommen als Issue mit dem Label `Fehler` ins Backlog.
3. **Abnahme** durch Gabriele Hofmarcher am 19.3.2027 anhand der Muss-Anforderungen.

Jede Muss-Anforderung hat mindestens einen Testfall. Die Liste wächst mit jedem Arbeitspaket: neue Testfälle bekommen die nächste freie Nummer.

## Automatische Tests

| Bereich | Was geprüft wird |
|---|---|
| Import | Namen trennen, „ - R“ entfernen, Jahrgang ableiten, Kopfzeile finden, keine Doppelten beim zweiten Import |
| IBAN | gültige und ungültige Beispiele, Leerzeichen und Kleinbuchstaben |
| Mitgliedschaft | Status je Datum, kein Austritt vor dem Beitritt, kein zweiter Beitritt, Schuljahresabschluss |
| Revision | Stand am Stichtag und Gegenrechnung mit Testdaten, deren Ergebnis vorher von Hand berechnet wurde |
| Rechte | jede Rolle versucht jede geschützte Seite zu öffnen; ein Mitglied sieht keine fremden Daten |

## Funktionstests

Spalte „Ergebnis“: Datum, Kürzel, ✔ oder ✘ mit Issue-Nummer, z. B. `3.2. LB ✘ #57`.

| Testfall | Prüft | Schritte | Erwartet | Paket | Ergebnis |
|---|---|---|---|---|---|
| T-01 | F-01 bis F-04 | Klassenliste 1IT26 importieren, danach dieselbe Datei noch einmal | 28 Personen, Jahrgang IT26, beim zweiten Mal 0 neu und 28 bekannt | AP-03 | |
| T-02 | F-07 bis F-09 | Beitritt mit Einzahlung für eine Person erfassen | Mitgliedsnummer vergeben, Status Mitglied, Anteil bezahlt | AP-04 | |
| T-03 | F-10, F-12, F-13 | Austritt erfassen, Liste der Ausgetretenen öffnen, Rückzahlung erfassen | Person mit IBAN in der Liste, danach „zurückgezahlt“ | AP-04, AP-05 | |
| T-04 | F-11 | Schuljahresabschluss für einen Jahrgang | alle aktiven Mitglieder des Jahrgangs ausgetreten mit Grund Schulabschluss | AP-04 | |
| T-05 | F-18, F-19 | Revision für einen Zeitraum mit bekannten Testdaten | Zahlen stimmen mit der Handrechnung überein | AP-06 | |
| T-06 | F-23, F-24 | Einladung senden, Link öffnen, Passwort setzen | Mitglied ist angemeldet und sieht nur eigene Daten | AP-07 | |
| T-07 | F-25 bis F-27 | Nachricht an einen Jahrgang senden | erscheint im Nachrichtenfeld, kommt per E-Mail und Push an, nur bei diesem Jahrgang | AP-08, AP-09 | |
| T-08 | F-28, F-29 | Termin mit Erinnerung 1 Stunde vorher anlegen | Erinnerung kommt zur richtigen Zeit per E-Mail und Push | AP-10 | |
| T-09 | F-31 bis F-33 | Preis eines Korbs ändern, Korb öffentlich bestellen | neuer Preis sichtbar, E-Mail an genossenschaft@josephinum.at, Bestätigung beim Besteller | AP-11 | |
| T-10 | N-03 | ohne Anmeldung und als Mitglied Admin-Adressen aufrufen | Weiterleitung zur Anmeldung bzw. kein Zugriff | AP-02 | |
| T-11 | S-01, S-02 | Anwendung auf dem Schulserver über https:// aufrufen | Seite lädt verschlüsselt, http:// leitet auf https:// um | AP-13 | |
| T-12 | S-07 | Sicherung erstellen, Testdaten ändern, Sicherung wiederherstellen | Daten entsprechen wieder dem Stand der Sicherung | AP-13 | |
| T-13 | S-08 | fünfmal ein falsches Passwort eingeben | Konto ist vorübergehend gesperrt, der Versuch steht im Anmeldeprotokoll | AP-13 | |
| T-14 | S-06 | ausgetretene Person mit abgelaufener Löschfrist anlegen, Löschlauf starten | Personendaten gelöscht oder anonymisiert, Revisionszahlen unverändert | AP-13 | |
| T-15 | F-05 | Klassenliste erneut hochladen, in der eine Person fehlt (sitzen geblieben) | Administration bekommt eine Nachricht, kann die Person händisch einem neuen Jahrgang zuordnen | AP-03 | |
| T-16 | F-36 | Nachnamen einer Person händisch ändern, danach Klassenliste mit neuem Namen importieren | alter Name im Protokoll, Person beim Import als bekannt erkannt, keine zweite Person | AP-03 | |
| T-17 | F-37 bis F-39, F-42 | Claude Desktop mit Mitarbeitsschlüssel verbinden, Mitgliederstand von IT26 abfragen | richtige Zahl, Aufruf im MCP-Protokoll | AP-12 | |
| T-18 | F-38, F-41 | über MCP nach IBAN und E-Mail einer Person fragen; danach Schlüssel widerrufen und erneut abfragen | keine IBAN und keine E-Mail in der Antwort; nach dem Widerruf kein Zugriff mehr | AP-12 | |
