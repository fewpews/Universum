---
cards-deck: 
tags: mathe, mathe1, logik
complete: links
aliases: Quantoren und Prädikatenlogik
linter-yaml-title-alias: Quantoren und Prädikatenlogik
date: 2022-10-18
mod-date: 2022-10-18
---
# Quantoren und Prädikatenlogik

## Quantoren
- ∀ Allquantor
- ∃ Existenzquantor
	- ∃! Quantor der eindeutigen Existenz
		- $(\exists^! n \in \mathbb{N}: n^2 = 2n)$
		- $\Leftrightarrow (\exists n \in \mathbb{N}: n^2 = 2n) \wedge (\forall n,m \in \mathbb{N}: (n^2 = 2n \wedge m^2 = 2m) \Leftrightarrow n=m)$

## Funktionssweise
- *Prädikat* + **Quantor** -> *Aussage*
**Warnung:** Tauschen von Quantoren verändert Bedeutung der Aussage

## Fachtermini
#### Prädikat
- Form einer Aussage
- Ausdruck mit Variablen

## Beispiele
“Für alle $m$ aus $M$ ist die Aussage $p(m)$ wahr.”
	$∀m ∈ M : p(m)$

“Es gibt ein $m$ aus $M$ , so dass die Aussage $p(m)$ wahr ist.”
	$∃m ∈ M : p(m)$
