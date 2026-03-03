**Prover A**
- wählt zwei große Primzahlen p und q
- berechnet n = pq (modulus)
- wählt s < n und berechnet $v = s^2 \mod n$ 

A kennt Quadratzahl mod n

 wählt zufällig r < n (ggf (n,r) =1)
 berechnet $x = r^2 \mod n$ ---- Commitment ----> wählt zufällig $b {0,1}$
                    <---- Challange b ----
                    