---
tags:
  - insy
  - 5te_klasse
created: 2026-10-07T11:30:39+02:00
modified: 2026-10-07T11:47:29+02:00
---
# Vom Datenchaos zur 3. Normalform
# Ausgangssituation

Die fiktive Autovermietung _CityCar_ speichert sämtliche Buchungsdaten in einer einzigen Textspalte
Buchungsdaten. Stammdaten werden ständig kopiert, Zusatzleistungen stecken als Listen im Text
und niemand überprüft die Eingaben. Entwickeln Sie eine relationale Datenbank bis zur dritten
Normalform und planen Sie die Migration der vorhandenen Daten.

**Voraussetzungen:** Grundkenntnisse zu Primär- und Fremdschlüsseln sowie SQL.
**Abgabe:** Schritte der Normalisierung, Abhängigkeiten, ER-Diagramm oder Schema der Relationen,
Migrationsskript bzw. präziser Pseudocode, Fehlerprotokoll und Prüfergebnisse.

# Geschäftsregeln und Datenformat

- Eine Mietnummer bezeichnet genau einen Vertrag mit einer Person, einem Fahrzeug und einer Abholstation. Die Rückgabe erfolgt in dieser Übung immer an derselben Station.
- Kundennummern, Fahrzeugnummern, Kategoriecodes, Stationsnummern und Extracodes sind stabile fachliche Kennungen. Namen sind keine Schlüssel. Fahrzeugkennzeichen sind in diesem Übungsbestand eindeutig und unveränderlich.
- Ein Fahrzeug gehört genau einer Kategorie an; ein Kategoriecode bestimmt deren Bezeichnung. Stationsdaten sind über die Stationsnummer bestimmt. Stammdatenänderungen werden hier nicht historisiert.
- Eine Miete hat null bis mehrere Extras. Derselbe Extracode darf je Miete nur einmal vorkommen. Die Menge ist daher immer ein Wert, er muss nicht gespeichert werden.
- Der Fahrzeug-Tagespreis wird pro Vertrag vereinbart. Ebenso wird der Extra-Tagespreis je Vertrag und Extra vereinbart. Beide sind historische Preise und dürfen nicht aus heutigen Tarifen ersetzt werden.
- Mietzeiträume sind halboffen: Beginn inklusive, Ende exklusive. Miettage sind die Datumsdifferenz; Ende muss nach Beginn liegen. Beträge sind in Euro, ohne Steuern und Rabatte.
- Felder sind durch ;getrennt. Innerhalb eines Felds trennt|die Teilwerte. Extras haben das Format \[Code|Name|Tagespreis,...\]; \[] bedeutet keine Extras. Diese Trennzeichen kommen nicht in den eigentlichen Werten vor.
- Kundenteil: Nummer, Name, E-Mail, Telefon. Fahrzeugteil: Nummer, Kennzeichen, Kategoriecode, Kategoriebezeichnung. Stationsteil: Nummer, Stadt, PLZ, Straße, Hausnummer. Fehlendes Telefon wird als-notiert.
- Datumsformate könnenTT.MM.JJJJoderJJJJ-MM-TTsein, Dezimaltrennzeichen Komma oder Punkt. Die Labels sind einheitlich; Fehler liegen in den Werten und Wiederholungen.

**Wichtig:** Die folgenden Z1–Z8 sind nur Referenzen der Zeilen im Arbeitsblatt, keine zweite Tabellenspalte. Zeilenumbrüche innerhalb der Zellen dienen ausschließlich der Lesbarkeit. Alle Datensind synthetisch.

# Die Tabelle, eine Katastrophe: genau eine Spalte

