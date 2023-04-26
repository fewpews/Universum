# String-Matching mit Rabin und Karp
- arbeitet mit *Hashfunktion*
	- jedem Pattern der Länge $m$ ein *Hashwert* 

## Lösung
```
H := Hashwert von P;  
FOR s:=0 TO n−m DO  
	IF (Hashwert von T [s+1...s+m]) = H THEN Test(s) ENDIF;
```
- `Test()` vergleicht $T[s+i]$ mit $P[i]$ für alle $i$ von $1$ bis $m$
### Hashwert
- Hashwert für jedes $m$-buchstabige Pattern über Alphabet $\Sigma$
	- Pattern als $m$-stellige Zahl mit Basis $|\Sigma|$
		- Berechnung dieser Zahl modulo geeigneter natürlicher Zahl $q$
- Entscheidend ist sher effiziente Berechnung durch sukzessive Adaption
#### Beispiel
- $m=4, \quad |\Sigma|=3, \quad q=11$
- Text enthält Teilwort $a_5a_4a_3a_2a_1$ 
- Hashwert erst $27a_5 + 9a_4 + 3a_3 + a_2 \: mod \: 11$
- Im nächsten Schritt soll $27a_4 + 9a_3 + 3a_2 + a_1 \: mod \: 11$ 
	- subtrahieren $27a_5$ (bzw. $5a_5$ wegen $mod 11$)
	- multiplizieren mit $3 \: (|\Sigma|)$
	- addieren $a_1$
	- Aufwand für Anpassung unabhängig Text-/Patternlänge -> konstant
#### Pseudo-Code
```
u := |Σ|m−1 mod q;  
p := 0; t := 0;                                              /* Initiale */  

FOR i := 1 TO m DO                                 /* Hashwertberechnung */  
	p := (|Σ| · p + P[i]) mod q;  
	t := (|Σ| · t + T[i]) mod q  
ENDFOR; 

/* Hauptteil */
FOR s := 0 TO n−m DO                                      
	IF p = t THEN test(s) ENDIF;                      /* ggfs. Ausgabe s */  
	IF s < n−m THEN  
		t := ((t − T[s+1] · u) · |Σ| + T[s+m+1]) mod q  
	ENDIF  
ENDFOR
```

## Analyse
- Anzahl Hashwertberechnungen in beiden Teilen zusammen -> $m+n$ 
	- **Aufwand:** $O(m+n)$ 
- Für jede *Kollision* -> jedes $s$ für das $p=t$ erfüllt
	- ein Vergleich mit Pattern $P$ 
	- $O(m)$ Schritte
- **Gesamtrechenzeit** bei $k$ Kollisionen
	- $O(m+n) + k \cdot O(m)$

#### Average-Case
- lineare Gesamtrechenzeit bei realistischen Annahme
	- $q>m$
	- Hashwerte zufällig verteilt im Bereich $0,...,q-1$
#### Worst-Case
- Theoretisch im Bereich $\Theta(m \cdot n)$

## Beispiel
- Pattern `adac` 
- Hashwert `adac` $0 \cdot 64 + 3 \cdot 16 + 0 \cdot 4 + 2 \cdot 1 \: mod \: =50 \: mod \: 11= 6$

![[StringMatching_RabinKarp.png|500]]
- Bei den Matches muss getestet werden