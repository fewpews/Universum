# Medianberechnung in Linearzeit
## Ziel
- Median von $n$ Array-Elementen
- Index $r$ finden, für den gilt...
	- $|\{i \: | \: a[i] ≤ a[r]\}| ≥ n/2$ und $|\{i \: | \: a[i] ≤ a[r]\}| ≥ n/2$
	- mit nur $O(n)$ Vergleichen

## Erster Schritt: Median aus 5
- gutes Pivot-Element suchen
- *lokaler* Median aus 5 Elementen -> 6 Vergleiche:
```
Die Elemente seien a,b,c,d,e
IF a>b THEN vertausche(a,b) ENDIF;
IF c>d THEN vertausche(c,d) ENDIF;
IF a>c THEN vertausche(a,c); vertausche(b,d) ENDIF;
	-> a kleiner b,c,d -> nicht Median
IF b>e THEN vertausche(b,e) ENDIF;
IF b>c THEN vertausche(b,c); vertausche(e,d) ENDIF;
	-> b kleiner c,d,e -> nicht Median
	-> d größer a,b,c -> nicht Median

-> Vergleich c und e -> kleinere ist Median
```
- **Gesamtaufwand:** $\frac{6}{5} n$ Vergleiche

## Zweiter Schritt: Median der Mediane
-> muss nicht wirkliche Median sein -> gutes Pivotelement
- aus jedem Fünferblock des Eingabe-Arrays jeweils Blockmedian
- von $\lceil \frac{n}{5} \rceil$ Elementen rekursiv Median Berechnen
- **Anzahl Vergleiche Gesamtprozedur:** $T(\frac{n}{5})$ (Eingabe $a[1,...,n]$)

## Dritter Schritt: Feld aufteilen
- gesamter Array in zwei Teile:
	- kleiner als Pivot: $a[1,...,m]$
	- größer als Pivot: $a[m+1,...,n]$
- Es gilt: $\frac{3}{10} n \leq m \leq \frac{7}{10} n$
	- jeder Blockmedian kleiner Pivot -> drei Elemente aus Block im linken Teil
	- trifft bei Hälfte der $n/5$ Blöcke zu -> $n/10$
	- rechts analog
- Bei rekursiven Aufruf des gesuchten Elements nur mit Feldgröße bis $\frac{7}{10} n$ rechnen

## Vierter Schritt: Rekursion
- gesuchte Element in einem beider Teile
- $k$-kleinste Element in $a[1,...,n]$ 
```
Ist k <= m?
	JA: Suche k-kleinste Element in a[1,...,m]
	NEIN: Suche (k-m)-kleinste Element in a[m+1,...,n]
```

## Aufwand
- **Gesamtaufwand:** $T(n) \leq \frac{6}{5} n + T(\frac{n}{5}) + n + T(\frac{7}{10} n)$
	-  $\frac{6}{5} n$ Vergleiche für Blockmediane
	- $T(\frac{n}{5})$ für erste Rekursion
	- maximal $n$ Vergleiche für Quicksort-Schritt
	- rekursiv $T(\frac{7}{10} n$)
- [[Master-Theorem II]] -> **lineare Anzahl Vergleiche**