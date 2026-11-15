---
tags:
  - itsi
  - 5te_klasse
created: 2026-11-15T18:17:17+01:00
modified: 2026-11-15T20:18:55+01:00
---
**Themenbezug:** Penetration Testing, Social Engineering, Schwachstellenmanagement, Schwachstellenscanner, Patchmanagement
**Bearbeitung:** Ihr Unternehmen beauftragt einen externen Sicherheitsberater mit einem Penetration Test. Beantworten Sie die folgenden Fragen aus Sicht dieses Beraters beziehungsweise der internen ITLeitung.

## 1. Auftragsklärung und Scope
Nennen Sie mindestens vier Informationen oder Unterlagen, die der Berater von Ihrem Unternehmen vor Beginn der Überprüfung benötigt (zum Beispiel Scope, betroffene Systeme, Ansprechpartner, rechtliche Freigaben). Erklären Sie in wenigen Sätzen, wofür ein Rules-of-Engagement-Dokument dient.

- Ein Rules-of-Engagement-Dokument (RoE-Dokument) mit schriftlicher Freigabe durch die Geschäftsführung
- Den genauen Scope, also eingeschlossene und ausgeschlossene Systeme (z.B. Online-Shop und DMZ eingeschlossen, Produktions-VLAN mit den SPS-Steuerungen wegen Ausfallrisiko ausgeschlossen)
- Technische Angaben zu den betroffenen Systemen wie IP-Bereiche, die PHP-Anwendung des Shops und die MySQL-Datenbank
- Ansprechpartner (die beiden internen IT-Mitarbeiter und den externen IT-Dienstleister) sowie Eskalationswege bei Störungen

Das RoE-Dokument ist die rechtliche Grundlage des Tests. Es legt Scope, erlaubten Zeitraum sowie erlaubte und verbotene Techniken fest, wie z.B. das Verbieten von DoS-Techniken gegen den laufenden Shop. Ohne diese Vereinbarung wäre derselbe Test ein unbefugter Zugriff auf ein fremdes Computersystem.
## 2. Ablauf des Penetration Tests
Beschreiben Sie den typischen Ablauf eines Penetration Tests anhand von mindestens vier aufeinanderfolgenden Phasen, bezogen auf die im Briefing beschriebenen Systeme Ihres Unternehmens. Ihr Unternehmen möchte zusätzlich wissen, ob die Mitarbeiterinnen und Mitarbeiter ausreichend für Phishing sensibilisiert sind. Beschreiben Sie, wie ein Social-Engineering-Test in den Penetration Test eingebettet werden könnte, und welche ethischen und rechtlichen Aspekte dabei zu beachten sind.

1. Information Gathering:
	- Sammeln öffentlich verfügbarer Informationen über den Online-Shop, die eingesetzte PHP-Software und das E-Mail-Adressschema der Mitarbeitenden
2. Vulnerability Analysis:
	- gezielte Suche nach Schwachstellen in der selbst entwickelten PHP-Anwendung
		- z.B. SQL-Injection im Warenkorb oder in der Gutschein-Prüfung
		- z.B. Prüfung der Serverberechtigungen der Datei export_orders.sh mit den rwxrwxrwx-Rechten
3. Exploitation:
	- kontrolliertes Ausnutzen einer gefundenen Schwachstelle
		- ersten Zugang zum Shop-Server oder zur MySQL-Datenbank erhalten
4. Post-Exploitation und Reporting: Prüfung, ob von der DMZ aus das Büro-VLAN oder das nicht getrennte Produktions-VLAN erreichbar sind (laterale Bewegung), danach strukturierte Dokumentation aller Ergebnisse

## 3. Auswertung und Abgrenzung
Erklären Sie, wie der Berater das Ergebnis an Ihr Unternehmen sinnvoll übergeben sollte. Nennen Sie mindestens zwei Punkte, wodurch sich ein Penetration Test grundsätzlich von einem realen Angriff unterscheidet.

Eine simulierte Phishing-Mail an alle 120 Mitarbeitenden wird in die Angriffsphase eingeführt, da der bereits eingetroffene Vorfall über ein gefälschtes Login-Portal begann. Klickrate, eingegebene Zugangsdaten und Meldequote werden gemessen. Die Geschäftsführung und das Betriebsrat sind vorab zu verständigen und die Auswertung soll anonymisiert und DSGVO-konform ausgeführt werden.

- Schriftliche Zustimmung der Geschäftsführung und vorab begrenzter Scope
- Verzicht auf tatsächliche Schädigungen und ein festgelegter Zeitrahmen
- Ziel ist das Aufdecken und Melden von Schwachstellen, nicht der eigene Vorteil
## 4. Schwachstellenmanagement
Erklären Sie die Begriffe „==🟢Schwachstelle==” und „==🟢CVE==” anhand mindestens ==🟢eines konkreten Systems aus Ihrem Unternehmen==. Gibt es auch ==🟢europäische Alternativen oder Ergänzungen== zu US-amerikanischen ==🟢CVE-Datenbanken==, und warum könnte deren Existenz aus europäischer Sicht sinnvoll sein? 
Beschreiben Sie die Schritte eines ==🟢strukturierten Schwachstellenmanagementprozesses anhand von mindestens vier Schritten==, den Ihr ==🟢Unternehmen zusätzlich zu punktuellen Pentests== etablieren sollte. Erläutern Sie, wodurch sich dieser Prozess von einem ==🟢Penetration Test unterscheidet==.

**Vulnerability**, a flaw or weakness that can be exploited.
	Example: A web server with outdated php versions. (Frontend/Backend)

**CVE** is the official entry related to a specific vulnerability. This often includes how it is exploited, vulnerable software versions, etc.
	Example: CVE-2026-109618 and CVE-2026-109619 Both say they allow an unauthenticated attacker to execute their own code on a server running PHP, potentially taking control of it.

EU CVE-Datenbanken: European Vulnerability Database (EUVD)

4 Steps of a Structured Vulnerability Management Process in an Enterprise

- Detect
Automated scans search the network, endpoints, and applications for known and newly disclosed vulnerabilities.
- Assess
Each detected vulnerability receives a CVSS score, supplemented by context such as exploitability and affected systems.
- Remediate
Depending on the case, this is done through a patch, a configuration change, or a compensatory measure if no patch is available.
- Verify
A rescan and targeted spot checks confirm that the measure is effective and that no new vulnerabilities have been introduced.

Vulnerability management is a continuous, automated process for the ongoing monitoring and remediation of known security gaps. Penetration testing is a one-off, manual simulation of a cyberattack.
## 5. Schwachstellenscanner und Patchmanagement*
Nennen Sie beispielhaft mindestens ==🟢zwei unterschiedliche Arten von Schwachstellenscannern== und erläutern Sie, worin sie sich ==🟢unterscheiden==. 
Beschreiben Sie, wie solche Scanner in den ==🟢in Frage 4 beschriebenen Schwachstellenmanagementprozess integriert== werden könnten. Erklären Sie abschließend den ==🟢Zusammenhang zwischen Patchmanagement und Vulnerability Management==.

- Detect: finding vulnerabilities
- Asses: Aiding in scoring vulns
- Remediate: in some systems automatic updates/patches can be assigned
- Verify: Repeat of `Detect` to make sure the vulnerability has been managed