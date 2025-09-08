---
tags:
  - sew
  - 4te_Klasse
date: 2025-09-04T15:30:00
---
## Wiederholung
- Rekurionen Methode ruft sich selber auf
- Heration Schleifen

## Beurteilung
1 Test pro Semester
	- 2-3 SMÜ's
- Programmier Projekte
- Mitarbeit

## 1. Sem
- wiederholung
- nebenläufige Programmierng } Thread-Programming
	- (parallele Programmierung)
- Beispiel-Projekte -> Grafikprogrammierung

## 2. Sem
- Netzwerkprogrammierung
- TCP Client-Server Anwendungen
- UDP Client-Server Anwendungen

Fakultät
5! = 5 * 4 * 3 * 2 * 1
5! = 5 * 4!
	n * (n-1)
n! = n * (n-1)

```
int faku(int n)
{
	if (n==1)
		return 1;
	else
		return n * faku(n-1)
}
```
![[4kl-sew 2025-09-04 16.11.22.excalidraw|100%]]