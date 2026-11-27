# Anforderungen

Aus dem Projektplan, Kapitel 2 und 3. Die Nummern werden in Issues, Branches, Pull Requests und Testfällen verwendet.
Neue Anforderungen bekommen die nächste freie Nummer, bestehende Nummern werden nie umvergeben.

Quelle: A = Anforderungsdokument, M = Meeting-Notizen, F = Fragenrunde vom 27.11.2026, Team = vom Team ergänzt.

**38 Muss**, **4 Kann**. Wenn es eng wird, fallen zuerst F-17, F-30 und F-35 weg, danach wird F-29 auf E-Mail beschränkt (Kapitel 11).

## Funktionale Anforderungen

### Klassenlisten importieren

| Nr. | Anforderung | Prio | Quelle | Paket |
|---|---|---|---|---|
| F-01 | Excel-Klassenliste (.xlsx) importieren. Aufbau: Zeile 1 mit Klasse (z. B. 1IT26), Schuljahr (2026/27) und Schüleranzahl; darunter eine Tabelle mit den Spalten „Nr“ und „Zu- und Vorname“. | Muss | A, F | AP-03 |
| F-02 | Der Zusatz „ - R“ (Repetent) hinter dem Namen wird beim Import entfernt und nicht gespeichert. | Muss | F | AP-03 |
| F-03 | Die Klasse wird pro Schuljahr gespeichert, der Jahrgang (z. B. IT26, LWB 25) bleibt fest bei der Person. | Muss | A, F | AP-03 |
| F-04 | Vor der Übernahme zeigt eine Vorschau alle erkannten Personen. Bereits bekannte Personen werden erkannt und nicht doppelt angelegt. | Muss | A | AP-03 |
| F-05 | Fehlt eine Person beim erneuten Hochladen einer Klassenliste (z. B. weil sie sitzen geblieben ist oder die Schule verlassen hat), bekommt die Administration eine Nachricht und bessert die Zuordnung händisch nach: neuer Jahrgang, Austritt oder unverändert lassen. | Muss | F | AP-03 |
| F-06 | Personen lassen sich per Klick auswählen, alle ihre Daten sind auf einer Seite sichtbar. | Muss | A | AP-03 |
| F-36 | Namensänderung (z. B. neuer Nachname): Der Import erkennt sie nicht automatisch. Die Administration ändert den Namen händisch bei der Person; der alte Name bleibt im Protokoll. Taucht der neue Name in einer Klassenliste auf, zeigt die Vorschau ihn als „prüfen“, damit keine zweite Person entsteht. | Muss | F | AP-03 |

### Ein- und Austritte, Geschäftsanteil

| Nr. | Anforderung | Prio | Quelle | Paket |
|---|---|---|---|---|
| F-07 | Beitritt pro Person erfassen: Datum und die Angaben der Beitrittserklärung (welche genau: offener Punkt O-01). | Muss | A | AP-04 |
| F-08 | Beim Beitritt wird automatisch eine Mitgliedsnummer vergeben (Format: O-05). | Muss | F | AP-04 |
| F-09 | Jedes Mitglied hat genau einen Geschäftsanteil zu 10 €. Die Einzahlung wird erfasst (Datum, Betrag). | Muss | F | AP-04 |
| F-10 | Austritt pro Person erfassen: Datum und Grund. | Muss | A | AP-04 |
| F-11 | Am Schulende eines Jahrgangs treten dessen Mitglieder automatisch aus (Grund „Schulabschluss“). Die Verwaltung bestätigt den Vorgang vorher. | Muss | F | AP-04 |
| F-12 | Die Rückzahlung der 10 € wird erfasst (Datum, Betrag). Genaue Auszahlungsdaten: O-03. | Muss | F | AP-04 |
| F-13 | Auf Knopfdruck entsteht eine Liste aller Ausgetretenen mit IBAN, Kontoinhaber, Betrag und Rückzahlungsstand, als Excel-Datei. | Muss | A | AP-05 |
| F-14 | Die IBAN wird bei der Eingabe geprüft (Prüfziffer). | Muss | F | AP-04 |
| F-15 | Jede Änderung an einer Person wird mit Datum und Benutzer protokolliert. | Muss | F | AP-03 |

### Sortieren, Filtern, Auswerten

