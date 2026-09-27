---
tags:
  - itsi
  - 5te_klasse
created: 2026-09-21T14:44:56+02:00
modified: 2026-09-27T22:46:18+02:00
---
## 1 Schutzbedarf und Risiken 
Bestimmen Sie für mindestens ==drei wichtige Systeme oder Datenbestände== Ihres Unternehmens den Schutzbedarf hinsichtlich ==Vertraulichkeit, Integrität und Verfügbarkeit==. Ordnen Sie außerdem mindestens ==einem System ein erweitertes Schutzziel== zu (zum Beispiel Authenticity oder Non Repudiation) und ==begründen== Sie diese Zuordnung. Leiten Sie daraus ==mindestens drei wesentliche Risiken== für das Unternehmen ab. 
- ==DMZ==: Online-Shop (eigenentwickelte PHP-Anwendung mit Warenkorb, Gutscheincodes, Produktbewertungen), Newsletter-Anmeldung.
	- Vertraulichkeit: Gaining access to client information
		- encryption
		- authentication
		- accress control
	- Integrität: Correct orders being sent to the correct address
		- Hashes
		- digital signature 
	- Verfügbarkeit: Online shop down → no orders
		- redundancy
		- monitoring
- ==Fabriksverkauf==: Kassensystem vor Ort, verbunden mit dem zentralen Warenwirtschaftssystem.
	- Vertraulichkeit: stealing money
		- passwords (access control)
		- which employees have which passwords (Tiers)
	- Integrität: access to backlog or manipulation of history to take out money without noticing
		- saving logs on a remote server
		- hashing every bill
		- passwords
	- Verfügbarkeit: registers needing to reboot/be fixed 
		- enough registers (Kassen) redundancy
- ==Home-Office==: Marketing- und Vertriebsmitarbeiter greifen über Client-VPN auf das interne Netz zu.
	- Vertraulichkeit: only trusted employees can see company data and ony the data the nee/are assigned to 
		- 2FA
		- encrypted traffic
		- only trusted company issued devices
	- Integrität: Outside factor changing company data
		- hashing every "significant" action before a change
		- backups to rollback any changes
		- needing an onsite connection at least once a week
	- Verfügbarkeit: Remote workers not being cut off
		- Dedicated IT-VPN hotline
		- Firewall to block susupicious activity/ddos
		- sufficient networking infrastructure
	- Non Repudiation: logging who changes what
		- account based connection (2FA)
		- non trust principle (having to log in for every service)
		- no personal account sharing (dedicated accounts for multiple access)
## 2 Risikobewertung und Risikomatrix 
Stellen Sie eine geeignete Methode zur Risikoberechnung vor (zum Beispiel Risiko gleich Eintrittswahrscheinlichkeit mal Schadensausmaß). Ordnen Sie mindestens ==drei Ihrer Risiken aus Frage 1 in einer Risikomatrix ein==. Wählen Sie anschließend die zwei größten Risiken aus und schlagen Sie jeweils eine passende ==Strategie der Risikobewältigung vor (Vermeidung, Verminderung, Transfer oder Akzeptanz). Begründen== Sie Ihre Wahl jeweils kurz. 
### Risikomatrix
![[risikomatrix.png]]
### Risiken
-  DMZ Verfügbarkeit: Hoch
	- Sicherheitsscans müssen kleine veränderungen in exestierenden Systemen erkennen können (Siehe Incident-Report)
- Fabriksverkauf Integrität: Niedrig
	- Alle vorhandenen Kassen/Laptops/Handys müssen davor registriert sein damit keiner die Gelbeträge oder Inventarstände mit nicht authorisierten Geräten verändern kann.
- Home-Office Non Repudiation: Mittel
	- logging changes for responsibility
