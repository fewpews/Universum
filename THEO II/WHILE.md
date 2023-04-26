# WHILE-Programme
- Für ein gegebenes Programm $P$ ist auch $\text{WHILE} \: x_i \neq 0 \: \text{DO} \: P \: \text{END}$ ein erlaubtes Programm

## Semantik
- Programm $P$ soll solange wiederholt ausgeführt werden, wie der Wert der Variablen $x_i$ nicht $0$ ist
	- Test ob $x_i =0$ zu Beginn

## WHILE-Berechenbarkeit
Definition:
- Funktion $f : \mathbb{N}^k \rightarrow \mathbb{N}$ nennen wir **WHILE-berechenbar**, wenn es ein WHILE-Programm $P$ gibt, das $f$ wie folt berechnet:
	- $P$ mit $n_1,...,n_k$ in den Variablen $x_1,...,x_k$ gestartet (restlichen Variablen $0$)
	- hält nach endlich vielen Schritten (wenn Wert $f(n_1,...n_k)$ definiert ist)
	- dann befindet sich in der Variable $x_0$ dieser Wert $f(n_1,...,n_k$)
	- Ist $f(n_1,...n_k)$ nicht definiert, so hält $P$ nicht

## Simulation von WHILE-Programmen
- Wertzuweisungen/Hintereinanderausführungen/WHILE-Schleifen mit Turingmaschinen simulierbar
	- Variable $x_i$ entspircht Band $i$ auf TM (Schleifen)
#### Satz
- Jede WHILE-berechenbare Funktion ist Turing-berechenbar

