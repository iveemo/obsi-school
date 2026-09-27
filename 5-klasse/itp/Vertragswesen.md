---
tags:
  - 4te_Klasse
  - itp
created: 2026-09-24T13:39:41+02:00
modified: 2026-09-24T14:14:47+02:00
---
## Grundidee klären (Werkvertrag vs. Dienstvertrag)
- Werkvertrag: Es wird ein konkretes Ergebnis („Werk“) geschuldet (z. B. funktionierendes Zutrittssystem inkl. Abnahme).
- Dienstvertrag: Es wird Tätigkeit/Arbeitszeit geschuldet (ohne garantierten Erfolg).
- Contracting: Der Contractor übernimmt langfristig mehrere Aufgaben – beispielsweise Planung, Finanzierung, Errichtung, Betrieb und Wartung einer Anlage. Vergütung, Laufzeit, Leistungen und Verantwortlichkeiten werden in einem Contracting-Vertrag geregelt.

## Kopfteil / Parteien sauber definieren
- Auftraggeber (AG): Name/Firma, Adresse, UID/Firmenbuch, Vertretung, Kontakt
- Auftragnehmer (AN): Name/Firma, Adresse, UID/Firmenbuch, Kontakt
- Optional: Projektbezeichnung, Angebots-/Bestellnummer, Datum, Anhänge (Leistungsbeschreibung, Preisblatt)
- Tipp: Dazuschreiben, dass Angebot/Lastenheft/Beilagen Vertragsbestandteil sind (mit Versionsdatum).

## Vertragsgegenstand (kurz und eindeutig)
### 3 - 6 Zeilen
- Was wird geliefert (Ergebnis/Werk)?
- Wofür (Zweck/Use Case)?
- Wo (Standort/e)?
- In welchem Umfang (z. B. Anzahl Geräte, Nutzergruppen)?

## Klar strukturieren Leistungsbeschreibung (Scope) – der wichtigste Teil
- Funktionen (Was muss das Werk können?)
- Lieferobjekte (Hardware, Software, Doku, Schulung)
- Qualität/Kriterien (z. B. Reaktionszeit, Erkennungsrate, Verfügbarkeit – nur wenn sinnvoll)
- Schnittstellen & Abhängigkeiten (Datenquellen, Netzwerk, Strom, Zugänge)
- Out of Scope (alles, was nicht enthalten ist: Elektroarbeiten, Serverbetrieb, Kartenproduktion …)
- Tipp: Messbar formulieren: „2 Eingänge, unabhängig“, „Protokoll enthält: Zeitpunkt, Token, Ergebnis“, „Regel: 1× pro Tag“.

## verhindert Streitigkeiten Mitwirkungspflichten des Auftraggebers
- Datenbereitstellung (Formate, Qualität, rechtzeitig)
- Zugänge/Termine/Ansprechperson
- Infrastruktur (Strom/Netzwerk/Montageflächen)
- Entscheidungen & Freigaben in Fristen
- Wichtig: Dazu schreiben, was passiert, wenn Mitwirkung ausbleibt (Terminverschiebung, Mehrkosten nach Aufwand).

## Termine, Meilensteine, Änderungsmanagement
- Startdatum, Liefer-/Installationsfenster, Abnahmetermin
- Optional: Meilensteine (Konzept → Lieferung → Installation → Test → Abnahme)
- Change Request: Wie werden Änderungen am Scope beauftragt?
- schriftlich, Aufwand/Preis/Terminfolgen vorab freigeben

## Preis & Zahlungsbedingungen
- Eindeutig entscheiden:
- Pauschalpreis (inkl. klarer Leistungsbeschreibung) oder
- Aufwand (Stundensatz, Spesenregel, Kostenvoranschlag, Reporting)
- Zahlungsplan (üblich):
- Teilzahlung bei Beauftragung
- Teilzahlung bei Lieferung/Installation
- Rest nach Abnahme

## Abnahme (Werkvertrag-Kern)
- Abnahmekriterien (Checkliste)
- Testablauf (wer testet, wie lange, Protokoll)
- Mängelklassen (wesentlich/unwesentlich) und Nachbesserungsfrist
- Fiktive Abnahme nur vorsichtig: z. B. wenn AG nicht testet trotz Termin

## Gewährleistung, Wartung, Support (trennen!)
- Gewährleistung / Garantie: gesetzlich / vertraglich konkretisieren (Fristen, Ablauf)
- Wartung/SLA (optional extra): Reaktionszeit, Supportzeiten, Updates, Remote-Zugriff, Pauschale (Service Level Agreement)
- Tipp: Klar definieren, ob Updates/Anpassungen enthalten sind oder als Zusatzleistung gelten.

## Rechte, Eigentum, Lizenzen
- Eigentum an Hardware nach Zahlung
- Nutzungsrechte an Software (einfach/nicht übertragbar, Standort/Anzahl Geräte);
- Drittsoftware: Lizenzbedingungen
- Optional: Quellcode/Customizing-Regelung

## Datenschutz & IT-Sicherheit (wenn Daten verarbeitet werden)
- Rollen: AG Verantwortlicher, AN Auftragsverarbeiter (wenn zutreffend)
- AVV (Auftragsverarbeitungsvereinbarung) falls nötig
- Logging: Minimalprinzip, Speicherdauer, Zugriff, Löschung
- TOMs (technische/organisatorische Maßnahmen) grob benennen

## Haftung & Vertragsstrafen (realistisch halten)
- Unbeschränkt bei Vorsatz/grober Fahrlässigkeit
- Begrenzung bei leichter Fahrlässigkeit (Cap)
- Ausschluss entgangener Gewinn/Folgeschäden (soweit zulässig)
- Vertragsstrafe nur, wenn wirklich gewollt und berechenbar

## Vertraulichkeit, Kündigung, Schlussbestimmungen
- Vertraulichkeit (auch nach Vertragsende)
- Kündigung aus wichtigem Grund
- Schriftform/Änderungen
- Gerichtsstand & anwendbares Recht (z. B. Österreich)
- Salvatorische Klausel (üblich)

## Mini-Checkliste (zum Durchgehen vor dem Unterschreiben)
- [ ] Ergebnis/Werk eindeutig beschrieben?
- [ ] Scope vs. Out-of-Scope sauber getrennt?
- [ ] Abnahmekriterien messbar und vollständig?
- [ ] Mitwirkungspflichten + Folgen bei Verzug geregelt?
- [ ] Preislogik (Pauschal/Aufwand) klar + Zahlungsplan?
- [ ] Change-Request-Prozess drin?
- [ ] Datenschutz/AVV-Thema geprüft?
- [ ] Support/Wartung als eigener Abschnitt/Option klar getrennt?
- [ ] Haftung angemessen und verständlich?