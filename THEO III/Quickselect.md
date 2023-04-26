# Quickselect

## Funtkionsweise
- Idee von [[Quicksort]]
- zufälliges Pivot-Element
	1. Teil $a[1,...,m]$
	2. Teil $a[m+1,...,n]$
- Rekursiv weiter teilen

## Worst-Case
- wie bei [[Quicksort#Worst-Case|Quicksort]]
- kleinste/größte Element als Pivot
	- **Laufzeit:** quadratisch

## Average-Case
- Gleichverteilung
- Anzahl Vergleiche: $Q(n)$ 
	- $Q(n) \leq 4n$
