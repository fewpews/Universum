# Vektorräume
## Definition
- **Vektorraum** über Körper $K$ / $K$-**Verktorraum**
	- Menge $V$ mit Addition $+$ eine abelsche Gruppe 
	- weitere Abbildung $K \times V \rightarrow V, \quad (\lambda, v) \mapsto \lambda \cdot v$
		- ***Skalarmultiplikation***, folgende Eigenschaften gelten...
		- **(V1)** $∀λ, μ ∈ K \quad ∀v ∈ V : (λ · μ) · v = λ · (μ · v)$
		- **(V2)** $∀λ, μ ∈ K \quad ∀v ∈ V : (λ + μ) · v = λ · v + μ · v$
		- **(V3)** $∀λ ∈ K \quad ∀v,w ∈ V : λ · (v + w) = λ · v + λ · w$
		- **(V4)** $∀λ ∈ K \quad ∀v,w ∈ V : λ · (v + w) = λ · v + λ · w$

## Weitere geltende Aussagen
- Nullelement $0 = 0 \cdot v$
	- zweite $0$ im Körper $K$
- $(−λ)v = −(λv) = λ(−v)$ für alle $λ ∈ K, v ∈ V$
- $0 = \lambda \cdot 0$
	- $0 \in V$ 

## Fachtermini
#### Vektoren
- Elemente der Menge $V$
#### Skalare
- Elemente des Körpers $K$ 

## Beispiel
- Menge $K^n$ der $n$-Tupel von Zahlen aus $K$
	- komponentenweise Addition
	- Skalarmultiplikation
		- $λ · (x_1, . . . , x_n) := (λx_1, . . . , λx_n)$
- $\mathbb{R}^3$ dreidimensionalen Anschauungsraum, $\mathbb{R}^2$ Zeichenebene
	- komponenteweise Addition
		- anschauliche Vektoraddition, Hinteraeinandersetzen von Vektorpfeilen
	- Skalarmultiplikation eines Vektors $v$ mit reelen Zahl			- zentrische Streckung von $v$ um Faktor $\lambda$ 

- Menge $V$ der reelen Funktionen
	- $V := \{f : \mathbb{R} → \mathbb{R}\}$ 
		- $\{f : \mathbb{R} → \mathbb{R}\}$ Menge der Abbildungen
	- Addition punktweise
		- $(f + g)(t) := f(t) + g(t)$
	- Skalarmultiplikation punktweise
		- $(λ · f)(t) := λf(t)$
