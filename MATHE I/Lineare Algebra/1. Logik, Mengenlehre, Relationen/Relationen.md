---
cards-deck: 
tags: mathe mathe1,
complete: false
aliases: Relationen
linter-yaml-title-alias: Relationen
date: 2022-10-18
mod-date: 2022-10-25
---
# Relationen

## Definition
- Relation über $A$ und $B$ -> Teilmenge des kartesischen Produkts $A \times B$
- Beziehung zwischen einem Element von $A$ und einem von $B$
	- $(a, b)$ in Relation enthalten -> "$a$ und $b$ stehen in Relation"

## Äquivalenzrelationen
### Definition 1.4.1.
- Menge $M$, Relation $R$ auf $M \times M$
- $a,b \in M$ stehen in Relation -> $a \sim b$
- ***Äquivalenzrelation***, wenn
	- (Ä1) **Reflexivität**: $∀a ∈ M: a ∼ a$
	- (Ä2) **Symmetrie**: $∀a, b ∈ M: a ∼ b ⇒ b ∼ a$
	- (Ä3) **Transitivität**: $∀a, b, c ∈ M: (a ∼ b ∧ b ∼ c) ⇒ a ∼ c$

## Äquivalenzklasse
- $[x] := {y ∈ M \: | \: y ∼ x}$

## Satz 1.4.2.
- Menge $M$, Äquivalenzrelation $\sim$ auf $M$
- Menge der *Äquivalenzklassen* ${[x] \: | \: x ∈ M}$ bilden *disjunkte* Zerlegung/Partition von $M$
- es gilt $M = \bigcup_{x∈M}[x]$
	- zwei Äquivalenzklassen stimmen überein oder leere Schnittmenge (disjunkt)

Umgekehrt:
- $\{M_j | j ∈ J\}$ *disjunkte* Zerlegung einer Menge $M$
	- falls $j \neq k$ und $M = \bigcup_{j \in J} M_j$ 
	- gilt $M_j ∩ M_k = ∅$
- Äquivalenzrelation auf $M$
	- $x ∼ y ⇔ ∃j ∈ J : x, y ∈ M_j$
##### Beweis 1.4.2. (s.16f)

## Restklassen
- Menge $M = \mathbb{Z}, \quad p \in \mathbb{N}$
- Relation $n \sim m$ genau dann wenn $n - m$ durch $p$ teilbar
- Äquivalenzklassen dazu -> **Restklassen**
	- $p=2$ hat 2 Restklassen gerade & ungerade Zahlen

## Fachtermini
#### disjunkt
- leere Schnittmenge
#### Abbildung
- zu jedem $x \in \mathbb{R}$ genau ein $y \in \mathbb{R}$