# String-Matching mit Brute-Force
- Prüfe für alle $s \in \{0,...,n-m\}$ ob $s$ Lösung

## Pseudo-Code
```
FOR s := 0 TO n−m DO  
	found := TRUE;  
	FOR i:=1 TO m DO  
		IF T[s+i] != P[i] THEN found:=FALSE ENDIF  
	ENDFOR  
	IF found THEN OUTPUT(s) ENDIF  
ENDFOR
```
## Analyse
- **Zeitkomplexität:** $\Theta(m \cdot n)$