| Nr. | Anforderung | Prio | Quelle | Paket |
|---|---|---|---|---|
| F-16 | Mitgliederliste sortieren und filtern nach Klasse, Jahrgang, Status, Eintrittsdatum, Austrittsdatum, Anteil bezahlt und Rückzahlung offen; Suche nach Namen. | Muss | A | AP-05 |
| F-17 | Die gefilterte Liste lässt sich als Excel-Datei speichern. | Kann | F | AP-05 |
| F-18 | Für die Revision: aktueller Mitgliederstand sowie Beitritte und Austritte im Zeitraum, aufgeschlüsselt nach Jahrgang und Klasse (z. B. LWB 25). | Muss | A | AP-06 |
| F-19 | Der Mitgliederstand lässt sich für jeden Stichtag berechnen, mit Gegenrechnung: Stand am Anfang + Beitritte − Austritte = Stand am Ende. | Muss | A | AP-06 |
| F-20 | Der Revisionsbericht wird als Datei ausgegeben, in der Form, die der Revisionsverband verlangt (O-07). | Muss | A | AP-06 |

### Zugänge

| Nr. | Anforderung | Prio | Quelle | Paket |
|---|---|---|---|---|
| F-21 | Anmeldung mit Benutzername und Passwort, Rollen Administration, Mitarbeit und Mitglied (Kapitel 4). | Muss | M, F | AP-02 |
| F-22 | Die Administration legt Konten an, sperrt sie und setzt Passwörter zurück. | Muss | M | AP-02 |
| F-23 | Mitglieder bekommen ihren Zugang über einen Einladungslink per E-Mail und setzen ihr Passwort selbst. | Muss | F | AP-07 |
| F-24 | Mitglieder sehen ihre eigenen Daten, den Stand ihres Anteils, Nachrichten und Termine. Ihre Kontaktdaten können sie selbst ändern. | Muss | M | AP-07 |

### Mitgliederbetreuung

| Nr. | Anforderung | Prio | Quelle | Paket |
|---|---|---|---|---|
| F-25 | Ein Nachrichtenfeld in der Web-App zeigt Infos an alle Mitglieder oder an einen Jahrgang. Zusätzlich ein Newsletter über einen kostenlosen, datenschutzkonformen Dienst (Auswahl: O-21). | Muss | F | AP-08 |
| F-26 | Infos werden zusätzlich per E-Mail von genossenschaft@josephinum.at verschickt. | Muss | F | AP-08 |
| F-27 | Push-Benachrichtigungen aufs Handy und den PC. Dazu lässt sich die Web-App auf dem Startbildschirm installieren. | Muss | A | AP-09 |
| F-28 | Kalender mit Terminen (z. B. Versammlungen), sichtbar für alle Mitglieder. | Muss | F | AP-10 |
| F-29 | Terminerinnerungen per E-Mail und Push, zu einem wählbaren Zeitpunkt vor dem Termin. | Muss | F | AP-10 |
| F-30 | Ein Termin lässt sich in den eigenen Kalender übernehmen (.ics-Datei). | Kann | – | AP-10 |

### Geschenkkörbe

| Nr. | Anforderung | Prio | Quelle | Paket |
|---|---|---|---|---|
| F-31 | Öffentliche Seite mit allen bestellbaren Geschenkkörben, ohne Anmeldung. | Muss | M | AP-11 |
| F-32 | Bestellformular. Die Bestellung geht per E-Mail an genossenschaft@josephinum.at, der Besteller bekommt eine Bestätigung. | Muss | M | AP-11 |
| F-33 | Die Administration pflegt Körbe, Preise, Inhalt und Sichtbarkeit in der Anwendung. | Muss | M | AP-11 |
| F-34 | Übersicht aller Bestellungen mit Status (neu, in Arbeit, erledigt, storniert). | Muss | M | AP-11 |
| F-35 | Bestellungen als Excel-Datei speichern. | Kann | – | AP-11 |

### MCP-Schnittstelle für KI-Assistenten

