# Graphen
## Definition
- 4-Tupel $(V,E,\sigma, \tau)$
	- Mengen $V,E$
	- totale Abbildungen $\sigma: E \rightarrow V$ und $\tau: E \rightarrow V$

## Definition: ungerichtete Graphen
- Paar $(V,E)$ 
	- Menge der Knoten $V$ 
	- Menge der Kanten $E \subseteq \binom{V}{2}$
### Handschlaglemma
- Summe aller Knotengrade in ungerichtetem Graph ist immer gerade
- **Folgerung:**
	- In jedem endlichen Graph ist Anzahl der Knoten mit ungeradem Grad gerade

## Definition: Komplementgraph
- Graph $G = (V,E)$
- Komplement Graph $G' = (V, \binom{V}{2} \setminus E)$

## Fachtermini
#### Inzidenz
- Knoten $u$ und Kante $e$ sind **inzident** wenn $u \in e$ gilt
#### Adjazenz
- Zwei Knoten $u,v$ sind **adjazent** wenn $\{u,v\} \in E$ gilt
#### Knotengrad
- **Grad** des Knotens $u \in V$ ist die **Anzahl** der Kanten, die zu *inzident* sind
- **Beispiele:**
	- **Graph $C_n$**
		- Knotengrad jedes Knoten = 2
		- Zyklus
	- **Graph $P_n$**
		- zwei Knoten Grad 1
		- übrigen Grad 2
	- **Graph $K_n$**
		- Kanten von jedem Knoten zu allen anderen
		- Knotengrad jedes Knoten = Gesamtanzahl Knoten - 1
		- *vollständig*
	- **Graph $K_{3,3}$**
		- jeder Knoten hat Grad 3


## Besondere Graphen
### Isomorphe Graphen
- Graphen $G_1 = (V_1,E_1), \quad G_2 = (V_2,E_2)$ **isomorph**, wenn
	- *bijektive* Abbildung $φ : V_1 → V_2$, sodass für alle $u,v \in E_1$ gilt:
	- $\{u,v\} ∈ E_1 \iff \{φ(u),φ(v)\} ∈ E_2$
	- Graphen sind "bis auf Umbenennung" gleich
#### Beispiel: Stier
![[GraphenBeispielStier.png|50]]
- Komplementgraph ist isomorph zum ursprünglichen Graph

### Bipartite Graphen
- $G =(V,E)$ **bipartit**, wenn
	- Knotenmenge in $V_1$ und $V_2$ aufgeteilt
	- für jede Kante $\{u,v\} \in E$ genau einer der beiden Knoten $u,v$ in jeder der beiden Mengen $V_1$ und $V_2$ liegt
#### Beispiel:
![[GraphenBeispielBipartit.png|150]]
- Abbildung $φ$:
	- $φ(A) = 1, φ(B) = 4, φ(C ) = 2, φ(D) = 5, φ(E ) = 3, φ(F ) = 6$
	- bijektiv
	- bildet obigen Graph auf bipartitem Graph $K_{3,3}$ ab:
![[GraphenBeispielK33.png|150]]

### Zusammenhängende Graphen
- zwischen je zwei Knoten immer einen Weg gibt
	- für $u, u′ ∈ V$ existieren $v_0, . . . , v_n$ so, dass 
		- $v_0 = u, v_n = u′$
		- $(v_0, . . . , v_n)$ ist ein Weg im Graph

### Planare Graphen
- $G =(V,E)$ planar, wenn zeichenbar in Ebene ohne das Kanten sich schneiden
#### Beispiele
- $P_n, C_n$ 
#### Satz: Eulerformel
-> Folie 23.6f.
- in endlich zusammenhängenden planaren Graphen mit $n \geq 1$ Knoten, $m$ Kanten, $f$ Facetten gilt:
	- $n - m + f = 2$
##### Facette
- zusammenhängende Fläche, die von Kanten berandet wird
- "Äußere" immer Facette
#### Folgerungen
-> Folie 23.8f.
1. Ein planarer Graph mit $n ≥ 3$ Knoten hat höchstens $3n − 6$ Kanten  
2. Ein planarer bipartiter Graph mit $n ≥ 4$ Knoten hat höchstens $2n − 4$ Kanten  
3. In jedem planaren Graph gibt es mindestens einen Knoten mit Grad kleiner oder gleich 5  
	- Ikosaeders – Graph mit 12 Knoten, die alle den Grad 5 haben
4. Der $K_5$ und der $K_{3,3}$ sind nicht planar
#### Satz von Kuratowski
- Graph genau dann planar, wenn
	-  Keine "Unterteilung" des $K_5$ oder $K_{3,3}$ enthalten

## Wege und Kreise
### Weg/Pfad
- Graph $G=(V,E)$
- **Folge $(v_0,...,v_n)$ von Knoten** $v_i  \in V$ mit Eigenschaft, dass für alle $1 \leq i \leq n$ gilt:
	- $\{v_i−1, v_i \} ∈ E$
- **Länge** des Weges ist $n$
- *einfacher Weg*
	- alle Knoten verschieden
### Kreis
- Weg $(v_0,...,v_n)$ mit $v_0 = v_n$
- *einfacher Kreis*
	- Kreis $(v_0,...,v_n)$ mit $v_0 = v_n$
	- Knoten $v_0,...,v_{n-1}$ alle verschieden

### Eulerweg
- wenn jede Kante von $G = (V,E)$ genau einmal durchlaufen wird
### Eulerkreis
- Eulerweg der gleichzeitig ein Kreis ist
#### Beispiele
- $P_n$ (für $n \geq 2$)
	- hat immer Eulerweg aber kein Eulerkreis
- jeder $C_n$ hat Eulerkreis
#### Satz
-> Folie 23.3f.
- Zusammenhängender endlicher Graph $G=(V,E)$ 
	- hat genau dann **Eulerpfad**, wenn
		- Anzahl der Knoten mit ungeradem Grad maximal 2
	- hat genau dann **Eulerkreis**, wenn
		- alle Knoten haben geraden Grad

