# Spann und Linearkombinationen

## Definition: Spann/Aufspann
- Sei Vektorraum $V$, Teilmenge $M \subseteq V$ 
- Spann/Aufspann ist Schnittmenge aller Untervektorräume die $M$ enthalten

## Weitere geltende Aussagen
- Spann einer Teilmenge $M \subseteq V$ ist kleinster Untervektorraum von $V$ der Teilmenge $M$ enthält
- $M \subseteq span(M)$
- Spann der leeren Menge ist $\{0\}$

## Beispiel
- Sei $V = \mathbb{R}^2$, $M$ Vereinigung der $x$-Achse mit $y$-Achse
	- $M$ enthält jeden Vektor $(x,0)$ / $(0,y)$ $x,y \in \mathbb{R}$ 
	- $span(M)$ als Untervektorraum von $\mathbb{R}^2$ enthält jede Paar $(x,y)$
	- $span(M) = \mathbb{R}^2$

## Definition: Linerarkombination
- Sei Vektorraum $V$, $v_1,...,v_n$ endlich viele Vektoren in $V$
- **Linerakombination** der Vektoren $v_1,...,v_n$
	- $λ_1v_1 + . . . + λ_nv_n$
	- mit ***Koeffizienten*** $λ_1, . . . , λ_n ∈ K$
- ***Triviale Linearkombination*** der $v_1,...,v_n$
	- alle *Koeffizienten* gleich $0$

## Weitere geltende Aussagen
- **Linearkombination** über null Elemente ist eine leere Summe
	- ***Nullvektor***

## Hilfssatz 3.3.3.
- Sei Vektorraum $V$, Teilmenge $M \subseteq V$
- Menge alle **Linearkombinationen** gebildet über endliche Teilemenge $M$ $\{λ_1v_1 + . . . + λ_nv_n \mid n ∈ N ∪ \{0\}, v_1, . . . , v_n ∈ M, \quad λ_1, . . . , λ_n ∈ K\}$
	- Untervektorraum von $V$ 
- ->Beweis s.39

## Satz 3.3.4.
- Sei Vektorraum $V$, Teilmenge $M$
- Teilmenge $span(M) \subseteq V$ besteht aus allen **Linearkombinationen** $λ_1v_1 + . . . + λ_nv_n$ 
	- mit $n ∈ N ∪ \{0\}, v_1, . . . , v_n ∈ M, \quad λ_1, . . . , λ_n ∈ K$
- ->Beweis s.39

- Aus dem Satz folgt
	- $span(\{v\}) = \{λ_v \mid λ ∈ k\} = K \: v$ 
		- für jeden Vektor $v \in V$
