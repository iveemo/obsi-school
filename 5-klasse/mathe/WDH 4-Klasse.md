---
tags:
  - m
  - 5te_klasse
created: 2026-09-21T23:30:30+02:00
modified: 2026-09-22T04:54:14+02:00
---
## Aufgabe 1: Prosit Neujahr
### 1 a) 
Besitzt ein Körper zum Zeitpunkt $t$ die Temperatur T(t), so besagt das Newtonsche Abkühlungsgesetz: 
$$\cfrac{dT}{dt} = k \cdot (T(t)-T_{U})$$
Dabei ist $k$ eine Konstante und $T_{U}$ die Umgebungstemperatur.
1) Interpretieren Sie diese Differentialgleichung, durch Ergänzung der Lücken: Die ==Änderungsrate== $\cfrac{dT}{dt}$ ist ==proportional== zur Differenz der ==aktuellen Temperatur== und der Umgebungstemperatur.
2) Babsi stellt an Silvester um 21 Uhr eine 22 °C warme Flasche Sekt auf den Balkon. Draußen herrscht eine konstante Temperatur von 5 °C. Die Temperatur der  Sektflasche zum Zeitpunkt $t$ beträgt $T(t)$. Dabei sei $t$ die nach 21 Uhr vergangene Zeit in Minuten. Um 21:30 Uhr hat die Sektflasche eine Temperatur von 17,594 °C. Berechnen Sie mit diesen Vorgaben die spezielle Lösung der Differentialgleichung. 
$$\begin{aligned}
22 = 5+C \cdot e^{k \cdot 0} = C = 17 \\
17.594 = 5+17 \cdot e^{k \cdot 0} \quad |-5 \; :17 \\
\cfrac{12.594}{17}=e^{30k} = 0.74082 \approx e^{30k} \quad \ln \\
\ln(0.74082) = 30k \\
-0.3000 \approx 30k \quad |:30 \\
\cfrac{-0.3000}{30} = k = -0.01 \\
T(t) = 5 + 17 \cdot e^{-0.01 \cdot t}
\end{aligned}$$
3) Sebi stellt um 23 Uhr eine Bierflasche in den Kühlschrank. Der Abkühlprozess dieser Bierflasche kann durch die Funktion $T(t) = 15 \cdot e^{-0.02t}+3$ modelliert werden (Zeit  in Minuten ab 23 Uhr). Berechnen Sie, welche Temperatur die Bierflasche um Mitternacht haben wird.
$$\begin{aligned}
T(60) =& 15 \cdot e^{0.02 \cdot 60}+3 \\
&15 \cdot e^{-1.2}+3 \\
&15 \cdot 0.30119 +3 = 7.5179°C \\
\end{aligned}$$
A: Um Mitternach hat die Flasche Bier 7.52°C
### 1 b) 
Sämtliche Lebensmittelerzeugnisse unterliegen strengen Gesundheitsrichtlinien. Daher müssen sie regelmäßig auf etwaige Verunreinigungen überprüft werden. Eine solche Probe wurde entnommen, ins Labor geschickt und eine Bakterienkultur angelegt. In dieser Bakterienkultur ist die zeitliche Änderung der Bakterienanzahl $N$ proportional zur der Anzahl der vorhandenen Bakterien. Der Proportionalitätsfaktor beträgt $k = 0.2 min^{-1}$.  
1) Weshalb nimmt die Bakterienanzahl zu (und nicht ab)? Begründen Sie!
Es nimmt zu weil $k$ positiv ist, wäre es negativ würde es abnehmen 
2) Bestimmen Sie die Differentialgleichung für die Anzahl der Bakterien bezogen auf die Zeit (in Minuten) unter Angabe aller Rechenschritte.
$$\cfrac{dN}{dt} = 0.2 \cdot N$$
3) Ermitteln Sie die allgemeine Lösung der Differentialgleichung.
$$\begin{aligned}
\cfrac{dN}{dt}=&0.2 \cdot N  \\
\cfrac{1}{N}dN=&0.2 \cdot dt \\
\int \cfrac{1}{N} \, dN =& \int 0.2 \, dt \\
\ln |N| =& 0.2 t + C  \\
\\
N(t) =& e^{0.2t+C} \\
N(t) =& N_{0} \cdot e^{0.2t}
\end{aligned}
\begin{aligned}
\\
& \quad |:N \cdot dt \\
\\
\\
\\
\\
\\
& \quad |\;e
\\
\\
\\
\\
\end{aligned}
$$
### 1 c) 
Nach 10 Minuten wurden 70 Bakterien gezählt. 
1) Stellen Sie mit Hilfe der gegebenen Bedingungen die Funktion auf, die die Anzahl der vorhandenen Bakterien $N$ nach $t$ Minuten bestimmt.

