---
tags:
  - 4te_Klasse
  - cryptography
date: 2026-01-12T09:05:00
---
- seit 12/2023 : ID Austria -> digitale Ausweisplatform (Vollfunktion)
- techn. Umsetzung A-Trust
- Handy-Signatur ist rechtlich der eigenhändigen Unterschrift gleichgestellt
1) Aktivierung
- persöhnlich bei Registrierungsbehörde (Magistrat, LPD, Finanzamt)
	- Lichtbildausweis
- WWW
1) Signatur
	1) WWW
	2) A-Trust schickt Vergleichswert (SMS oder in App) und ggf. TAN (SMS)
		-> bestätigung, dass ich im Besitz WWW

2) pdf signieren -> a-trust.at/pdfsign
	- pdf hochladen
	- Mobiltelefonnmr. + Signaturpasswort eingelesen
	- auswählen: App (z.B. Digitales AWW) oder SMS/TAN
	- Vergleichswert prüfen. Handy vs PC?
	- ggf. TAN am PC eingeben, als A-Trust aufs Handy geschickt hat
	- auf "Signieren" klicken, Signiertes pdf herunterladen
3) signiertes pdf verifizieren -> a-trust.at/pdfverify
	- pdf hochladen auf a-trust.at
	- oder direkt im Adobe Reader (:vomit:)
	- (oder selbst machen, ssh verify)

## Sichere verwendung
- privater Signaturschlüssel wird durch A-Trust WWW+ gespeichert, <u>nicht</u> am Handy
- User authentiziert sich durch
	- Besitz (Handy)                       jeder mit Zugriff darauf kann im meinem Namen
	- Wissen (Signaturpasswort)   

## 2. Version
1) Basisfunktion: Handy Signatur
2) Vollfunktion: zusätzliche Funktionen, Z.B. Ausweis am Smartphone (digitaler Führerschein)
	- <u>kein</u> SMS/TAN (aus Sicherheitsgründen)
	- Smartphone -> erforderlich
		- App -> Fingerabdrücke / Gesichtserkennung
		- Token + PC
		- SignturWWW + kartenleser