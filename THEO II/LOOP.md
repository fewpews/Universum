# LOOP-Programme
- Variablen $x_i \: (i \in \mathbb{N})$
- Konstanten: $0,1,2,...$ (also $\mathbb{N}$)
- Trennsymbole: $; \: :=$
- Operationen: $+ \: -$
- Schlüsselwörter: `LOOP, DO, END`
## Syntax
- $x_i := x_j + c$ und $x_i := x_j - c$ sind LOOP-Programme
- Wenn $P_1$ und $P_2$ LOOP-Programme sind, dann auch $P_1;P_2$
- Ist $P$ LOOP-Programm, dann auch `LOOP x_i DO P END` $(i \in \mathbb{N})$
## Semantik
- Soll Funktion $f: \mathbb{N}^k \rightarrow \mathbb{N}$ berechnen
- Zu Beginn habe Variable $x_i$ den Wert $n_i \: (i=1,...,k)$
	- alle anderen Wert $0$
- Interpretaion einer Wertzuweisung ($x_i := x_j + c$ / $x_i := x_j - c$)
- Nur modifizierte Subtraktion!
- Hintereinanderausführung $P_1;P_2$
- `LOOP x_i DO P END` -> $P$ wird $x_i$-mal ausgeführt

## LOOP-Berechenbarkeit
Definition:
- Funktion $f: \mathbb{N}^k \rightarrow \mathbb{N}$ nennen wir **LOOP-berechenbar**, wenn es ein LOOP-Programm $P$ gibt, das $f$ wie folgt berechnet:
	- $P$ mit $n_1,...,n_k$ in den Variablen $x_i,...,x_k$ gestartet (restliche Variablen $0$)
	- hält nach endlichen Schritten
	- dann befindet sich in Variable $x_0$ der Wert $f(n_1,...,n_k)$

- Alle LOOP-berechenbaren Funktionen sind **total**
	- Bei jedem Input gibts ein Output -> keine Undefiniertheit -> total
- [[Ackermann-Funktion]]
	- -> totale, intuitiv berechenbare Funktion die nicht LOOP-berechenbar

## Simulationen in LOOP
- Wertzuweisungen $x_i := x_j + c$ und $x_i := x_j - c$ simulierbar
	- `x_i := x_j + 0 bzw. x_i := x_m + c`
- Versch. IF-Anweisungen simulierbar
	```
	z.B. IF x_i > 8 THEN P FI
	
	x_n := x_i - 8; x_m := 1;
	LOOP x_n DO LOOP x_m DO P END;
	x_m:=0, x_n:=0
	END
	```
- Übliche arithmetischen Berechnungen simulierbar
	- Addition/Subtraktion/Multiplikation/Division