### Risikobewältigung
Skimming - Verminderung:
- CSP + Allow-List, Script-Integrität (SRI), Self-Hosting Tracker
- Warum: Funktion wird gebraucht, Schaden ist eingetreten - nicht akzeptabel
SPS-Verminderung:
- Strikte VLAN-Trennung Produktions-/Büronetz + Firewall-Regeln
- Warum: SPS-Austausch (Vermeidung) zu teuer, Transfer schützt nur monetär
## 3 Rechtliche Vorgaben 
Bestimmen Sie mindestens ==drei rechtliche Vorgaben== oder Regulationen, die für Ihr Unternehmen aufgrund seiner ==Größe, Branche und verarbeiteten Daten== relevant sein könnten (zum Beispiel ==DSGVO, NIS-2, DORA, EU AI Act, CRA==, branchenspezifische Regularien). ==Begründen== Sie zu jeder genannten Vorgabe konkret anhand des Briefings, warum sie zutrifft. Prüfen Sie zusätzlich mindestens eine ==auf den ersten Blick naheliegende Regulation==, die bei ==genauerer Betrachtung tatsächlich nicht zutrifft==, und begründen Sie auch das. ITSI, IT-Sicherheit Seite 1 von 2 20.07.2026 5. Klasse / Wiederholung / Aufgabenblaetter 
### Zutreffend
- DSGVO: Kundendaten, Art. 9 Gesundheitsdaten (Allergien), Zeiterfassung
- NIS-2: Lebensmittelbranche - relevante/wichtige Einrichtung: Risikomanagement, Incident-Reporting, Schulungen
- PCI DSS: Checkout als Kartendaten-Eingabeoberfläche (SAQ A-EP) - Skimming-Fall zeigt Lücke
- E-Commerce/DSA[^1]: Newsletter & Tracking-Tool - Einwilligung, Transparenz 
### Nicht zutreffend
- DORA - gilt nur für Finanzsektor, Zahlungsdienstleister-Vertrag macht Süßwarenhersteller nicht zum Finanzinstitut
- EU AI Act - keine KI-Systeme im Einsatz
## 4 Risikobasiertes Sicherheitskonzept nach CIS Controls 
==Ordnen Sie Ihr Unternehmen== begründet einer Implementation Group der CIS Critical Security Controls zu (==IG1, IG2 oder IG3==). Stützen Sie diese Einstufung auf mindestens ==drei Kriterien aus dem Briefing==, etwa ==Unternehmensgröße und verfügbare IT-/Sicherheitsressourcen, Branche und regulatorisches Risikoprofil== (auch im Zusammenhang mit Ihrer Antwort zu Frage 3) sowie ==Art und Sensibilität der verarbeiteten Daten==.
### IG2[^2]
- "Es gibt keine eigene IT-Abteilung. Die IT wird von zwei internen Mitarbeitern sowie einem externen IT-Dienstleister betreut." 
- "Anmeldung an den Büro-Arbeitsplätzen existiert kein zentrales Verzeichnisdienst-System, jeder Rechner verwaltet eigene lokale Benutzerkonten"
- "Zugriff auf den Cloud- Speicher für Rezepturen, der über geteilte Zugangsdaten mehrerer Mitarbeiter erfolgt"
- ==Unternehmensgröße und verfügbare IT-/Sicherheitsressourcen==: 120 Mitarbeiter, 2 IT keine eigene IT-Abteilung -> klein
- ==Branche und regulatorisches Risikoprofil==: Lebensmittelherstellung (DSGVO, NIS-2) -> mittel
- ==Art und Sensibilität der verarbeiteten Daten==: Kunden/Mitarbeiterdaten (Gesundheitsdaten bzw. Allergien, Betriebsgeheimnisse, Zahlungen) -> hoch
Prüfen Sie anschließend anhand des Abschnitts ==„Bereits aktive Sicherheitsmaßnahmen”== im Briefing, ==welche CIS Controls in Ihrem Unternehmen bereits (auch nur teilweise)== umgesetzt sind, und benennen Sie zu mindestens ==zwei bereits vorhandenen Maßnahmen== den jeweils passenden CIS Control samt konkretem Safeguard. 
### Aktive CIS Controls 
- 10.1: Deploy and Maintain Anti-Malware Software
	- Antiviren-Software auf allen Büro-Arbeitsplätzen, zentral verwaltet durch den externen IT- Dienstleister.
- 11.2: Perform Automated Backups
	- Tägliches Backup des Warenwirtschaftssystems auf ein NAS am Standort Hallein
- 7.6: Perform Automated Vulnerability Scans of Externally-Exposed Enterprise Assets
	- Monatlicher automatisierter Schwachstellenscan des öffentlich erreichbaren Online-Shops durch den externen IT-Dienstleister.
