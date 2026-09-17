---
tags:
  - nwt
  - 5te_klasse
created: 2026-09-11T10:30:16+02:00
modified: 2026-09-14T10:42:59+02:00
---
## OSPF-Kosten
[[OSPF-18.09.2025#Kostenmetrik OSPF]]
```math
||{"id":815412218705}||
Kosten = \cfrac{Ref. BB}{\sum Pfad. BB}
```
`Referenz Bandbreite`: Größte im Netzwerk
`Pfad Bandbreite`: entlang des Pfades wird summiert

Satische/Default routen kosten = 0


Database:
Adjacency DB	    Neighbor Table

Link-state DB	    Topology Table

Forwarding DB	Routing Table
	Normale routing Tabelle 
	exists on every router