$$
\begin{aligned}
70=&N_{0} \cdot e^{0.2 \cdot 10} \\
70=&N_{0} \cdot e^{2} \quad \\
→ \cfrac{70}{e^{2}} =& N_{0} \approx 9.47 \\
→ N(t) =& 9.47 \cdot e^{0.2t}
\end{aligned}
\begin{aligned}
\\
& | :e^{2} 
\\
\\
\\
\\
\end{aligned}
$$
1) Berechnen Sie, wie viele Bakterien zu Beginn und nach 30 Minuten vorhanden sind.
$$
\begin{aligned}
N(0) &= 9.47 \cdot e^0 = 9.47\\
N(30) &= 9.47 \cdot e^{0.2 \cdot 30} = 9.47 \cdot e^6 \approx 3820.47
\end{aligned}
$$
## Aufgabe 2: Boy’s Aquarium
Seit den neuesten Buchverfilmungen _Heated Rivalry_ (Rachel Reid) und _Off Campus_ (Elle Kennedy), erlebt Hockey einen riesigen Aufschwung in Besucherzahlen.
### 2 a) 
In der kanadischen Eishockeyliga werden die Ergebnisse aller Spiele statistisch ausgewertet. In der Saison 2012/13 wurde über einen bestimmten Zeitraum erfasst, in wie vielen Spielen jeweils eine bestimmte Anzahl an Toren erzielt wurde. Das nachstehende Säulendiagramm stellt das Ergebnis dieser Auswertung dar.
![[Spiele-Tore.png|right|390]]
1) Bestimmen Sie den Median der Datenliste, die diesem Säulendiagramm zu Grund liegt.
Mittleren Datensatz: 6
2) Berechnen Sie das arithmetische Mittel.
$$
\overline{x} = \cfrac{3 \cdot 2 + 4 \cdot 2 + 5 \cdot 6 + 6 \cdot 3 + 7 \cdot 8 + 9 \cdot 2}{23} = 5.913
$$
3) Erstellen Sie ein Boxplot, das diesen Sachverhalt darstellt und markiere alle wichtigen Kenngrößen.
![[boxplot.png| center | 100%|642]]
### 2 b)
Der Puck, eine Hartgummischeibe, ist genau 1 Zoll (2,54 cm ± 1mm) hoch und hat einen Durchmesser von 3 Zoll (7,62 cm ± 1mm). Das Gewicht darf zwischen 5,5 und 6 Unzen (entspricht 156 bis 170 Gramm) variieren.
1) Berechnen Sie die Oberfläche des Pucks und bestimmen Sie das totale Differential dP.

$$
\begin{aligned}
&P(d,h) = 2 \cdot \cfrac{d^2 \cdot \pi}{t}+d \cdot \pi \cdot h =\cfrac{\pi}{2}d^2 + \pi \cdot d \cdot h \\
&P = \frac{\pi}{2}(7.62)^2 + \pi \cdot 7.62 cdit 2.54 = 91.207 + 60.804 = 152.01cm^2\\
&\text{1. Ableitung} \quad 2 \cdot \frac{\pi}{2}d + \cdot h = \pi d+ \pi h= \pi (d+h)\\
&\text{2. Ableitung} \quad h = \pi d \qquad dP = \pi(d+h) \cdot dd+ \pi d \cdot \pi h
\end{aligned}
$$
2) Berechnen Sie den maximalen absoluten Fehler der Oberfläche bei der Herstellung eines Pucks.

$$
\begin{aligned}
&\Delta P \approx |\pi (d+h)| \cdot \Delta d+ |\pi d| \cdot \Delta h \\
&\Delta P \approx \pi (7.62+2.54) \cdot 0.1+ \pi 7.62 \cdot 0.1 \\
&\Delta P \approx \pi (10.16) \cdot 0.1+ \pi 7.62 \cdot 0.1 \\
\end{aligned}
\begin{aligned}
&\quad \Delta \approx 3.192+2.394=5.586cm^2 \\
&\quad \text{Der maximale absolute Fehler} \\
&\quad \text{beträgt ca 5.586}m^2
\end{aligned}
$$
3) Berechnen Sie den relativen Maximalfehler in Prozent.

