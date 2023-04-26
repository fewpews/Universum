# Körper

## Definition
- kommutativer Ring mit Eins heißt **Körper** wenn...
	- jedes Element (außer neutrales Element Addition (0)) hat multiplikatives Inverses

## Axiome
**Körper:** Menge $K$, Verknüpfungen $+, \cdot$
- **(K1)** Addition assoziativ
	- $∀a, b, c ∈ K: (a + b) + c = a + (b + c)$
- **(K2)** Es gibt neutrales Element 0 bezüglich Addition
	- $∀a ∈ K: a + 0 = a$
- **(K3)** Zu jedem Element in $K$ ein inverses Element bezüglich Addition
	- $∀a ∈ K ∃b ∈ K: a + b = 0$
- **(K4)** Addition kommutativ
	- $∀a, b ∈ K: a + b = b + a$
- **(K5)** Multiplikation assoziativ
	- $∀a, b, c ∈ K: (a · b) · c = a · (b · c)$
- **(K6)** Es gibt neutrales Element 1 bezüglich Multiplikation
	- $∀a ∈ K: a · 1 = a$
- **(K7)** Zu jedem Element in $K \backslash \{0\}$ ein inverses Element bezüglich Multiplikation
	- $∀a ∈ K ∃b ∈ K: a · b = 1$
- **(K8)** Multiplikation kommutativ
	- $∀a, b ∈ K: a · b = b · a$
- **(K9)** Distributiv gesetz gilt
	- $∀a, b, c ∈ K: a · (b + c) = a · b + a · c$

- Körper $K$ abelsche Gruppe bezüglich Addition
- $K \backslash \{0\}$ abelsche Gruppe bezüglich Multiplikation

## Beispiele
- Körper der rationalen Zahlen $\mathbb{Q}$ , Addition, Multiplikation
	- $\mathbb{Q} = \frac{n}{m} \mid m ∈ \mathbb{Z}, n ∈ \mathbb{N} \setminus \{0\}$
- Körper der reelen Zahlen $\mathbb{R}$ 
- [[Komplexe Zahlen#Körper: Komplexe Zahlen|Komplexe Zahlen ]] $\mathbb{C}$
- Körper $\mathbb{Z}_2$ mit zwei Elementen
	- ![[AdditionsMultiplikationstabelle_KöperZ2.png|300]]

**Gegenbeispiel: Ring der reelen Polynome**
-> s.33

## Satz 2.4.3.
- In einem Körper gibt es keine Nullteiler
- Körper $K$, $a,b \in K$ 
- Falls $ab = 0$
	- $a = 0$ , $b = 0$
