# Primitive Rekursion
## Induktive Definition: Was ist primitiv rekursiv?
- Konstante Funktionen
- Projektionen (Bestimmte Variable aus Menge wählen)
- $s : \mathbb{N} \rightarrow \mathbb{N}$ mit $s(n) = n + 1$
- Funktionen durch Einsetzen aus primitiv rekusiven Funktionen
- Funktionen durch primitive Rekursion aus primitiv rekursiven Funktionen
- **Defintion**:
	- $f(0, x_1 , . . . , x_k ) = g(x_1 , . . . , x_k )$  
	- $f(n + 1, x_1 , . . . , x_k ) = h(f (n, x_1 , . . . , x_k ), n, x_1 , . . . , x_k )$
	- $g : \mathbb{N}^k \rightarrow \mathbb{N}, h : \mathbb{N}^{k+2} \rightarrow \mathbb{N},$ beide prim.rek. $\Rightarrow f : \mathbb{N}^{k+1} \rightarrow \mathbb{N}$ prim.rek.

## Prinzip
->Folie 10.2
### Addition
$add:\mathbb{N}^2 \rightarrow \mathbb{N}$:
- $g(x) =x$ und $h(z,n,x) =s(z)$
	- $h(z,n,x) = s(\pi^3_1(z,n,k))$
		- $\pi^3_1$: Von 3 Stellen auf die 1. projektieren
		- $g=\pi^1_1$
	- $f(0,y) = g(y) =y$
	- $f(n,y) = n+y$
	- $f(n+1,y) = h(f(n,y),n,y) = s(f(n,y)) = f(n,y) +1 = n+1+y$ 

### Multiplikation
$g(x) = 0$ und $h(z,n,x) = add(z,x)$ -> was kommt raus?
- $h= add(\pi^3_1, \pi^3_3)$ 
- $f(0,y) = g(y) = 0$ 
- $f(n+1,y) = h(f(n,y),n,y) = f(n,y) +y$
	- $f(x,y) = x*y$ 

### Dekrement
- $g() = 0$ und $h(z,n) = n$ 

### Modifizierte Subtraktion

### Weitere Beispiele:
unter geeigneter Verwendung von Projektion/Einsetzung primitiv rekursiv realisierbar
- **Identifikation** von Variablen:
	- $f(x_1,...,x_k)$ primitiv rekursiv
	- $g(x_1,...,x_{k-1}) = f(x_1,...,x_{k-1},x_{k-1})$ dann auch $g$ primitiv rekursiv
- **Fiktive** Variablen:
	- $f(x_1,...,x_k)$ primitiv rekursiv
	- $g(x_1,...,x_k,x_{k+1}) = f(x_1,...,x_k)$ dann auch $g$ primitiv rekursiv
- **Vertauschte** Variablen:
	- $f(x_1,...,x_k)$ primitiv rekursiv
	- $g(x_1,...,x_k) = f(x_1,...,x_{k-2},x_k,x_{k-1})$ dann auch $g$ primitiv rekursiv
- Einsetzen mit **verschiedenen** Variablen

## Bijektion $\mathbb{N}^2 \rightarrow \mathbb{N}$
Funtion $f: \mathbb{N} \rightarrow \mathbb{N}$ mit $f(n) = \binom{n}{2}$ ist primitiv rekursiv
- $f(0) = 0$
- $f(n+1) = f(n) + n$
Also auch $c: \mathbb{N}^2 \rightarrow \mathbb{N}$ primitiv rekursiv
- $c(x,y) = \binom{x+y+1}{2} +x$ 
- $c$ ist Bijektion
	- verwenden um $k$-Tupel zu codieren
### Kodierung von $k+1$-Tupeln
- $c:\mathbb{N}^2 \rightarrow \mathbb{N}$ sei bijektive Kodierung von Paaren
#### Tupel bilden:
- **Tripel:** $c_3 (x_1 , x_2 , x_3 ) = c(x_1 , c(x_2 , x_3 ))$ 
- **Quadrupel:** $c_4 (x_1 , x_2 , x_3 , x_4 ) = c(x_1 , c_3(x_2 , x_3 , x_4 ))$
- **$k+1$-Tupel:** $c_{k+1}(x_1 , ... , x{k+1}) = c(x_1 , c_k(x_2 , ... , x{k+1} ))$
	- Jede Funktion durch Einsetzen einer primiv rekursiven Funktion in die primitiv rekursive Funktion $c$ entstanden -> alle primitiv rekursiv
#### Umkehrungen $e,f: \mathbb{N} \rightarrow \mathbb{N}$:
- $e(c(x,y)) = x$ und $f(c(x,y)) = y$
##### Beschränkte Operatoren
- Sei $P: \mathbb{N} \rightarrow \mathbb{N}$ eine Funktion mit $im(P) = \{0,1\}$
	- $P$ ist **Eigenschaft** und identifizieren $P(x)$ mit $P(x) = 1$
**Beschänkter Max-Operator:**
- $q(n) = max\{x \leq n \mid P(x)\}$
	- Wenn $P$ primitiv rekursiv, dann auch $q$
**Beschränkter Existenz Operator:**
- $Q(n) = 1$, falls $x \leq n$ existiert mit $P(x)$
- $Q(n) = 0$, sonst
	- Wenn $P$ primitiv rekursiv, dann auch $Q$
##### Funktionen $e$ und $f$
->Beweis Folie 10.8
Wir definieren:
- $e(n) = max\{x \leq n \mid \exists y \leq n : c(x, y ) = n\}$ -> primitv rekursiv
- $f(n) = max\{y \leq n \mid \exists x \leq n : c(x, y ) = n\}$ -> primitiv rekursiv
Folgerung aus Bijektivität von $c$
- $c(x, y ) = n \Leftrightarrow e(n) = x \wedge f (n) =y$ 