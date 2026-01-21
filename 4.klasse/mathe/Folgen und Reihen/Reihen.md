---
tags:
  - 4te_Klasse
  - m
date: 2026-01-14T10:05:00
---
Bei einer Reihe werden die Glieder nacheinander aufsummiert
$$\begin{aligned}
\text{n-te Teilsumme:} &\quad S_{n}=a_{1}+a_{2}+\dots + a_{n} = \sum_{k=1}^n a_{k}\\
\text{Bsp:} &\qquad a_{n}=\dfrac{1}{2^n} \qquad n>0 \\
&S_{5} = \dfrac{1}{2^1}+ \dfrac{1}{2^1}+ \frac{1}{2^2}+ \dfrac{1}{2^3}+ \dfrac{1}{2^4}+\dfrac{1}{2^5} \\
&\lim_{ n \to \infty } \cfrac{1}{2^n} = 0
\sum_{k=0}^{\infty} \cfrac{1}{2^k} = 1 + \cfrac{1}{2}+\cfrac{1}{4}+\dots=2
\end{aligned}$$
Konvergente Reihe falls $|a|<1$
divergent falls $|a| \geq 1$
$$\begin{aligned} \text{5.5a)}
&\sum_{n=0}^\infty \cfrac{1}{4^n} = \sum_{n=0}^\infty \left( \cfrac{1}{4} \right)^n = \cfrac{1}{1-\cfrac{1}{4}}=\cfrac{1}{\cfrac{3}{4}}=\cfrac{4}{3} \qquad \boxed{\sum_{n=0}^\infty b_{1} \; q^k =\cfrac{b_{1}}{1-q}}\\

\text{b)} &\sum_{n=0}^\infty \cfrac{1}{3^{2n}} = \sum_{n=0}^\infty = \left( \cfrac{1}{q} \right)^n = \cfrac{1}{1-\cfrac{1}{q}}=\cfrac{1}{\cfrac{8}{9}} = \cfrac{9}{8}\\

\text{c)} &\sum_{k=0}^\infty \cfrac{2}{3^{k}} = 2 \cdot \left( \cfrac{1}{3} \right)^k =\cfrac{2}{1-\cfrac{1}{3}}=\cfrac{2}{\cfrac{2}{3}} = 3\\

\text{d)} &\sum_{m=0}^\infty 3 \cdot 10^{-m} =  3 \cdot \left( \cfrac{1}{10} \right)^{m} = \cfrac{3}{1-\cfrac{1}{10}}=\cfrac{3}{\cfrac{9}{10}} = \cfrac{10}{8}
\end{aligned}$$
Konvergent = es ==hat einen== Grenzwert
Divergent = ==keinen== Grenzwert

## Alternierende Reihe
$c_{1} + c_{2} - c_{3} + c_{4} -c_{5} + \dots\ \to$ alternierende Reihe, wenn aufeinanderfolgende Glieder wechselnde Vorzeichen haben.

## Leibnitz-Kriterium
Die alternierende Reihe $c_{1}-c_{2} + \dots$ (alle a > 0) konvergiert, wenn die Folge $(c_{1},c_{2},\dots)$ eine monotone Nullfolge ist.
$$\begin{aligned}
\text{5.11)b)} \quad
&\sum_{n=0}^{\infty}(-1)^{n} \cfrac{1}{n!} \\
&c_{0}-c_{1}+c_{2}-c_{3}+ \dots \ = 1-1+\cfrac{1}{2}-\cfrac{1}{6}+\cfrac{1}{24}-\dots\\
&c_{n} = \cfrac{1}{n!} \qquad c_{n+1} = \cfrac{1}{(n+1)!} \qquad c_{n+1} \leq c_{1} \implies \lim_{ n \to \infty } \ln = 0 \\
\\
\text{5.11)c)} \quad
&\sum_{n=0}^{\infty}\left( - \frac{1}{3} \right)^{n} = 1- \cfrac{1}{3} + \cfrac{1}{9} - \cfrac{1}{27} + \dots \\
&c_{n} \geq c_{n+1} \implies \lim_{ n \to \infty } = 0 \implies \text{konvergiert} 
\end{aligned}
$$
