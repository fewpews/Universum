---
cards-deck: 
tags: mathe, zahlenmengen, induktion
complete: true
aliases: 1. Natürliche Zahlen und vollständige Induktion
linter-yaml-title-alias: 1. Natürliche Zahlen und vollständige Induktion
date: 2023-04-12
mod-date: 2023-04-26
---
# 1. Natürliche Zahlen und vollständige Induktion
$\mathbb{N} = \{1,2,3,…\}$

## Definition 1.1 (Peano-Axiome)
Axiomsystem, dass $\mathbb{N}$ charakterisiert
- Natürlichen Zahlen bilden Menge auf Abbildung $f$, die jedem $n \in \mathbb{N}$ einen Nachfolger zuordnet
	- $f: \mathbb{N} \rightarrow \mathbb{N}$
- und folgende Eigenschaften besitzt:
	- $\bf{(\mathbb{N} 1)}$ $∃ !1 ∈ N : 1 \notin f (N)$
		- Es existiert genau eine natürliche Zahl (1), die nicht der Nachfolger einer natürlichen Zahl ist
	- $\bf{(\mathbb{N} 2)}$ Abbildung $f$ ist *injektiv*, d.h. $f(n) = f(m) \Rightarrow n=m$
	- $\bf{(\mathbb{N} 3)}$ Ist $M \subseteq \mathbb{N}$ eine Teilmenge, dann gilt $M = \mathbb{N}$, wenn:
		- **a)** $1 \in M$ (n+1)
		- **b)** $n \in M \Rightarrow f(n) \in M$
		- (Induktionsaxiom)
- Können auch mit 0 beginnen: $\mathbb{N}_0 =\mathbb{N} \cup \{0 \}$

## Satz 1.2 (Beweisprinzip der vollständigen Induktion)
Für $n \in \mathbb{N}$ sei $A = A(n)$ eine Menge. Es gelte:
1. $A(1)$ ist wahr (**Induktionsanfang**)
2. Für alle $n$ gilt: Ist $A(n)$ wahr, dann folgt auch, dass $A(n+1)$ wahr ist. (**Induktionsschritt**)
3. Dann ist auch $A(n)$ wahr $\forall n \in \mathbb{N}$ (**Induktionsschluss**)
#### Beweis
- Ist eine Folgerung von $\bf{(\mathbb{N} 3)}$
- Sei $M= \{n \mid A(n) \: ist \: wahr\}$. Dann sind die Eigenschaften **a)** und **b)** in $\bf{(\mathbb{N} 3)}$ für $M$ erfüllt.
- Also gilt nach $\bf{(\mathbb{N} 3)}$ $M= \mathbb{N}$.

## Beispiele:
### Z.z.: Es sei $q \neq 1$. Dann gilt für alle $n \in \mathbb{N} \quad q^0 +q^1 +q^2 +…+q^n = \frac{1-q^{n-1}}{1-q}$
Beweis: $A(n)$ soll die obige Formel sein
- **IA** $n=1$
	- links $q^0 + q^1 = 1+q$
	- rechts $\frac{1-q^2}{1-q}$
	- Also $A(1)$ wahr
- **IS** $n \rightarrow n+1$
	- $A(n) : 1 + q + q^2 +…+ q^n = \frac{1-q^{n+1}}{1-q}$
	- …
	- $A(n) \Rightarrow A(n+1)$
	- *Alternativer Beweis*: $(q^0 + q^1 +…+ q^{n-1} + q^n)(1-q) = 1-q^{n+1}$ ("Teleskopsume")