$$
\begin{aligned}
\frac{\Delta P}{P} \quad &\frac{5.586}{152.01} \approx 0.0367 \\
\\
&3.67\%
\end{aligned}
$$
## Aufgabe 3: Aprés-Ski
Es ist nicht mehr lange bis zum Start der Skisaison und wie wir alle wissen, sind gute (und günstige) Unterkünfte und guter Empfang in den Bergen rar.
### 3 a)
Daher vergleichen einige Ski- und Snowboardlehrerinnen verschiedene Unterkünfte für die Skisaison. Die 1. Woche in einer Ferienwohnung kostet 800 Euro. Jede weitere Woche kostet um 10% weniger als die vorangegangene Woche. Die Kosten der n-ten Woche können durch eine Folge beschrieben werden.
1) Geben Sie an, ob es sich dabei um eine arithmetische oder eine geometrische Folge handelt und begründen Sie die Entscheidung.
Es ist eine geometrische Fkt. weil bei einer Reduktion von 10% werden die Kosten jede Woche mit Konstanten $q = 0,9$ multipliziert
2) Erstellen Sie ein explizites Bildungsgesetz für diese Folge.
$$a_{n}=800 \cdot 0.9^{n-1}$$
3) Berechnen Sie, wie lange sie bleiben müssten, damit die Unterkunft unter 100€ pro Woche kostet.
$$
\begin{aligned}
800 \cdot 0.9^{n-1} <\;& 100 \\
0.9^{n-1} < \frac{100}{800} = 0.9^{n-1} <\;& 0,125 \\
n-1 > \cfrac{\ln(0.125)}{\ln(0.9)} =\;& 19.73 \\
n-1 >\;& 19.73 \\
n-1 >\;& 20.73 \\
\end{aligned}
\begin{aligned}
&\quad | :800 \\
&\quad |\ln \\
\\
&\quad |\ln(0.9)\\
\\
&\quad | +1 \\
\\
\end{aligned}
$$
A: Man müsste mindestens 21 Wochen bleiben damit die Unterkunft unter 100€ pro Woche kostet.
### 3 b)
Durch die geografischen Gegebenheiten in den Bergen, haben viele Menschen nur schlechten oder gar keinen Empfang. In der Nachrichtentechnik wird das Abklingverhalten eines gefilterten Signals durch eine unendliche Reihe beschrieben. Für die mathematische Analyse eines bestimmten Verstärkers wird die folgende Funktion als Potenzreihe angesetzt:
$$f(n)= \sum^{\infty}_{n=1} \cfrac{3^n \cdot (x-2)^n}{n \cdot 5^n}$$
1) Schreiben Sie die ersten drei Glieder (n = 1, 2, 3) dieser Reihe explizit auf und vereinfachen Sie die Brüche so weit wie möglich.
$$
\begin{aligned}
&\cfrac{3^1 \cdot (x-2)^1}{1 \cdot 5^1}\\
&\cfrac{3 \cdot (x-2)}{5} \\
\end{aligned}
\begin{aligned}
\quad &\cfrac{3^2 \cdot (x-2)^2}{2 \cdot 5^2}\\
&\cfrac{9(x^2-4x+4)}{50}
\end{aligned}
\begin{aligned}
\quad&\cfrac{3^3 \cdot (x-2)^3}{3 \cdot 5^3} \\
&\cfrac{27x^3-162x^2+324x-216}{375} \\
&\cfrac{\cancel{3} \cdot (9x^3-54x^2+108x-72)}{\cancel{375}} \\
&\cfrac{9x^3-54x^2+108x-72}{125}
\end{aligned}
$$
  2) Untersuchen Sie die Reihe mithilfe des Quotientenkriteriums.

$$
\begin{aligned}
|\frac{an+1}{an}| =& \cfrac{3^{n+1}(x-2)^{n+1}}{(n+1)5^{n+1}} \cdot \cfrac{n \cdot 5^n}{3^n (x-2)^n} \\
&\cfrac{3 \cdot (x-2)}{5} \cdot \cfrac{n}{n+1} \\
\lim_{ n \to \infty } |\cfrac{3 \cdot (x-2)}{5} &\cdot \cfrac{n}{n+1}| = \cfrac{3 \cdot (x-2)}{5} \cdot 1 
\end{aligned}
$$
### 3) Bonusaufgabe:
Bestimmen Sie aus dem Ergebnis den Konvergenzradius R dieser Potenzreihe und geben Sie das oLene Konvergenzintervall für x an. (Die Ränder müssen nicht untersucht werden).

$$
\begin{aligned}
|\cfrac{3 \cdot (x-2)}{5}| < 1 &⇒ |x-2| < \frac{5}{3} = 12\\
2 - \frac{5}{3} < x < 2 + &\frac{5}{3} = \frac{1}{3} < x < \frac{11}{3}\\
&\left( \cfrac{1}{3}, \cfrac{11}{3} \right)
\end{aligned}
$$