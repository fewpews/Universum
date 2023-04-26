---
cards-deck: 
tags: 
complete: true
aliases: Abbildungen
linter-yaml-title-alias: Abbildungen
date: 2022-10-24
mod-date: 2022-10-25
---
# Abbildungen

## Definition
- Mengen $A, B$ ; Relation $F \subseteq A \times B$
- Relation $F$ heißt **Abbildung/Funktion** von $A$ nach $B$, wenn $∀x ∈ A : ∃^!y ∈ B: (x, y) ∈ F$ gilt
	- zu jedem $x \in \mathbb{R}$ genau ein $y \in \mathbb{R}$

## Prinzip: *Zuordnungsvorschrifft*
- jedem Element $x$ aus $A$ ein eindeutiges bestimmtes aus $B$ zuordnet
- $F: A \rightarrow B$
	- $F(x)$ (eindeutig aus $B$) in Relation mit $x \in A$

## Fachtermini
#### "Wert von F bei x / Bild des Elements x"
- $F(x)$
#### "x wird auf y abgebildet"
- $x \mapsto y$
- es gilt $y = F(x)$
#### "Urbild von y"
- $x \in A$ mit $F(x) = y$ ist **Urbild** von $y$
	- Menge $A$ -> *Definitionsbereich* von $F$
	- Menge $B$ -> *Bild-/Wertebereich* von $F$
#### Bild
- $Bild(F) := {y ∈ B \:|\:∃x ∈ A: F(x) = y}$
	- **Bild** der Abbildung $F$
- $Bild(F) = B$ -> Abbildung $F$ ***surjetkiv*** (Gleichung/Funktion lösbar)
	- wenn jedes $y \in B$ mindestens ein **Urbild** hat
#### Bild der Teilmenge M
- $M \subseteq A$
- $F(M) := {y ∈ B \: | \: ∃x ∈ M: F(x) = y}$
- es gilt $Bild(F) = F(A)$
#### Urbild der Teilmenge N
- $N \subseteq B$
- $F^{−1}(N) := {x ∈ A \: | \: F(x) ∈ N}$
- es gilt $F^{−1}(B) = A$
- einelementige Teilmenge {$y$} von $B$
		- **Urbild** $F^{−1}(y)$ höchstens ein EIement
	- -> Abbildung ***injektiv***
#### bijektiv (eindeutig lösbar)
- -> ***injektiv*** und ***surjektiv***
- wenn $F: A \rightarrow B$ **bijektiv**
	- -> *Umkehrabbildung* (eindeutig bestimmt) $F^{-1}/G: B \rightarrow A$
	- $G$ mit $G(F(a)) = a$ für alle $a \in A$ und $G(F(b)) = b$ für alle $b \in B$
#### Mächtigkeit $|M|$
- Anzahl der Elemente endlicher Menge
- ***gleichmächtig***
	- zwei Mengen, wenn *bijektive* Abbildung zwischen ihnen
- **Mächtigkeit** $M$ ***größer gleich*** von $N$
	- *surjektive* Abbildung $M \rightarrow N$
#### Identische Abbildung
- Menge $X$
- $id_X : X → X, x \mapsto x$
- jedes Element auf sich selbst abbildet
#### Verkettung
- Abbildungen $F: A → B$ und $G: B → C$
- $G ◦ F : A → C, \quad a \mapsto G(F(a))$
	- Verkettung von $G$ und $F$
- nicht *kommutativ*
	- $f, g : R → R$ definiert durch $f(x) = x^2, g(x) = x + 1$
	- Dann gilt $(f ◦ g)(x) = x^2 + 2x + 1$, aber $(g ◦ f)(x) = x^2 + 1$
- *assoziativ*
	- Abbildungen $F : A → B, \quad G: B →C, \quad H: C → D$
	- $(H ◦ G) ◦ F = H ◦ (G ◦ F)$
		- $a \in A$
			- Links: $((H ◦ G) ◦ F)(a) = (H ◦ G)(F(a)) = H(G(F(a)))$
			- Rechts: $(H ◦ (G ◦ F))(a) = H((G ◦ F)(a)) = H(G(F(a)))$
#### Einschränkung
- Abbildung $f : M → N, \quad A ⊆ M$
	- $f|_A : A → N, \quad f|_A(a) := f(a)$
	- *Einschräkung* der Abbildung $f$ auf $A$
- Einschränkung injektiver Abbildung ist

## Satz
- $F ◦ id_A = F$ und $id_B ◦ F = F$
