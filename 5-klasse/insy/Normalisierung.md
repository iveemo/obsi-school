---
tags:
  - insy
  - 5te_klasse
created: 2026-09-30T10:49:17+02:00
modified: 2026-09-30T11:15:44+02:00
---
Die strukturierte aufteilung der Daten auf mehrere logisch zusammenhöngende Tabellen
Ziele sind Merfchspeicherungen und Abhängigkeiten zu vermeiden
## 1. Normalform
Jede Tabellenzelle entrählt ==EINEN==,unteilbaren Wert
Es gibt keine listen oder Wiederholungsgruppen in einer Zeile
	=> Auslagern in andere Tabelle
Jeder Datensatz ist eindeutig identifizierbar
## 2. Normalform
Aufbauend 1. NF
Jedes NICHTSCHLÜSSELATTRIBUT trägt WWW WWW primärschlüssel ab
## 3.Normalform
Aufbauend 2. NF
Alle NICHTSCHLÜSSELATTRIBUTE durfen NICHT von einander abhängig sein, sie müssen ausschließlich vom Primärschlüssel ab
`# unique` `* not null` `o optional`