# 1. Auftragsklärung und Scope

###### Nennen Sie mindestens vier Informationen oder Unterlagen, die der Berater von Ihrem Unternehmen vor Beginn der Überprüfung benötigt (zum Beispiel Scope, betroffene Systeme, Ansprechpartner, rechtliche Freigaben).

- A Rules-of-Engagement document with written approval by the management
- The exact scope, meaning included and excluded systems (e.g. online shop and DMZ included, production VLAN with the PLC controllers excluded due to the risk of failure)
- Technical details about the affected systems such as IP ranges, the PHP application of the shop and the MySQL database
- Contact persons (the two internal IT employees and the external IT service provider) as well as escalation paths in case of disruptions
###### Erklären Sie in wenigen Sätzen, wofür ein Rules-of-Engagement-Dokument dient.

The RoE document is the legal basis of the test. It defines the scope, the permitted time period as well as allowed and prohibited techniques, such as prohibiting DoS techniques against the running shop. Without this agreement, the same test would be unauthorized access to a foreign computer system.
# 2. Ablauf des Penetration Tests

###### Beschreiben Sie den typischen Ablauf eines Penetration Tests anhand von mindestens vier aufeinanderfolgenden Phasen, bezogen auf die im Briefing beschriebenen Systeme Ihres Unternehmens.

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
###### Ihr Unternehmen möchte zusätzlich wissen, ob die Mitarbeiterinnen und Mitarbeiter ausreichend für Phishing sensibilisiert sind. Beschreiben Sie, wie ein Social-Engineering-Test in den Penetration Test eingebettet werden könnte, und welche ethischen und rechtlichen Aspekte dabei zu beachten sind.

A simulated phishing e-mail to all 120 employees is introduced into the attack phase, since the incident that already occurred began via a fake login portal. Click rate, entered credentials and reporting rate are measured. The management and the works council are to be informed in advance and the evaluation is to be carried out anonymously and in compliance with the GDPR.
# 3. Auswertung und Abgrenzung

###### Erklären Sie, wie der Berater das Ergebnis an Ihr Unternehmen sinnvoll übergeben sollte.

Handover through a structured report:
- A management summary for the management (without technical details)
    - Which risks exist for the shop, customer data and production?
- Technical individual findings with risk classification and concrete recommendation
- In addition, a presentation in front of the management and the IT responsible persons
###### Nennen Sie mindestens zwei Punkte, wodurch sich ein Penetration Test grundsätzlich von einem realen Angriff unterscheidet.

- Written consent of the management and a scope limited in advance
- Renunciation of actual damage and a defined time period
- The goal is to uncover and report vulnerabilities, not one's own advantage
# 4. Schwachstellenmanagement

###### Erklären Sie die Begriffe „Schwachstelle” und „CVE” anhand mindestens eines konkreten Systems aus Ihrem Unternehmen. 

###### Gibt es auch europäische Alternativen oder Ergänzungen zu US-amerikanischen CVE-Datenbanken, und warum könnte deren Existenz aus europäischer Sicht sinnvoll sein? 

###### Beschreiben Sie die Schritte eines strukturierten Schwachstellenmanagementprozesses anhand von mindestens vier Schritten, den Ihr Unternehmen zusätzlich zu punktuellen Pentests etablieren sollte. 

###### Erläutern Sie, wodurch sich dieser Prozess von einem Penetration Test unterscheidet.
# 5. Schwachstellenscanner und Patchmanagement

###### Nennen Sie beispielhaft mindestens zwei unterschiedliche Arten von Schwachstellenscannern und erläutern Sie, worin sie sich unterscheiden. 

###### Beschreiben Sie, wie solche Scanner in den in Frage 4 beschriebenen Schwachstellenmanagementprozess integriert werden könnten. 

###### Erklären Sie abschließend den Zusammenhang zwischen Patchmanagement und Vulnerability Management.