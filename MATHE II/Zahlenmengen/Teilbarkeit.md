---
cards-deck: 
tags: mathe, ggT, teibarkeit
complete: true
aliases: Teilbarkeit
linter-yaml-title-alias: Teilbarkeit
date: 2023-04-23
mod-date: 2023-04-26
---
# Teilbarkeit
## Definition 1.3
Sei $n \in \mathbb{Z}, m \in \mathbb{Z}$.
- Die Zahl $m$ heißt **Teiler** von $n$ ($m | n$), wenn gilt:
	- $\exists k \in \mathbb{Z} : km=n$
Es gilt:
- Die Zahl $0$ ist durch alle $m \in \mathbb{N}$ teilbar
- Gilt $m|n_1$ und $m|n_2$,, dann folgt $m|(n_1+n_2)$

## Definition 1.4
Sei $a \in \mathbb{Z}$.
- Die Menge alle Teiler von $a$ ist $D(a) := \{d \in \mathbb{N} : d|a \}$
Seien $a,b \in \mathbb{Z}$.
- Die Menge aller gemeinsamen Teiler von $a$ und $b$ ist $D(a,b) := D(a) \cap D(b)$
Die Zahl $ggT(a,b) := max(D(a,b))$ heißt größter gemeinsamer Teiler von $a$ und $b$
### Beispiel
- $D(30) = \{1, 2, 3, 5, 6, 10, 15, 30\}$
- $D(24) = \{1, 2, 3, 4, 6, 8, 12, 24\}$
- $D(30, 24) = D(30)∩D(24) = \{1, 2, 3, 6\}$
- $ggT(30, 24) = 6$

## Berechnung des größten gemeinsamen Teilers
### Teilen mit Rest
- $a,b \in \mathbb{N}$ und $a>b$
- Dann gibt es $q \in \mathbb{N}$ und $r \in \mathbb{N}_0$
	- $q =qb + r$
- mit $0 \leq r < b$
### Hilfssatz
Seien $a,b \in \mathbb{N}$ und $a = qb +r$. Dann gilt:
- $D(a,b) = D(b,r)$ und $ggT(a,b) = ggT(b,r)$
#### Beweis
…

### Euklidischer Algorithmus zur Berechnung von ggT(a,b)
Starte mit $(a,b)$
1. Teste, ob $b|a$
2. Falls ja: $D(a,b) = D(b)$ und $ggT(a,b)=b$, stop
3. Falls nein: Teile mit Rest $a=qb +r$ ($0<r<b$), zurück zum Anfang mit $(b,r)$

![[ggT.png|300]]
