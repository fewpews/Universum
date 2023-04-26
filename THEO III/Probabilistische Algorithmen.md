# Probabilistische Algorithmen

## Verstärkung der Erfolgswahrscheinlichkeit
- Verbesserung probabilistischer Algorithmus durch Wiederholung
	- Sprache $L$,, Algorithmus
	- `Input x ∈ L: Der Algorithmus gibt JA aus`
	- `Input x ∉ L: Der Algorithmus gibt NEIN mit W'keit ≥ 1/2 aus`
- Algorithmus $n$ mal wiederholen
	- $x ∈ L$ wenn $n$ mal JA, sonst $x ∉ L$
	- JA-Antwort mit Wahrscheinlichkeit ≤ $1/2^n$

- Auch bei **zweiseitigem Fehler** ähnlicher Effekt
	- Algorithmus gibt JA mit W'keit $2/3$
		- 
- **Allgemein:** $t$-fache Wiederholung
	- richitge Ergebnis mit W'keit $> (1- \delta)$
	- maximale Fehlerwahrscheinlichkeit $\delta '$
		- $\delta ' = [2* \sqrt{\delta(1- \delta}]^t$ (für $0< \delta < 1/2$)

##  Monte Carlo Algorithmen
- darf falsches Ergebnis dürfen
- W'keit für korrektes Ergebnis möglichst hoch
	- -> Gleichverteilung bei  Zufallsexperiment

### Beispiel: Primzahltest
- theoretisch mit AKS-Test deterministisch in polynomieller Zeit möglich
- **Effizienter: probabilistischer Primzahltest**

- z.B. Fermat-Primzahltest
	- gibt für jede Große Zahl aus: ist keine Primzahl / ist wahrscheinlich Primzahl
	- selbst Test mit Fehlerwahrscheinlichkeit von 25% brauchbar
		- 5 Wiederholungen -> 0,1%

## Las Vegas Algorithmen
- keine Fehler erlaubt
- Laufzeit von verwendeten Zufallswerten abhängig
- Option keine Ausgabe zu machen
	- Algortihmus wiederholen mit neuen Zufallswerten