```
Buchungsdaten (TEXT)
Z
Miete=M1001; Kunde=K01|Lea Fischer|lea@example.test|0664 1111111;
Auto=F01|W-101CC|C01|Kompakt;
Station=S01|Wien|1220|Wagramer Strasse|10;
Von=01.10.2026; Bis=04.10.2026; Tag=49,90;
Extras=[NAV|Navi|5,00,KIND|Kindersitz|3,00]
Z
Miete=M1002; Kunde=K02|Sam Berger|sam@example.test|0676 2222222;
Auto=F02|W-202CC|C01|Kompakt;
Station=S01|Wien|1220|Wagramer Strasse|10;
Von=2026-10-02; Bis=2026-10-05; Tag=54.90; Extras=[NAV|Navi|5.00]
Z
Miete=M1003; Kunde=K01|Lea Fischer|lea@example.test|06641111111;
Auto=F03|G-303CC|C02|SUV;
Station=S02|Graz|8010|Elisabethstrasse|20;
Von=05.10.2026; Bis=07.10.2026; Tag=89,00; Extras=[]
Z
Miete=M1002; Kunde=K02|Sam Berger|sam@example.test|0676 2222222;
Auto=F02|W-202CC|C01|Kompakt;
Station=S01|Wien|1220|Wagramer Strasse|10;
Von=2026-10-02; Bis=2026-10-05; Tag=54.90; Extras=[NAV|Navi|5.00]
Z
Miete=M1004; Kunde=K03|Alex Novak|alex@example.test|-;
Auto=F01|W-101CC|C01|Kompakt;
Station=S01|Wien|1220|Wagramer Strasse|10;
Von=08.10.2026; Bis=10.10.2026; Tag=59,90; Extras=[KIND|Kindersitz|3,00]
Z
Miete=M1005; Kunde=K02|Sam Berger|SAM@example.test|0676 2222222;
Auto=F03|G-303CC|C02|SUV;
Station=S02|Graz|8010|Elisabethstrasse|20;
Von=2026-10-08; Bis=2026-10-11; Tag=92.00; Extras=[ZUS|Zusatzfahrer|8.00]
Z
Miete=M1006; Kunde=K03|Alex Novak|alex@example.test|-;
Auto=F02|W-202CC|C01|Kompakt;
Station=S01|Wien|1220|Wagramer Strasse|10;
Von=12.10.2026; Bis=15.10.2026; Tag=54,90;
Extras=[NAV|Navi|6,00,ZUS|Zusatzfahrer|8,00]
Z
Miete=M1007; Kunde=K02|Sam Bergmann|sam@example.test|0676 2222222;
Auto=F01|W-101CC|C01|Kompakt;
Station=S01|Wien|1220|Wagramer Strasse|10;
Von=20.10.2026; Bis=18.10.2026; Tag=49,90; Extras=[NAV|Navi|5,00]
```

# Teil A – Analysieren und normalisieren (50 Punkte)


## A1 Probleme erkennen (8 P). Finden Sie mindestens vier unterschiedliche Strukturprobleme. Beschreiben Sie je eine konkrete Änderungs-, Einfüge- und Löschanomalie anhand der Daten. Trennen Sie Strukturprobleme von Datenqualitätsproblemen.

Eine einzige Textspalte (verletzt 1NF).  
Wiederholungsgruppe Extras als Liste im Text (Mehrwertiges Attribut.)
Stammdaten (Kunde, Fahrzeug, Station) je Vertrag kopiert (Redundanz).  
Kategoriebezeichnung hängt am Fahrzeug (transitive Abhängigkeit).
Ein neues Fahrzeug ohne Vertrag lässt sich nicht speichern, da kein Mietvertrag existiert.  
Löscht man die einzige Miete eines Kunden, verschwinden alle Kundendaten mit.

## A2
Erste Normalform (10 P). Extrahieren Sie atomare Attribute und lösen Sie die Extra-Listen auf. Wählen Sie geeignete Schlüssel. Zeigen Sie den Vertrag M1001 und seine Extras sowie M1003 ohne Extras. Erklären Sie, warum bloßes Aufteilen des Texts in mehr Spalten nicht ausreicht.

Atomare Attribute: 
MietNr, Beginn, Ende, Kunde(KundenNr, Name, EMail, Telefon), Fahrzeug(FahrzeugNr, Kennzeichen, KatCode, KatBez), Station(StationsNr, Stadt, PLZ, Strasse, HNr) und eine eigene Relation für Extras: Mietvertrag(MietNr PK, KundenNr, FahrzeugNr, StationsNr, Beginn, Ende) Miet_Extra(MietNr, ExtraCode) – PK (MietNr, ExtraCode); mit [] gibt es schlicht keine Zeile (keine Leer-Extras nötig).  
M1001: eine Zeile im Vertrag, je Extra (z. B. E1|Navigationsgerät|5,00) eine Zeile in Miet_Extra. M1003: nur die Vertragszeile, keine Extra-Zeilen.  
Warum bloßes Spaltenaufteilen nicht reicht: die Extra-Liste ist eine wiederholende Gruppe variabler Länge – feste Spalten (Extra1, Extra2, …) verletzten weiterhin 1NF (NULLs, Obergrenze) und die vertrags- und extra-individuellen Tagespreise müssten zusätzlich pro Spalte gepaart werden.

## A3 
Abhängigkeiten und zweite Normalform (12 P). Notieren Sie die funktionalen Abhängigkeiten. Zeigen Sie an einer Relation mit zusammengesetztem Schlüssel eine partielle Abhängigkeit und beseitigen Sie diese. Begründen Sie, welche Relationen bereits in 2NF sind.

