	Asset
	Alles, was einen Wirtschaftlichen Wert hat für ein Unternehmen (von Hardware bis Software, alles, was für uns Relevant ist) Computer, Software, Dienste (Services)
CIA – Basissicherheit
V
ertraulichkeit wahren 
	mit Zertifikaten, Verschlüsselung (Verkehr wird verschlüsselt mit TLS)

Warum nutzt nicht jeder/von jedem Gerät TLS 1.3?
	Weil nicht alle Geräte es unterstützen, Hardware, z.B. zu langsam dafür

Integrität mit Zertifikaten 
	Vor Veränderung schützen: Durch Hashes (Prüfsummen) schauen, dass die Software unverändert bleibt

Verfügbarkeit 
	CDN (Content Delivery Networks) man mietet verschiedene Cloudserver, Knoten aus verschiedenen Clouds, somit kann man sicherstellen, dass nichts komplett ausfällt, in Falle von einen Ausfall
	ginge auch alles Manuell mit Hardware

WAF 
	Web Applikation Firewall -> der Traffic auf dem Web-Server wird regelmäßig überwacht und so kann es abgesichert werden 

Wie vor DDos Angriffe schützen?
	Eine dynamische Firewall nutzen, die alle Zugänge immer überprüfen soll, dass ein Client für eine kurze Zeit blockiert wird, der komische Merkmale aufweist 

CMS (Content Management System) 
	typo 3, sehr viel Selbständig durchführen, leicht zugängliche Schnittstelle 
	Man verwendet spezielle CMS, weil sich bestimmte Personen damit auskennen (WordPress, typo 2 (hat unsere Schule))