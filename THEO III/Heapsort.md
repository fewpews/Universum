# Heapsort
- In-place
- jeder Knoten im Wert **kleiner(gleich)** beiden Nachfolgeknoten
	- **Minimum** immer in $a[1]$
	- für alle $i$ gilt Bedingung $a[i] \leq a[2i]$ und $a[i] \leq a[2i+1]$
	- nur falls $2i \leq n$ bzw. $2i+1 \leq n$
- **Tiefe:** $\lceil log \: n \rceil$

## Sortieren
- $a[1,...,n]$ in Heap
- Tausche $a[1]$ mit $a[n]$
- nur noch $a[1,...,n-1]$ betrachten
- Stelle Heap bei $a[1]$ wieder her und fahre rekursiv fort
### Reheap
#### Pseudo-Code
```
reheap(i):
	if 2i+1 > n then                                   <- Sonderfall
		if 2i = n then
			if a[i] > a[2i] then swap(a[i],a[2i])
	else                                               <- Normalfall
		if a[2i] <= a[2i+1] then
			if a[i] > a[2i] then
				swap(a[i],a[2i]); reheap(2i)
		else
			if a[i] > a[2i+1] then
				swap(a[i],a[2i+1]); reheap(2i+1)  
```

#### Anzahl Vergleiche der Heaperstellung
- Einsinken eines Elements von Höhe $h$ -> maximal $2h$ Vergleichsoperationen
	- $h=1$ maximal $n/2$ Elemente, $h=2$ maximal $n/4$ Elemente, ...
- **Obere Schranke** Anzahl Vergleiche:
	- $2·1·\frac{n}{2} + 2·2·\frac{n}{4} + 2·3·\frac{n}{8} + ... ≤ 2n· \sum^∞_{i=0} \frac{i}{2^i} = 4n ∈ \bf O(n)$

#### Aufwand
- jedes der $n$ Elemente von ganz oben nach unten
	- maximal $2n \: log \: n$ Vergleiche
- Gesamtzahl $V(n)$ der Vergleiche
	- $V(n) \leq 2n \: log \: n + O(n)$
- -> Schranke für Worst-Case
	- immer optimale Laufzeit $O(n \: log \: n)$
	- Konstante 2 auch bei Average-Case -> Quicksort besser

## Varianten
#### Bottom-Up Heapsort
- konstante bei $n \: log \: n$ kleiner
- wie Standard-Heapsort, reheap anders implementiert
- einsinkende Element sinkt bis zum Blatt (unabhängig von Wert)
	- jeder Schritt nur ein Vergleich
- dann so lange aufsteigen bis über ihm liegenede Element kleiner(gleich)
	- jeder Schritt nur ein Vergleich
##### Analyse
- Vergleich Absinken: $a[2i] < a[2i+1]$ 
	- nicht mehr als $n \: log \: n$ Vergleiche
- weniger als Hälfte um eine Ebene, weniger als ein Viertel um zwei Ebenen,...
	- weniger als $\frac{n}{2^i}$ um $i$ Ebenen -> im **Durchschnitt** plausibel
	- Gesamtzahl Aufstiege kleiner als $n$ mal unendliche Summe $\frac{i}{2^i}$
	- ->$\bf O(n)$
- **Average-Case** $\: n \: log\: n + o(n \: log \: n)$
- **Worst-Case:** $1.5 \: n \: log\: n + o(n \: log \: n)$

#### Ultimatives Heapsort
##### Gedaankenspiel - out-of-place
- $2n$ Speicherplätze für Sortierung von $n$ Elementen
	- Elemente $a[1,...,n]$ + weitere $n$ Elemente mit Wert $∞$
	- dann Heapsort bis $n$ Elemente einsortiert
	- **Aufwand:** $O(n)$ Vergleiche
		- aber $n \: log \: n$ Vergleiche für Heraussortieren der Elemente $a[1]$ bis $a[n]$ an die $n$ hinzugefügten Plätze -> $1 \cdot log \: n$ pro Element
		- Elemente mit Wert $∞$ ganz nach unten, aber kein Aufstieg

##### plan - in-place
- Eingabe-Array: erste Hälfte kleine / zweite Hälfte große Elemente
	- $i < \lceil n/2 \rceil, j ≥ \lceil n/2 \rceil \Rightarrow a[i] < a[j]$
- $a[j]$ mit $j ≥ \lceil n/2 \rceil$ behandeln als Wert $a[j]=∞$
- Wie in Gedankenspiel nach unten sickern
	- kleinste $a[i]$ auf Platz $a[n]$, zweitkleinste auf Platz $a[n-1]$,...
	- Quicksort-Schritt: Elemente zweite Hälfte Array (größer Median) nie an Position $a[n]$
	- unsortierte Array-Elemente (größer Median, von groß nach klein) in $a[1,...,\lfloor n/2 \rfloor]$
	- 
- Hälfte Array sortiert mit Aufwand $\frac{n}{2} log \: n$ 
- rekursiven Aufruf auf $a[1,...,\lfloor n/2 \rfloor]$ um Rest sortieren

##### Analyse
- Medianberechnung mit lineare Anzahl Vergleiche
- Erste Hälfte: Quicksort-Schritt und Heapaufbau -> linear viele Vergleiche 
	- höchstens $c \cdot n$ Vergleiche (für geeignetes $c$) 
	- sortieren $n/2$ Elemente ein (aus $log \: n$ Höhe bis ganz unten)
		- Heap wird jedesmal um ein Element kleiner
- Prozedur rekursiver Aufruf (halb so großer Eingabe-Array)
	- $T(n) = c · n + \frac{n}{2} log \: n + T(\frac{n}{2})$
	- **Lösung:** $T(n) = n \: log \: n + 2c · n$

##### Beispiel
-> Folie 11.3/4
