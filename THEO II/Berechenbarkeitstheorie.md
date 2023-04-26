# Berechenbarkeitstheorie
- prinzipelle Machbarkeit in endlicher Zeit

- Intuitiver Berechenbarkeitsbegriff
- **Mathematisch**: Funktion $f : \mathbb{N}^k \rightarrow \mathbb{N}$ $\Leftrightarrow$ **Algorithmus**
- Grundfunktionen in weitere Funktionen einsetzen -> partielle Funktionen

## Churchsche These
- Die durch die formale Definition der **Turing-Berechenbarkeit** (oder auch WHILE-Berechenbarkeit, GOTO-Berechenbarkeit, $\mu$-Berechenbarkeit) beschriebene **Klasse von Funktionen** stimmt mit der **Klasse der im intuitiven Sinne** berechenbaren Funktionen überein.

## Turing-Berechenbarkeit
### Definition
- $f: \mathbb{N}^k \rightarrow \mathbb{N}$ heißt **Turingberechenbar**, falls es eine DTM $M$ gibt, so dass $f(n_1,...,n_k) = m$ genau dann gilt, wenn $M$, gestartet in ihrem Anfangszustand mit dem $k$-Tupel $n_1,...,n_k$ auf ihrem Band (in Binärdarstellung, mit Trennzeichen zwischen den Komponenten) nach endlich vielen Schritten einen Endzustand erreicht mit Bandinhalt $m$
- Bei undefinierten Wert $m$ läuft sie unendlich/bricht ab

### Beispiele
Dekrement-Funktion:
- $f: \mathbb{N} \rightarrow \mathbb{N}$
- $f(n) = n-1$, falls $n>0$ $f(0) =0$ 
- $f(n) = n \dot{-} 1$ -> **modifizierte Subtraktion**
- **Allgemein:** $a \dot{-} b = max\{0, a-b\}$ 

"Nirgends definierte Funktion" ist Turing-berechenbar:
- $\Omega: \mathbb{N} \rightarrow \mathbb{N}$
- $\Omega(n)$ ist undefiniert für alle $n$
- gibt es für jedes $k$
- Beweis:
	- TM mit $(z_0,x) \rightarrow (z_0,x,R)$ $\forall x$ 

$f: \mathbb{N}^2 \rightarrow \mathbb{N}$
- $f(a,b) = a+b$
$g: \mathbb{N}^2 \rightarrow \mathbb{N}$
- $g(a,b)= a \dot{-} b$
$h: \mathbb{N}^2 \rightarrow \mathbb{N}$
- $h(a,b) = a \cdot b$
$h: \mathbb{N}^2 \rightarrow \mathbb{N}$
- $i(a,b) = \lfloor a/b \rfloor$, falls $b \neq 0$ $i(a,0) = a$