Wählen Sie danach mindestens ==vier der von Ihnen in Frage 1 oder 2 identifizierten Risiken== aus und ordnen Sie ==jedem dieser Risiken einen passenden CIS Control== mit einem ==konkreten, noch fehlenden Safeguard== zu, der zur von Ihnen gewählten Implementation Group gehört. Stellen Sie ==diese Zuordnung für mindestens vier Punkte== explizit dar, in der Form ==“Risiko, CIS Control (Nummer und Name), fehlender Safeguard (Nummer und Name), Priorität”== und begründen Sie jeweils kurz, warum genau dieser Safeguard das genannte Risiko wirksam adressiert. 
### Fehlende Safetyguars
- DMZ Verfügbarkeit: Sicherheitsscans müssen kleine veränderungen in exestierenden Systemen erkennen können (Siehe Incident-Report)
	- Risiko: Hoch
	- CIS: 10 Malware Defenses
	- Fehlender Safeguard: 10.7: Use Behavior-Based Anti-Malware Software
	- Priorität: ASAP
- Fabriksverkauf Integrität: Alle vorhandenen Kassen/Laptops/Handys müssen davor registriert sein damit keiner die Gelbeträge oder Inventarstände mit nicht authorisierten Geräten verändern kann.
	- Risiko: Niedrig
	- CIS: 1 Inventory and Control of Enterprise Assets
	- Fehlender Safeguard: 1.2: Address Unauthorized Assets
	- Priorität: Niedrig
- Home-Office Vertraulichkeit: 8-char Passwort + MFA oder 14-char Passwort um unathorisierten Zugang von außen zu verweigern
	- Risiko: Hoch
	- CIS: 5 Account Managemen
	- Fehlender Safeguard: 5.2 Use Unique Passwords
	- Priorität: Hoch
- Home-Office Non Repudiation: logging changes for responsibility
	- Risiko: Mittel
	- CIS: 5 Account Managemen
	- Fehlender Safeguard: 5.6 Centralize Account Management
	- Priorität: Mittel
Fassen Sie abschließend zusammen, welche der ==von Ihnen gefundenen Lücken am dringendsten zu schließen sind==, damit Ihr Unternehmen die von Ihnen gewählte Implementation Group insgesamt tatsächlich vollständig erfüllt. 
### Most to Least Important Risiken
- DMZ Verfügbarkeit
- Home-Office Vertraulichkeit
- Fabriksverkauf Integrität
- Home-Office Non Repudiation
## 5 Zugriffs- und Berechtigungskonzept (AAA) 
Erklären Sie die Begriffe Authentication, Authorization und Accounting anhand mindestens einer konkreten Zugriffssituation aus Ihrem Unternehmen. ==Beurteilen Sie==, ob die im Briefing beschriebene Lösung eher eine ==zentrale oder dezentrale AAA-Umsetzung== ist, und nennen Sie ==mindestens zwei Indikatoren für Ihre Einschätzung==. Schlagen Sie für mindestens ==zwei unterschiedliche Zugriffsszenarien== (zum Beispiel Arbeitsplatz-Login, Fachanwendung, Fernzugriff im Home-Office) ==jeweils geeignete Authentifizierungsfaktoren vor== und ==begründen== Sie Ihre Wahl. Beschreiben Sie anhand eines ==konkreten Beispiels== aus Ihrem Unternehmen, ==welche Informationen== im Rahmen des Accounting ==protokolliert== werden sollten, und ==wofür diese Protokolle im Streitfall oder bei einem Sicherheitsvorfall== genutzt werden könnten.
### AAA
- Authentication: Identitätsnachweis – aktuell nur geteiltes Passwort → schwach
- Authorization: Rechte pro Rolle – aktuell alle alles → schwach
- Accounting: Wer wann was – mit geteilten Konten nicht zurückverfolgbar → kritische Lücke
### Dezentral, Indikatoren:
1. Kein zentraler Verzeichnisdienst (AD/LDAP) – nur lokale Konten
2. Cloud-Zugang als Einheitskonto ohne rollenbasierte Verwaltung
### Acccounting: Am Shop-Server -->
- Wer (Konto: deploy, www-data, root) · Wann (Zeitstempel) · Woher (IP) · Was (Aktion/Datei)
- Nutzen im Vorfall: Forensik, NIS-2-/DSGVO-Meldepflichten, Beweismittel (Non-Repudiation
## References
[^1]: “Digital Services Act (DSA) - Übersicht, Behörde, Verfahren, Designierungen,” _wko.at_, 2024. https://www.wko.at/internetrecht/digital-services-act-dsa (accessed Sept. 27, 2026).
[^2]: _Cisecurity.org_, 2024. https://learn.cisecurity.org/cis-controls-v8-1-guide-pdf (accessed Sept. 27, 2026).
[^3]: Moodle unterlagen