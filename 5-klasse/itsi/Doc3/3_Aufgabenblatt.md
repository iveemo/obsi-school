---
tags:
  - itsi
  - 5te_klasse
created: 2026-11-15T18:17:17+01:00
modified: 2026-11-15T20:58:35+01:00
---
**Themenbezug:** Penetration Testing, Social Engineering, Schwachstellenmanagement, Schwachstellenscanner, Patchmanagement
**Bearbeitung:** Ihr Unternehmen beauftragt einen externen Sicherheitsberater mit einem Penetration Test. Beantworten Sie die folgenden Fragen aus Sicht dieses Beraters beziehungsweise der internen ITLeitung.

## 1. Auftragsklärung und Scope
### Nennen Sie mindestens vier Informationen oder Unterlagen, die der Berater von Ihrem Unternehmen vor Beginn der Überprüfung benötigt (zum Beispiel Scope, betroffene Systeme, Ansprechpartner, rechtliche Freigaben). 

- A Rules-of-Engagement document with written approval by the management
- The exact scope, meaning included and excluded systems (e.g. online shop and DMZ included, production VLAN with the PLC controllers excluded due to the risk of failure)
- Technical details about the affected systems such as IP ranges, the PHP application of the shop and the MySQL database
- Contact persons (the two internal IT employees and the external IT service provider) as well as escalation paths in case of disruptions

### Erklären Sie in wenigen Sätzen, wofür ein Rules-of-Engagement-Dokument dient.

The RoE document is the legal basis of the test. It defines the scope, the permitted time period as well as allowed and prohibited techniques, such as prohibiting DoS techniques against the running shop. Without this agreement, the same test would be unauthorized access to a foreign computer system.
## 2. Ablauf des Penetration Tests
### Beschreiben Sie den typischen Ablauf eines Penetration Tests anhand von mindestens vier aufeinanderfolgenden Phasen, bezogen auf die im Briefing beschriebenen Systeme Ihres Unternehmens. 

1. Information Gathering:
	- Collecting publicly available information about the online shop, the PHP software in use and the e-mail address scheme of the employees
2. Vulnerability Analysis:
    - targeted search for vulnerabilities in the self-developed PHP application
        - e.g. SQL injection in the shopping cart or in the voucher check
        - e.g. checking the server permissions of the file export_orders.sh with the rwxrwxrwx permissions
3. Exploitation:
    - controlled exploitation of a found vulnerability
        - obtaining initial access to the shop server or the MySQL database
4. Post-Exploitation and Reporting: checking whether the office VLAN or the not separated production VLAN can be reached from the DMZ (lateral movement), afterwards structured documentation of all results

### Ihr Unternehmen möchte zusätzlich wissen, ob die Mitarbeiterinnen und Mitarbeiter ausreichend für Phishing sensibilisiert sind. Beschreiben Sie, wie ein Social-Engineering-Test in den Penetration Test eingebettet werden könnte, und welche ethischen und rechtlichen Aspekte dabei zu beachten sind.

A simulated phishing e-mail to all 120 employees is introduced into the attack phase, since the incident that already occurred began via a fake login portal. Click rate, entered credentials and reporting rate are measured. The management and the works council are to be informed in advance and the evaluation is to be carried out anonymously and in compliance with the GDPR.
## 3. Auswertung und Abgrenzung
### Erklären Sie, wie der Berater das Ergebnis an Ihr Unternehmen sinnvoll übergeben sollte. 

Handover through a structured report:
- A management summary for the management (without technical details)
    - Which risks exist for the shop, customer data and production?
- Technical individual findings with risk classification and concrete recommendation
- In addition, a presentation in front of the management and the IT responsible persons

### Nennen Sie mindestens zwei Punkte, wodurch sich ein Penetration Test grundsätzlich von einem realen Angriff unterscheidet.

- Written consent of the management and a scope limited in advance
- Renunciation of actual damage and a defined time period
- The goal is to uncover and report vulnerabilities, not one's own advantage
## 4. Schwachstellenmanagement
### Erklären Sie die Begriffe „==🟢Schwachstelle==” und „==🟢CVE==” anhand mindestens ==🟢eines konkreten Systems aus Ihrem Unternehmen==. Gibt es auch ==🟢europäische Alternativen oder Ergänzungen== zu US-amerikanischen ==🟢CVE-Datenbanken==, und warum könnte deren Existenz aus europäischer Sicht sinnvoll sein? 
**Vulnerability**, a flaw or weakness that can be exploited.
	Example: A web server with outdated php versions. (Frontend/Backend)
**CVE**, the official entry related to a specific vulnerability. This often includes how it is exploited, vulnerable software versions, etc.
	Example: CVE-2026-109618 and CVE-2026-109619 Both say they allow an unauthenticated attacker to execute their own code on a server running PHP, potentially taking control of it.
**EU CVE-Datenbanken**, European Vulnerability Database (EUVD)

### Beschreiben Sie die Schritte eines ==🟢strukturierten Schwachstellenmanagementprozesses anhand von mindestens vier Schritten==, den Ihr ==🟢Unternehmen zusätzlich zu punktuellen Pentests== etablieren sollte.
4 Steps of a Structured Vulnerability Management Process in an Enterprise
- Detect
Automated scans search the network, endpoints, and applications for known and newly disclosed vulnerabilities.
- Assess
Each detected vulnerability receives a CVSS score, supplemented by context such as exploitability and affected systems.
- Remediate
Depending on the case, this is done through a patch, a configuration change, or a compensatory measure if no patch is available.
- Verify
A rescan and targeted spot checks confirm that the measure is effective and that no new vulnerabilities have been introduced.

### Erläutern Sie, wodurch sich dieser Prozess von einem ==🟢Penetration Test unterscheidet==.
Vulnerability management is a continuous, automated process for the ongoing monitoring and remediation of known security gaps. Penetration testing is a one-off, manual simulation of a cyberattack.
## 5. Schwachstellenscanner und Patchmanagement
### Nennen Sie beispielhaft mindestens ==🟢zwei unterschiedliche Arten von Schwachstellenscannern== und erläutern Sie, worin sie sich ==🟢unterscheiden==. 
- Network-based scanners (Greenbone/OpenVAS, Nessus)
Checks open ports and services for known vulnerabilities from outside the network.
- Agent-based scanners
A small agent directly on the target system, for internal configuration details that would not be visible from the outside.
- Web application scanners (OWASP ZAP, Burp Suite)
Checks Web applications, such as SQL injection or XSS and actively test the application via HTTP requests.
- Cloud configuration scanners (Prowler, ScoutSuite)
Checks cloud services for misconfigurations e.g. open storage shares, overly broad access rights.

### Beschreiben Sie, wie solche Scanner in den ==🟢in Frage 4 beschriebenen Schwachstellenmanagementprozess integriert== werden könnten.
- Detect: finding vulnerabilities
- Asses: Aiding in scoring vulns
- Remediate: in some systems automatic updates/patches can be assigned
- Verify: Repeat of `Detect` to make sure the vulnerability has been managed

###  Erklären Sie abschließend den ==🟢Zusammenhang zwischen Patchmanagement und Vulnerability Management==.
Patch management is part of the vulnerability management cycle. Implementing updates, including testing and rollout planning. This means it is dependant on the overarching vulnerability management process and without it, lacks the necessary information to know what patches to apply where.