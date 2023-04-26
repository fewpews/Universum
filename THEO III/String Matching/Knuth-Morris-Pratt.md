# String-Matching mit Knuth-Morris-Pratt
- mit eindimensionaler Verschiebetabelle
	- in linearer Zeit in Patternlänge erstellt
	- -> Algorithmus in Linearzeit

## Definition Tabelle
- $Shft[q] = max\{k<q \mid P[1...k] = P[q-k+1...q]\}$ für alle $i \in \{1,...,m\}$
	- Mismatch an $(q+1)$-ten Stelle des Pattern
	- nächste Suche bei $q - Shft[q]$ Stellen weiter hinten
		- ersten $Shft[q]$ Buchstaben nicht nochmal prüfen
### Berechnung Verschiebetabelle
```
BerechneTabelle():

Shft[1] := 0; k := 0;  
FOR q:=2 TO m DO  
	WHILE (k > 0) ∧ (P[k+1] != P[q]) DO  
		k := Shft[k]  
	ENDWHILE;  
	IF P[k+1] = P[q] THEN k:=k+1 ENDIF;  
	Shft[q] := k;  
ENDFOR
```

## Algorithmus
```
BerechneTabelle(); q:=0;
FOR i:=1 TO n DO
	WHILE (q>0) ∧ (P[q+1] != T([i]) DO  
		q := Shft[q]  
	ENDWHILE;  
	IF P[q+1] = T[i] THEN q:=q+1 ENDIF;  
	IF q = m THEN OUTP(i − m); q := Shft[q] ENDIF  
ENDFOR
```
### Analyse
- WHILE-Schleife wird nur $O(n)$ mal ausgeführt
	- **Gesamtlaufzeit:** $O(n)$

## Beispiel: ``ananas``
- Shft-Werte aus Definition abgelesen: 001230
### BerechneTabelle
![[KMPBeispiel1.png]]
## Beispiel: ``adacadac``
### BerechneTabelle
![[KMPBeispiel2.png|500]]
- **Shift-Werte:** 00101234