Funktionale Abhängigkeiten:
MietNr → Beginn, Ende, KundenNr, FahrzeugNr, StationsNr  
MietNr, ExtraCode → ExtraTagespreis  
KundenNr → Name, EMail, Telefon  
FahrzeugNr → Kennzeichen, KatCode; 
Kennzeichen → FahrzeugNr  
KatCode → KatBez 
StationsNr → Stadt, PLZ, Strasse, HNr; 
ExtraCode → ExtraName (Stamm-Extra)  
FahrzeugNr, MietNr → FahrzeugTagespreis (Preis pro Vertrag → gehört zum Vertrag)  
Partielle Abhängigkeit: In der flachen Relation Miet_Extra_Flach(MietNr, ExtraCode, ExtraName, KundenName, Beginn, …) hängen ExtraName, KundenName, Beginn nur von ExtraCode bzw. MietNr allein ab, nicht vom gesamten Schlüssel (MietNr, ExtraCode) → Zerlegung: Mietvertrag, Miet_Extra(MietNr, ExtraCode, ExtraTagespreis), Stammrelationen.  
Bereits in 2NF sind alle Relationen mit Schlüsselattribut-Einzelschlüssel: Mietvertrag, Kunde, Fahrzeug, Kategorie, Station, Extra – dort kann keine partielle Abhängigkeit auftreten; nur Miet_Extra hatte sie vor der Zerlegung.

## A4 
Dritte Normalform (14 P). Beseitigen Sie transitive Abhängigkeiten und erstellen Sie ein Relationenschema oder ER-Diagramm. Markieren Sie PK, FK und Kardinalitäten. Begründen Sie die Position der beiden historischen Tagespreise.

## A5 
Integrität und Rekonstruktion (6 P). Legen Sie sinnvolle Datentypen und Constraints fest. Beschreiben Sie, wie M1001 vollständig rekonstruiert werden kann und wie M1003 ohne Extras bei der Abfrage erhalten bleibt.

**Hinweis zur Normalisierung:** Es ist erlaubt, bei der 1NF bereits eine Vertragsrelation und eine Extra-Zuordnungsrelation zu bilden. Erzwingen Sie keine künstlichen Leer-Extras. Ein einspaltiges Rohtextarchiv kann technisch gültig sein; es modelliert jedoch die fachlichen Einzelwerte und
Beziehungen nicht brauchbar.

# Teil B – Bestehende Daten migrieren (50 Punkte)

B1. Staging und Parser (10 P). Übernehmen Sie die Rohdaten unverändert in einen Staging-Bereich. Vergeben Sie dort technische Zeilenreferenzen und einen Importlauf. Definieren Sie das Parsing einschließlich leerer Extra-Listen, Anzahl der Teilwerte und Umgang mit unbekannten oder fehlenden Feldern. Die Ein-Spalten-Vorgabe gilt nur für die Quelle, nicht für
das Staging.

B2. Bereinigung und Konflikte (12 P). Vereinheitlichen Sie Datums- und Betragsformate, Telefon-Schreibweisen und E-Mail-Großschreibung. Für diese fiktiven Daten ist Kleinschreibung der gesamten E-Mail ausdrücklich vereinbart; sie ist keine allgemeingültige Regel für reale E-Mail-Adressen. Identifizieren Sie Dubletten und Widersprüche. Bestimmen Sie für jede Zeile: importieren, als Dublette protokollieren oder vollständig in Quarantäne stellen.
Keine Werte stillschweigend erfinden oder überschreiben.

B3. Zieltabellen laden (12 P). Implementieren Sie SQL bzw. ausführlichen Pseudocode für die Migration. Laden Sie Stammdaten vor abhängigen Tabellen. Nutzen Sie eine Transaktion für den freigegebenen Import. Bewahren Sie vereinbarte Preise. Erklären Sie den Umgang mit einer vorhandenen Mietnummer und widersprüchlichem Inhalt.

B4. Prüfen und abgleichen (10 P). Prüfen Sie Tabellenanzahlen, Fremdschlüssel, Dubletten, Mietzeiträume, fehlende Telefonnummern und Extra-Listen. Berechnen Sie den Vertrags- betrag für M1001 und M1006 nach der untenstehenden Formel. Dokumentieren Sie alle
abgewiesenen oder ausgelassenen Quellzeilen mit Ursache.

B5. Wiederanlauf und Rückabwicklung (6 P). Führen Sie einen zweiten Import desselben Bestands durch. Es dürfen keine zusätzlichen fachlichen Datensätze entstehen. Beschreiben Sie Backup, Fehlerfall, Rollback und nachvollziehbare Zuordnung der Zielwerte zu Quellzei-
len.
$$\begin{aligned}
\text{Betrag( m )} = Miettage( m ) \cdot \left( AutoTag( m ) + \sum_{e ∈Extras( m )}{ExtraTag( m, e )} \right)
\end{aligned}$$
**Scope:** Migriert wird ausschließlich in eine lokale Übungsdatenbank, nicht in ein produktives Sys-
tem. Die Umsetzung kann etwa mit PostgreSQL oder einem anderen ausdrücklich angegebenen
relationalen DBMS erfolgen.


