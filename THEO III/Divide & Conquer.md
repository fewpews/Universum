# Divide and Conquer
= Divide et impera = Teile und herrsche

## Funktionsweise
1. Teile $a_1, ..., a_n$ auf in $b_1, ....b_m$ und $c_1, ..., c_{n-m}$
	- Größer der Teile $m \approx \frac{n}{2}$ -> "guter" [[THEO III/Algorithmus|Algorithmus]]
2. Teile [[THEO III/Rekursion|rekursiv]] weiter wie in 1. Die Ergbenisse sind $LSG_b$ und $LSG_c$
3. Füge Teillösungen $LSG_b$ und $LSG_c$ zur $LSG_a$ des ursprünglichen Problems zusammen

- Schritt 1. und 3. in [[linearer Laufzeit]] -> $O(n)$ bzw. $\Theta(n)$ [[Landau-Symbole|->link]]
	- nicht zu viel Zeit verbrauchen

## Extremfälle
1. $m = n/2$
	- immer die Mitte $\Rightarrow O(n \: log \: n)$
	- Rekursionstiefe entscheidet Rechenzeit
2. $m=1 \rightarrow m=n-1$
	- sehr großer und sehr kleiner Teil
	- Rekursionstiefe $n$, Laufzeit Aurufebenen $n/2 \Rightarrow \Theta(n^2)$

## Laufzeit: Allgemein
- Aufteilung $\alpha * N$ und $(1-\alpha)*N$
- Rekursionstiefe *logarithmisch*
- Laufzeit $O(n \: log \: n)$

## Laufzeit: Multiplikation
-> Folie 3.4

## Beispiel
#### Mergesort
- Eingabe Array $a_1,...,a_n$ (OBdA $n$ gerade)
	-  $mergesort(a_1,...,a_n):$
		$IF \: n \geq 2 \: THEN$
			$b_1,...b_{n/2} := mergesort(a_1,...,a_{n/2})$
			$c_1,...b_{n/2} := mergesort(a_{n/2+1},...,a_{n})$
			$a_1,...a_n := mische \: b_1,...,b_{n/2} \: mit \: c_1,...,c_{n/2}$
		$END$

- Aufteilungsschritt in $O(n)$ -> optimal, da $m=n/2$
- mischen in Linearzeit
- *Aufruftiefe/Rekursionstiefe* $log \: n$
- Aufwand je "Ebene" $O(n)$
- Gesamt $O(n \: log \: n)$
- Nachteil: out of place

#### Quicksort
- Eingabe Array $a_1,...,a_n$
	- $quicksort(a_1,...,a_n):$
		$IF \: n \geq 2 \: THEN$
			teile $a_1,...,a_n$ in $b_1,...,b_r$ und $c_1,...,c_s$ so, dass $r+s=n$,  $b_i \leq a_1$ und $c_j > a_1$ für alle $i,j$
			$quicksort(b_1,...,b_r);$
			$quicksort(c_1,...,c_s);$
			$Lösung: \: b_1,...,b_r, \: c_1,...,c_s$
		$END$

- Laufzeit:
	- [[Worst-Case Analyse|worst-case]] $\Theta(n^2)$
	- [[Average-Case Analyse|average-case]] $O(n \: log \: n)$

## Fachtermini
#### Aufruftiefe / Rekursionstiefe
---
**Related:**
[[DSA/Divide & Conquer]]
