---
tags:
  - 4te_Klasse
  - sew
date: 2025-09-12T13:45:00
---

![[Threads 2025-09-12 14.02.52.excalidraw]]
1) was ist ein Thread
	asd
2) wie erstellt man einen Thread 
```java
class MeinThread extends Thread
```
3) welche Methode wird überschrieben
```java 
run()
```
4) Thread erzeugen
```java
MeinThread t1 = new MeinThread();
```
	-> Zustand Bereit 
5) Starten
```java
t1.start();
```

```java
//wie erstellt man einen Thread 
class MeinThread extends Thread
//welche Methode wird überschrieben
run()
//Thread erzeugen
MeinThread t1 = new MeinThread();
//Starten
t1.start();
//falsches starten
t1.run(); //läuft nicht als Thread nicht Parallel!!
/*wann ist ein Thread beendet
1) run() beendet
2) Programm Beendet
3) interrupt() //-s-t-o-p-
*/
//join()
// ein Thread wartet bis der andere Thread beendet ist
```
2\. Möglichkeit
class MeinThread extends BB implements Rumble