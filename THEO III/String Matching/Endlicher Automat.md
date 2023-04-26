# String-Matching mit endlichem Automat

## Aufgabe
- Finde DEA für Menge der Wörter $uababcv$ mit $u,v \in \{a,b,c\}^*$
### Zugehöriger Algorithmus
```
Berechne Übergangsfunktion δ;
z:=0;
FOR i:=1 TO n DO
	z:=δ(z,T[i]);
	IF z=m THEN OUT(i-m) ENDIF
ENDFOR
```
### Automat
![[StringMatchingAutomatBeispiel.png|400]]
- + Fangzustand
