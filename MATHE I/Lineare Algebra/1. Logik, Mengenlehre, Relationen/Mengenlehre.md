---
cards-deck: 
tags: mathe, mathe1, mengen
complete: links
aliases: Mengenlehre
linter-yaml-title-alias: Mengenlehre
date: 2022-10-18
mod-date: 2022-10-18
---
# Mengenlehre

## Operatoren für/auf Mengen
- $∈ ,\notin$ Element von…
- $\emptyset {}$ , {} leere Menge
- $\subseteq ,\subsetneq$ (echte) Teilmenge

### $Pot(M)$ Potenzmenge
- $Pot(M) := \{ A | A \subseteq M \}$
- $M$ hat $n$ Elemente -> $Pot(M)$ hat $2^n$ Elemente
### *Schnittmenge*
- $A ∩ B := \{x ∈ A | x ∈ B\}$
- $\bigcap_{i\in I} A_i$
### *Vereinigung*
- $A ∪ B := \{x | x ∈ A ∨ x ∈ B\}$
- $\bigcup_{i\in I} A_i$
### *Komplement*
- $A \backslash B := \{x ∈ A | x \notin B\}$
### *Kartesisches Produkt*
- $A × B := \{(a, b) | a ∈ A, b ∈ B\}$
- $A_1 × A_2 × . . . × A_n := \{(a_1, a_2, . . . , a_n) | a_1 ∈ A_1, a_2 ∈ A_2, . . . , a_n ∈ A_n\}$

## Beispiele: Mengen
- natürliche Zahlen $\mathbb{N}$, ganze Zahlen $\mathbb{Q}$, rationale Zahlen $\mathbb{R}$
- $Pot(\{1, 2, 3\}) = \{∅, \{1\}, \{2\}, \{3\}, \{1, 2\}, \{1, 3\}, \{2, 3\}, \{1, 2, 3\}\}$
- $\{0, 1\} × \{3, 6, 9\} = \{(0, 3), (0, 6), (0, 9), (1, 3), (1, 6), (1, 9)\}$
- $\mathbb{R}_3 = \mathbb{R} × \mathbb{R} × \mathbb{R}$ , Menge aller geordneten Tripel reeler Zahlen

## Fachtermini
#### Menge
- wohldefinierte Gesamtheit von **Objekten/Elementen** (auch Mengen)
- endlich/unendlich
- keine Duplikate
- keine Menge aller Mengen
- Definieren durch *Aufzählung/Aussonderung*

#### Russelsche Antinomie
- Menge aller Mengen, die sich nicht selbst als Element enthalten
- $R = \{X ∈ M | X \notin X\}$ liefer Wiederspruch
- Gesamtheit aller Mengen ist selbst keine wohldefinierte Menge
