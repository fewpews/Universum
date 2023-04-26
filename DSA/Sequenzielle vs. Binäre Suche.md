---
type: summarizing
tags: search
status: 
aliases: 
date: 2022-07-12
mod date: 2022-07-12
---
# Vergleich der Suchverfahren
| Verfahren | 10 | 10^2 | 10^3 | 10^4 |
| --------------------------------------------- | --- | ---- | ---- | ---- |
| [[DSA/Sequenzielle Suche\|Sequenziell]] (n/2) | 5 | 50 | 500 | 5000 |
| [[DSA/Binäre Suche\|Binär]] (log_2 n) | 3,3 | 6,6 | 9,9 | 13,3 |

-> Aufwand binäre Suche geringer
	- vor allem für große n
-> #TeileUndHerrscheGrundsatz
	- Rekursion
	- hier einfach durch Iteration
-> Lohnt sich [[DSA/Binäre Suche|binäre Suche]] für kleine n?
	- Abhängig von Sprache/Compiler & Rechenarchitektur
	- keine pauschale Antwort
	- [[DSA/Sequenzielle Suche|Sequenzielle Suche]] kann deutlich effizienter sein
-> [[DSA/Binäre Suche|Binäre Suche]] benötigt sortierte Folge
	[[Sortieralgorithmen]]