| Nr. | Anforderung | Prio | Quelle | Paket |
|---|---|---|---|---|
| F-37 | Die Anwendung bietet einen MCP-Server unter der Adresse /mcp an, den KI-Assistenten über HTTP erreichen. | Muss | Team | AP-12 |
| F-38 | Zugriff nur mit einem persönlichen Zugangsschlüssel, den man in der Web-App erzeugt. Es gelten dieselben Rollenrechte wie in der Web-App; der Schlüssel läuft ab und lässt sich jederzeit widerrufen. | Muss | Team | AP-12 |
| F-39 | Lesende Werkzeuge: Personen suchen (Name, Klasse, Jahrgang, Status), Mitgliederstand und Revisionszahlen für Stichtag oder Zeitraum, offene Anteile und Rückzahlungen (ohne IBAN), Termine, Nachrichten, Bestellungen. | Muss | Team | AP-12 |
| F-40 | Schreibende Werkzeuge nur als Entwurf (Nachricht oder Termin entwerfen). Versendet wird erst in der Web-App, nachdem ein Mensch bestätigt hat. | Kann | Team | AP-12 |
| F-41 | Über MCP werden nie IBAN, Geburtsdatum, Adresse, Telefonnummer oder E-Mail-Adresse herausgegeben. | Muss | Team | AP-12 |
| F-42 | Jeder MCP-Aufruf wird protokolliert: wer, wann, welches Werkzeug. | Muss | Team | AP-12 |

## Nicht-funktionale Anforderungen (von Anfang an)

| Nr. | Anforderung | Paket |
|---|---|---|
| N-01 | Bedienung auf Deutsch, im Browser am PC und am Handy (aktuelle Versionen von Chrome, Edge, Firefox, Safari). | AP-01 |
| N-02 | Eine Liste mit 500 Personen lädt in unter 2 Sekunden. | AP-05 |
| N-03 | ohne Anmeldung und als Mitglied Admin-Adressen aufrufen | AP-02 |
| N-04 | Passwörter werden nur verschlüsselt (gehasht) gespeichert, nie im Klartext. | AP-02 |
| N-05 | IBANs werden in Listen verdeckt angezeigt (AT61 •••• •••• •••• 3201) und nur auf Knopfdruck vollständig. | AP-05 |
| N-06 | Geheimnisse (Mail-Passwort, Push-Schlüssel) stehen nicht im Code und nicht auf GitHub, sondern in einer lokalen Konfigurationsdatei. | AP-01, AP-07 |
| N-07 | Code, Kommentare und Oberfläche sind so geschrieben, dass das Team sie bei der Präsentation erklären kann. | alle |
| N-08 | Wichtige Berechnungen (Import, IBAN, Revision, automatischer Austritt) sind durch automatische Tests abgedeckt. | AP-01 |

## Sicherheit, Datenschutz, Schulserver (vor der Abnahme, AP-13)

S-03 (Anmeldung mit Schulkonten) kommt erst nach dem Projekt.

| Nr. | Thema | Was zu tun ist |
|---|---|---|
| S-01 | Betrieb auf dem Schulserver | Installation auf dem Windows-Server der Schule, Start als Dienst, Absprache mit der Schul-IT. |
| S-02 | HTTPS / SSL | Zertifikat für die Adresse der Anwendung. Ohne HTTPS funktionieren Push-Nachrichten außerhalb des Entwicklungsrechners nicht. |
| S-03 | Anmeldung mit Schulkonten (SSO) | Prüfen, ob die Schule Microsoft 365 nutzt; dann Anmeldung über Microsoft (OpenID Connect) statt SAML. Erst nach dem Projekt, nicht Teil von AP-13. |
| S-04 | Datenschutz (DSGVO) | Verantwortliche Stelle festlegen (Genossenschaft oder Schule), Verarbeitungsverzeichnis, Informationspflicht beim Beitritt, Einwilligung für Push und E-Mail. |
| S-05 | Minderjährige | Klären, ob für Mitglieder unter 18 Jahren Daten von Erziehungsberechtigten nötig sind (hängt an O-01). |
| S-06 | ausgetretene Person mit abgelaufener Löschfrist anlegen, Löschlauf starten | Personendaten gelöscht oder anonymisiert, Revisionszahlen unverändert |
| S-07 | Sicherung erstellen, Testdaten ändern, Sicherung wiederherstellen | Daten entsprechen wieder dem Stand der Sicherung |
| S-08 | fünfmal ein falsches Passwort eingeben | Konto ist vorübergehend gesperrt, der Versuch steht im Anmeldeprotokoll |
| S-09 | MCP-Schnittstelle absichern | MCP nur über HTTPS, Zugangsschlüssel nur als Hash gespeichert und mit Ablaufdatum, Begrenzung der Aufrufe pro Minute, Klärung, welche Daten an KI-Dienste gehen dürfen (Minderjährige, DSGVO; O-20). |
