---
tags:
  - 4te_Klasse
  - itsi
date: 2025-11-24T08:15:00
---
xyc

Wie Tief (phasen) soll eingegangen werden
	reicht information gathering
		Risiko/Schwachstellen analyse?
	asd
	asd

Beteiligte Personen
AG und AN (meist pen-test team)
verantwortungspersonen
Poe-Engagement
	Auftraggeber (CEO/IT-Verantwortliche)
	Auftragnehmer/Pentester (intern od. extern)
	Sicherheitsverantw. (Incidents, Datenschutz, Patches...)
	Rechtl. Stellen

Kommunikation
	Wen kontaktieren?
	Was machen bei kritischen Funden
	Status-Updates (was, wie oft, wer...)

Scope & Ziele
	Welche technischen Systeme (IPs, Domains, Anwendungen, ...) (Target/Non Target)
	Physische Systeme? (On-site, Social engineering, ...)
	Angriffstechniken (wie weit darf der Angriff gehen)
	Testdauer & Testzeiten (Wie lange geht d. Auftrag, Wann darf ich testen?)
	Nachweise & Berichterstattung (Wie viel muss ich dokumentieren, gibt es Verbesserungsvorschläge ...)

## Information gathering
2 Kategorien (und ein zwischenstand)

Wenig bis keine traces aber begrenzte Information die man finden kann

Bestimmte Ressourcen die eindeutig im Besitz meines Zieles sind prüfen.

| Passive                                       | Aktiv                                             | (made up) semi-passiv                                                      |
| --------------------------------------------- | ------------------------------------------------- | -------------------------------------------------------------------------- |
| ohne direkte Interaktionen mit Zielsystem<br> | direkte Interaktion mit Zielsys.                  | indirekte Interaktion über offentl. Sys. die mit Ziel im Verbindung Stehen |
| alle öffentlich zugängliche Informationen     | etwas das auf der Antwort einer Nachricht basiert |                                                                            |
| Bsp: google suche                             | Jemanden Fragen                                   |                                                                            |
passive -> OSINT (Open Source Intelligence)
	Google, Social-Media, externe Websiten, Presseartikel, Stellenausschreibungen, ....
	Metadaten (Zus. Info zu Dateien, zB Author, Geolocation, Versionen, .... )
	Leaks (Userdbs, Passwörter, .....)
	
