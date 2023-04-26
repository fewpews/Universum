# Traveling Salesman Problem
## Definition
- **Gegeben:** $n \times n$-Entfernungsmatrix $\forall i,j \in \{1,...,n\}$
	- wie weit der Weg von Stadt $i$ zu Stadt $j$ 
	- Eintrag $m_{i,j}$ 
	- Matrix nicht notwendig symmetrisch
		- $m_{i,j} \neq m_{j,i}$ 
	- Muss nicht direkten Weg geben
		- Eintrag den Wert $\infty$ 
- **Gesucht:** Permutatuin $\pi$ der Zahlen $\{1,...,n\}$
	- Rundweg durch $\pi(1),...,\pi(n),\pi(1)$ hat minimale Länge

## [[Backtracking#Beispiel TSP-Problem]]

## Dynamische Programmieren: TSP
### Kosten
- Kosten des Weges allgemein
	- $c(\pi) = \sum^{n-1}_{k=1} m_{\pi(k),\pi(k+1)} + m_{\pi(n),\pi(1)}$ 
- Annahme $\pi(1) = 1$ 
- Kosten mit Annahme
	- $c(\pi) = m_{1,\pi(2)} + \sum^{n-1}_{k=2} m_{\pi(k),\pi(k+1)} + m_{\pi(n),\pi(1)}$

### Formel $g(i,S)$
- Tabelle mit Einträgen $g(i,S)$ für $S \subseteq \{2,...,n\}$ und $i \in \{1,...,n\}$
	- $g(i,S)$ **Kosten eines kürzesten Weges**
	- von Stadt $i$ startend alle Städte in $S$ genau einmal besuchen und dann zu Stadt 1 zurückkehren
- $g(i,\emptyset) = m_{i,1}$
- $g(i,S) = min_{j \in S}(m_{i,j} + g(j,S \setminus \{j\}))$
- **Gesamtkosten kürzester Weg:** $g(1,\{2,...,n\})$

### Pseudo-Code
- berechnen von $g(i,S)$ der Reihe nach -> für $S=\emptyset, |S| = 1,..., |S| = n-2$
- Zum Schluss $g(1,\{2,...,n\})$ berechnen
```
FOR i := 2 TO n DO
	g[i,∅] := m[i, 1];  
FOR k := 1 TO n − 2 DO  
	FORALL S ⊆ {2,...,n}, |S| = k DO  
		FORALL i ∈ {2,...,n} \ S DO  
			g [i, S] := min_j∈S (m_i,j + g[j,S \ {j}])  
g[1,{2,...,n}] := min_j∈{2,...,n} (m_1,j + g[j,{2,...,n} \ {j}])
```

### Analyse
- Termination und Korrektheit klar
- Effizienz:
	- Tabelle mit Einträgen $g(i,S), \quad i \in \{1,...,n\}, S \subseteq \{2,...,n\}$
	- Laufvariablen $i$ und $k$
		- **Speicherbedarf** in $O(n \cdot 2^n)$
	- Jeder der $n \cdot 2^n$ Einträge einmal berechnet durch Ermittlung eines Minimums von maximal $n-1$ bekannten Werten
		- **Zeitkomplexität** $O(n^2 \cdot 2^n)$
		- besser als naive Ansätze im Bereich $n!$ 

### Beispiel
- Matrix $M$ 
	- ![[TSP_BeispielMatrix.png|150]]
- Menge $\{2,3,4\}$ hat 8 Teilmengen
	- ![[TSP_DynamischeProgrammierung.png]]
- **Lösung:** $1 \rightarrow 35(2) \rightarrow 25(4) \rightarrow 3 \rightarrow 1$
- **Länge:** $m_{1,2} + m_{2,4} + m_{4,3} + m_{3,1} = 10 + 10 + 9 + 6 = 35$

