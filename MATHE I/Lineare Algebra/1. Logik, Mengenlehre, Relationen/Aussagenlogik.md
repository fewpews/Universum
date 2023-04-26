---
cards-deck: MATHE I test::Lineare Algebra::1. Logik, Mengenlehre, Relationen
tags: mathe, mathe1, logik
complete: links
aliases: Aussagenlogik
linter-yaml-title-alias: Aussagenlogik
date: 2022-10-18
mod-date: 2022-10-18
---

# Aussagenlogik

## Definition
- einzelne Aussagen miteinander Verknüpfen
- *aussagenlogische Formeln* bestehend aus *Elementaraussagen*(=Bausteine)

## Junktoren
- ( $\neg$ Negation )
- $\land$ Konjunktion
- $\lor$ Disjunktion
- $\Rightarrow$ Implikation ($(p \Rightarrow q)\Leftrightarrow((\neg p) \lor q)$ -> indirekter [[Beweise|Beweis]])
- $\Leftrightarrow$ Äquivalenz ("gleichwertig")

## Fachtermini
#### Allgemeingültigkeit / Tautologie
- Aussagenlogische Formel immer wahr
- Beweis der Äquivalenz mit Wahrheitstabelle
	- Bei $n$ beteiligten Elementaraussagen, $2^n$ Fälle abzudecken
#### Aussage
- sprachliches Gebilde
- Wahrheitswert: w(=wahr) oder f(=falsch)
- Entscheidbarkeit Wahrheitswert irrelevant

## Allgemeingültige aussagenlogische Formeln
*-> Satz 1.1.1.*
#### Doppelte Verneinung
- $¬(¬p) ⇔ p$
#### De Morgansche Regeln
- a) $¬(p ∨ q) ⇔ (¬p) ∧ (¬q)$
- b) $¬(p ∧ q) ⇔ (¬p) ∨ (¬q)$
#### Distributivgesetze
- a) $p ∨ (q ∧ r) ⇔ (p ∨ q) ∧ (p ∨ r)$
- b) $p ∧ (q ∨ r) ⇔ (p ∧ q) ∨ (p ∧ r)$

## Weitere Grundrechenregeln
#### Assoziativgesetz
- $(A \cap B) \cap C \Leftrightarrow A \cap (B \cap C)$
#### Kommutativgesetz
- $A \cap B \Leftrightarrow B \cap A$

## Weitere logische Grundregeln
- $A \vee \neg A \Leftrightarrow true, \quad A \wedge \neg A \Leftrightarrow false$
- $true \vee A \Leftrightarrow true, \quad false \vee A \Leftrightarrow A$
- $true \wedge A \Leftrightarrow A, \quad false \wedge A \Leftrightarrow false$