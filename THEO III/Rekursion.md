# Rekursion

Gegeben
- Problem abhängig von Parameter
- Löse für Parameterwert $n$ mit Hilfe von Teillösung für Parameterwert $m$ $(m < n)$
	- $sort(a_1,...,a_n): \: IF \: n>1 \: THEN \: sort(a_1,...,a_{n-1});$    füge $a_n$ ein.
	- Fibonacci-Zahlen, Euklidischer Algorithmus