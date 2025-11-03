---
tags:
  - 4te_Klasse
  - itsi
  - cryptography
date: 2025-10-13T09:10:00
---
Reste bei Division durch 10:
![[Modulo- Rechnen 2025-10-13 09.30.11.excalidraw]]
asd

## Dilhe Hellmann
sad

```math
||{"id":1552336689407}||

p=11, g=3, a=4, b=3
A = g^{a} mod(p)
```
## Elbau<> Verschl.

```math
||{"id":112678256802}||

\text{Bsp. Plaintext-Angriff}

p=m \quad g=3
m=7 \text{klartext}
(B,c)=(5,8) \text{Chiffretext}
k=?

7 \times 8 = 56 == 1 (mod 11)
k=c \times m^{-1} = 8 \times 8 == 9 (mod 11)
```
## Chosen Cyphertext Angriff
Angreifer will (B,C) entschlüsseln wählt zufällig <> und berechnet $(B',c') = (g^{b'}, A^{b'})$ lässt sich $B \times B', c \times c'$ entschlüsseln
```math
||{"id":1366385246607}||
(B \times B', c \times c') = (g^{b} \times g^{b'}, A^{b} A^{b'})
```
asd
![[Modulo- Rechnen 2025-11-03 09.43.48.excalidraw]]

## RSA-Verschlüsselung
erstes und bis heute wichtigestes Verchlüsselungsverfahren (asym)

### 1. Schlüsselerzeugung
Bob wählt zufälig 