# Dijkstra
- Lösung des single-source-all-targets shortest-path Problems

## Algorithmus
- ungerichteter Graph $G = (V,E)$ ohne Schlingen,Mehrfachkanten
- Kantengewichtung $γ : E → N \: \backslash \: \{0\}$
- Array $D[1,...,n]$ mit $n=|V|$
	- Anfangs Schätzwerte/Später genauen Abstandswerte der Knoten $x=x_i$ vom Startknoten $u$ 
- Array $v[1,...,n]$ 
	- von welchem Knoten $y=v[i]$ bei kürzestem Weg zu Knoten $x_i$ gehen
#### Pseudo-Code
```
B:={u}; R:=∅; v(u):=undef; D(u):=0;                       (* Init B, R und U *)
FORALL y∈V \ {u} mit (u,y)∈E DO
	D(y):=(u,y); v(y):=u; R:=R ∪ {y};
ENDFOR;
U:=V\(R ∪ {u});
WHILE R = ∅ DO
	x:=undef; α:=∞;                              (* suche x mit D(x) minimal *)  
	FORALL y∈R DO  
		IF D(y) < α THEN x:=y; α:=D(y) ENDIF  
	ENDFOR  
	B:=B ∪ {x}; R:=R\{x};                                  (* x von R nach B *)  
	FORALL (x,y)∈E DO  
		IF y∈U THEN                                    (* Rand aktualisieren *)  
			D(y) := D(x) + γ(x,y);  
			v(y) := x; U:=U\{y}; R:=R ∪ {y};  
		ELSIF y∈R AND D(x) + γ(x,y) < D(y) THEN  
			D(y) := D(x) + γ(x,y); v(y):= x;                 (* kürzerer Weg *)  
		ENDIF (* über x *)  
	ENDFOR  
ENDWHILE
```

## Nachweis Algorithmus
#### Nachweis Termininierung
- Teilmeng $B \subseteq V$ 
	- maximal $n$ Elemente
- Zu Beginn hat $B$ ein Element
- Jeder Durchgang WHILE-Schleife -> ein weiteres Element dazu (aus $R$ entfernt)
	- Elemente aus $R$ kommen aus $U$ -> jedes da nach $R$ geschoben aus $U$ entfernt
- Jeder Knoten höchstens einmal zu $B$ hinzugefügt
	- maximal $n-1$ Schleifendurchgänge -> **terminiert**

#### Nachweis Korrektheit der Werte
- Schleifeninvariante:
	- nach $k$-ten Schleifendurchlauf $(k=0,1,...)$ gilt:
		- Für jeden Knoten $x\in B$ is kürzester Weg $(u,x)$ und seine Länge bekannt
		- $\forall y \in B$ und $\forall z \notin B$ gilt:
			- der kürzeste Weg $(u,y)$ höchstens so lang wie kürzester Weg $(u,z)$
- $k=0$ korrekt

##### Beweis k+1
- für jeden Knoten $b \in U$ gibt es ein Knoten in $R$, der kürzeren Abstand von $u$ als $b$
- wenn Knoten $x \in R$ den kleinsten Abstand von $u$, dann auch Invariante korrekt wenn Knoten in $B$ hinzugefügt
- **Wiederspruchsbeweis:**
	- Gegenteil: Es gibt Knoten $a \in R$ dessen Abstand zu $u$ kleiner als von gewähltem Knoten $x$
	- -> Weg muss irgendwann aus $B$ herausführen
	- ->Teilweg (auf Weg zu $a$) der schon länger als gesamter Weg $(u,x)$ 
	- **-> Wiederspruch (alle Gewichte posititv) -> Korrektheit bewiesen**

## Analyse
- Initialisierung (**WHILE-Schleife**(läuft höchstens $n-1$ mal)) bei $n$ Knoten 
	- $O(n)$ Rechenschritte
- Aufwand je Schleifendurchlauf
	- **Erste FORALL**: maximal $O(n)$ Fälle
	- **Zweite FORALL:** jede Kante aus $E$ nur einmal & nicht einmal behandeln
- **Gesamtaufwand:**
	- Maximum von $n^2$ und $m=|E|$
	- Da immer $m<n^2$ -> $\bf O(n^2)$

### Dichte/Dünne Graphen
**Dicht:**
- Graph mit $n$ Knoten und $\Omega(n^2)$ Kanten -> obere Grenze möglicher Kantendichte       -> *dichter* Graph
- Dijikstra-Algorithmus lineare Laufzeit
**Dünn:**
- z.B. planare Graphen
	- höchstens linear viele Kanten -> *dünne* Graphen
- Dijkstra-Algorithmus quadratische Laufzeit -> nicht optimal

### Aufwand: Rolle der Datenstruktur
- Aufwand bei Verwendung *abstrakten Datentyps* für Menge $R$
- Zugriff auf $R$
	- fügen Knoten in Menge wenn neue/unbetrachtete Nachbarn am Rand 
	- entfernen Knoten mit minimalem $D$-Wert
	- verändern $D$-Wert einiger Elemente von $R$
- Definieren drei Routinen:
	- `insert(R,y,D(y))`
		- höchstens $n$-mal
	- `x := delete-min(R)`
		- höchstens $n$-mal
	- `decrease-key(R,y,D(y))`
		- $m$-mal ($m$ = Anzahl Kanten Input-Graph)

#### Array
- `insert` -> $O(1)$
- `decrease-key` -> $O(1)$
- `delete-min` -> $O(n)$
- **Gesamtaufwand:** $O(n^2)$

#### Heap
- `insert` -> $O(log \: n)$
- `decrease-key` -> $O(m \: log \: n)$
	- bei dichten Graphen $(m>n^2/log \: n)$ längere Laufzeit als Array
	- bei dünnen Graphen $(m \in O(n))$ besser mit Gesamtaufwand
- `delete-min` -> $O(log \: n)$
- **Gesamtaufwand:** $O(n \: log \: n)$
- Fibonacci-Heap
	- automatisch jeweils bessere Komplexität erreicht (egal ob dicht/dünn)