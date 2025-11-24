-> Schutzziele Integrität, Authentizität, Verbindlichkeit

Bsp: RSA-Signatur (Textbook)
	Alice hat öffentliche Schlüssel (n,e) und
			privaten      --||--       ==d==
	Alice signiert Nachricht um $S = m^{d} \; mod\; n$ 
	Alice Schickt (m,s) an Bob
	Bob verifiziert Signatur: $s^e mod\;n = m \to \text{Signatur OK!} \neq m \to \text{Signatur asd Bob akzeptiert s nicht}$
	-
	asd Signatur einer langen Nachricht braucht weil Ressourcen
	Lösung: Hashwert 