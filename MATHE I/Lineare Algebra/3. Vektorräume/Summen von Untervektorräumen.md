# Summen von Untervektorräumen

## Definition
- Seien $U_1,U_2, . . .U_k$ Untervektorräume von $V$
- **Summe der Untervektorräume** $U_1,U_2, . . .U_k$ 
	- $U_1 + U_2 + . . . + U_k := span(U_1 ∪ U_2 ∪ . . . ∪ U_k)$
	- besteht aus allen Vektoren $v$ in $V$
		- $v = u_1 + u_2 + . . . + u_n, \quad u_1 ∈ U_1, u_2 ∈ U_2, . . . , u_n ∈ U_n$

## Beispiel
- $\mathbb{R}^3$
- Untervektorräume $U_1 := span((1, 0, 0)), \quad U_2 := span((0, 1, 0)), \quad U_3 := span((1, 1, 0))$
- $U_1 + U_2 + U_3 = \{(x, y, z) ∈ \mathbb{R}^3 \mid z = 0\}$

## Definition: Diretkte Summe
- Seien $U_1,U_2, . . .U_k$ Untervektorräume von $V$
- ***Direkte Summe*** $U$ von $U_1,U_2,...U_k$
	- - $U = U_1 ⊕ U_2 ⊕ . . . ⊕ U_k$
	- jeder Vektor auf *genau eine* Weise als Summer darstellen lässt
		- $u_1 + u_2 + . . . + u_n, \quad u_1 ∈ U_1, u_2 ∈ U_2, . . . , u_n ∈ U_n$

## Satz 3.4.5.
->Beweis s.41
- Seien $U_1,U_2$ Untervektorräume von $V$
- Summe $U = U_1 + U_2$ direkt, wenn...
	- **(i)** $U = U_1 + U_2$
	- **(ii)** $U_1 ∩ U_2 = \{0\}$
- nicht für 3 oder mehr Vektorräume