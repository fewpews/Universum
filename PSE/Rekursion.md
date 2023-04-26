# Rekursion
## Allgemeiner Begriff
- Definition für Konzept ist **rekursiv**, wenn sie eine Instanz des Konzepts selbst betrifft

## Rekursive Operationen
- wenn Möglichkeit besteht eine Lösung für das Problem für einen bestimmten Einganssatz aus Lösungen **für einen oder mehrer kleinere Eingangsätze** zu konstruieren
- *Direkte Rekursion*: Operationsrump beinhaltet Aufruf der Operation selbst
	- r ruft sich selbst auf
- *Indirekte Rekursion*
	- r ruft s auf, s ruft r auf
	- r1 ruft r2 auf, r2 ruft rn auf,... rn ruft r1 auf

### Nützliche rekursive Definitionen
- **R1** gibt mindestens einen nicht rekursiven Zweig
- **R2** jeder rekursive Zweig tritt in Kontext auf, der sich vom Original unterscheidet
- **R3** für jeden rekursiven Zweig bringt der Kontextwechsel (R2) ihn näher an mindestens einen der nicht rekusiven Fälle (R1)

### Rekursionsvariante - Korrektheit der Rekursion
Gleiches Konzept wie bei Schleifen
- Jede rekusive Operation sollte **Rekursionvariante** verwenden: 
	- ganzzahlige Menge, die einem Aufruf zugeordnet, so dass:
		- Variante immer >= 0 (aus Vorbedingung)
		- Wenn Operationsausführung mit Variantenwert v beginnt, erfüllt der Wert v' für jeden rekusiven Aufruf 0 ≤ v' < v

### Rekursioneliminierung über Schleifen
- Rekursive Aufrufe verursachen Laufzeitstrafe -> Stack
- Manchmal kann rekursives Schema durch Schleife ersetzt werden
	- "Tail Recursion" (letzte Anweisung in Routine ist rekursiver Aufruf) kann in der Regel einfach eliminiert werden

### Beispiele
- Fakultät berechnen
- Größter gemeinsamer Teiler (ggT)
- Die Türme von Hanoi

## Rekursive Datenstrukturen
VL 17, Folie 50ff.
- binärer Baum von Typ G entweder:
	- Leer
	- Ein Knoten der aus drei disjunkten Teilen besteht
		- Wurzelknoten - Wert vom Typ G
		- Linke Teilbaum - (optionaler) binärere Baum vom Typ G
		- Rechte Teilbaum - (optionaler) binärere Baum vom Typ G