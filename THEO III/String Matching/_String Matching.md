---
cards-deck: 
tags: 
complete: true
aliases: String Matching
linter-yaml-title-alias: String Matching
date: 2022-11-17
mod-date: 2022-12-06
---
# String Matching

## Definition: String-Matching-Problem
- **Gegeben:** Text $T \in \Sigma^n$, Muster(pattern) $P \in \Sigma^m$, wobei $m \leq n$
- **Gesucht:** alle Verschiebungswerte(shifts) $s$ für die gilt:
	- $T[s+1,…,s+m] = P[1,…,m]$
	- alle Vorkommen von $P$ in $T$

## Varianten
- [[Brute-Force]]
- [[Rabin und Karp]]
- [[Endlicher Automat]]
- [[Knuth-Morris-Pratt]]
- [[Boyer-Moore]]

