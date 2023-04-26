# Quicksort

## Funktionsprinzip
- [[Divide & Conquer]]
- wähle **Pivot-Element** aus zu sortierendem Array
- sortiert in zwei Teile: links kleiner/rechts größer als Pivot-Element
- Pivot landet dirket auf seinem Platz bei geschickter Implementierung
- Restelemente $(n-1)$ rekursiv weiter sortiert

## Varianten
#### Standard
- Teil $a[links,...,rechts]$
- **Pivot-Element:** zufällig aus Array
#### Median-aus-drei
- Teil $a[links,...,rechts]$
- **Pivot-Element:** Mittelwert von...
	- $a[links]$
	- $a[rechts]$
	- $a[links+rechts/2]$
- Aufwändig -> komplette Medianberechnung in jedem Teil-Array
	- kaum Verwendung in Praxis
## Laufzeit
### Worst-Case
- $O(n^2)$
- in jedem Fall
### Average-Case
- Standard-Variante
- Bei jeder Aufteilung von $m$ Elementen -> $(m-1)$ Vergleiche mit Pivot-Element
#### Wahrscheinlichkeit eines Vergleiches
- $a[1, . . . , n]$ sei Folge $s_1 < s_2 < · · · < s_{n−1} < s_n$
- Werte $i < j$ ->Elemente $s_i$ und $s_j$ vegleichen
	- **1.Fall:** im gleichen Array-Teil
		- Pivot $s_\mu$ mit $\mu < i$ oder $\mu > j$
	- **2.Fall:** in verschiedenen Array-Teile
		- Pivot $s_\mu$ mit $i < \mu < j$
- **Resultierende Wahrscheinlichkeit**: $\frac{2}{j-i+1}$
#### Erwartete Anzahl an Vergleichen $V(n)$
- $V(n) = \sum^{n-1}_{i=1} \sum^n_{j=i+1} \frac{2}{j-i+1} ≤ \sum^{n-1}_{i=1} 2 \cdot  (H_n - 1) ≤ 2n \cdot (H_n - 1)$
- $H_n -1 kann durch $ln \: n$ beschränkt werden
- **Resultat:** $V(n) ≤ 2n \: ln \: n < 1.39 \: n \: log \: n$

