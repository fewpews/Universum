# Average-Case Analyse
Durchschnittskomplexität/Komplexität im Mittel

## Annahme:
- alle Eingaben Länge $n$ treten mit gleicher Wahrscheinlichkeit auf -> *gleichverteilt*

- $av-time_A(n) = E [T_A(n)]$
	- $T_A(n)$ ist Zufallsvariable
		Experiment: „Führe A auf zufälliger Eingabe der Länge n aus“
	- durch Laufzeit $av-time_A(n) = \frac{1}{N} · \sum_{|x|=n}  time_A(x)$
	- mit $N = |\{x : |x| = n\}|$

## Beispiel: Maximumberechnung
-> Folie 1.5