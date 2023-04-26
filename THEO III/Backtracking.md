# Backtracking
- es wird versucht schneller zu sein als das Brute-Force-Druchprobieren
	- Lösungsraum für Problem aus $n$ Komponenten, jeweils endliche viele Werte annehmen können
	- -> exponentiell viele Lösungen -> alle durchprobieren

## Beispiel
- logische Formel mit $n$ Variablen
- Gesucht: erfüllende Belegung
- Formel in KNF
	- Tripel von Variable finden, das in Klausel vorkommt und nicht belegt
	- wenn nicht gibt -> verbliebene Teilfromel leicht lösbar (2-KNFSAT...)
	- wenn gibt -> alle noch möglichen Belegungen ausprobieren
		- setzen 3 Variablen auf alle möglichen Werte (8 Möglichkeiten, eine ausgeschlossen wegen verwendeter Klausel)
		- **Rechenzeit für rekursive Aufrufe** $T(n) = 7 * T(n-3)$
		- **Rekursionstiefe** $n/3$
		- **Gesamtlaufzeit Algorithmus** $O(7^{n/3})$ -> $O(1.913^n)$ -> $o(2^n)$

## Branch and Bound
- Form des Backtrackings
- Baumstruktur des momentanen Fortschritts des Ablaufs
	- zu bearbeitende Problem ist Minimierungsproblem
	- $n$ Komponente mit Werten, sodass gewisser Zielwert minimiert

### Beispiel TSP-Problem
- untere Schranke für Länge eines Weges durch Stadt
	- alle Zeilen, dann alle Spalten der Entfernungsmatrix um jeweilingen Minimaleintrag herabsetzen
	- **Bound:** Summe der abgezogenen Werte

- Überprüfung: jede Tour mindestens so lang wie Bound
![[BranchandBound_TSPProblem.png]]