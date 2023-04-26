# GOTO-Programme
- Sind Anweisungsfolgen mit Marken:
	- $M_1: A_1; M_2: A_2; ...; M_k: A_k$
- Zugelassene Anweisungstypen:
	- $x_i := x_j \pm c$
	- $GOTO \: M_i$
	- $HALT$
	-  $IF \: x_i=c \: THEN \: GOTO \: M_j$
## Semantik
- Zuweisung wie bei LOOP behandeln
- zusätzlich Programmzähler hochzählen
	- $GOTO \: M_i$: Programmzähler auf $i$

## GOTO- simulieren WHILE-Programme
$WHILE \: x_i \neq 0 \: DO \: P \: END$ simuliert durch:
```
M_1:
	IF x_i=0 THEN GOTO M_2
	P
	GOTO M_1
M_2: ...
```
### Satz
- Jedes WHILE-Programm kann durch GOTO-Programm simuliert werden

## WHILE- simulieren GOTO-Programme
### Satz
- Jedes GOTO-Programm kann durch WHILE-Programm simuliert werden, mit nur einer einzigen WHILE-Schleife
	- (aber vielleicht vielen LOOP-Anweisungen)
### Beweis
- Schleife mit simuliertem Programmzähler
- Zuweisungen, GOTO, IF-THEN-GOTO und HALT
- schrittweise simulieren, Programmzähler immer anpassen
#### Details
$M_1: A_1; M_2: A_2; ...; M_k: A_k$
```
count := 1;
WHILLE count != 0 DO
	IF count 1 = THEN A'_1 END;
	IF count 2 = THEN A'_2 END;
	...
	IF count k = THEN A'_k END;
END
```
Wenn $A_i$ ..., dann so definiert:
- $x_j := x_i \pm c \quad \Rightarrow \quad x_j := x_i \pm c; count := count + 1$
- $HALT$-Anweisung $\quad \Rightarrow \quad count:=0$
- $GOTO \: M_n$-Anweisung $\quad \Rightarrow \quad count:=n$
- $IF \: x_j = c \: THEN \: GOTO \: M_n \quad \Rightarrow \quad IF \: x_j = c \: THEN \: count:=n; \: ELSE \: count := count+1 \: END$
## Normalform-Theorem von Kleene
### Satz
- Jede [[WHILE]]-berechenbare Funktion kann durch WHILE-Programm mit nur einer WHILE-Schleife berechnet werden
### Beweis
- gleichwertiges GOTO-Programm erzeugen
- nach eben bewiesenem Satz in WHILE-Programm umwandeln

## GOTO simuliert Turingmaschinen
bisher $LOOP \subsetneq  GOTO = WHILE \subseteq TM$
jetzt $WHILE = TM$
- Turingmaschine $M = (Z, \Sigma, \Gamma, \delta, z_1, \square, E)$ berechne $f$
- simulieren $M$ mit GOTO-Programm:
	- $M_1: P_1; M_2: P_2; M_3:P_3$

### $P_1:$ Anfangskonfigurationen $z_1bin(x_1 )\#...\#bin(x_k)$ aus Werten $x_1,...,x_k$ 
- Sei Konfiguration der TM $\alpha z_l \beta$ mit $\alpha,\beta \in \Gamma^*$ und $z_l \in Z$
- Sei $Z = \{z_1,...,z_k\}, \Gamma = \{a_1,...,a_m\}$ und $b>m$
- $\alpha$ durch $|\alpha|$-stellige Zahl zur Basis $b$ ($b$-Stück)
	- $\alpha = a_{i_1}a_{i_2}...a_{i_p}$ -> $x = \Sigma^p_{\mu=1} i_\mu \cdot b^{p-\mu}$ 
	- $\beta = a_{j_1}a_{j_2}...a_{j_p}$ -> $x = \Sigma^q_{\upnu=1} j_\upnu \cdot b^{\upnu-1}$ 
- Zustand $z_l$ durch Zahl $z=l$ 
-> $(x,y,z)$ beschreibt nun eindeutig eine Konfiguration der TM

### $P_2:$ Schritt-für-Schritt-Simulation der Turingmaschine
```
M_2:
	IF z ist Endzustand THEN GOTO M_3;  
	a := y MOD b;  
	IF (z = 1) AND ... 
	IF (z = i) AND (a = j) THEN GOTO M_ij;              //alle Kombinationen!  
	...
	IF (z = k) AND ...

M_11: Programmsequenz für δ(z_1,a_1)
	GOTO M_2;
M_12: Programmsequenz für δ(z_1,a_2)
	GOTO M_2;
...
M_km: Programmsequenz für δ(z_k,a_m)
	GOTO M_2;
```
#### Simulation der TM-Übergänge $M_{ij}$
```
δ(z_i,a_j) = (z_i',a_j',N):
	z := i';  
	y := b * (y DIV b) + j';
```

```
δ(z_i,a_j) = (z_i',a_j',R):
	z := i';  
	y :=  y DIV b;
	x := b * x + j';
```

```
δ(z_i,a_j) = (z_i',a_j',L):
	z := i';  
	y := b^2 * (y DIV b) + b * j' + (x MOD b);
	x := x DIV b;
```

### $P_3:$ In Konfiguration $z_ebin(y)$ berechne $y$ und speichere Wert/Ergebnis in $x_0$

### Satz
- Jede Turing-berechenbare Funktion ist GOTO-berechenbar
- WHILE = TM