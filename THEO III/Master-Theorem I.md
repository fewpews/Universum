# Master-Theorem I

- bei rekursiven Algorithmen Abschätzung der Laufzeit in meisten Fällen nur mit rekursiver Gleichung

## Satz:
- Für reelle Zahlen $a > 0, b> 1$ und eine Funtkion $g: \mathbb{N} \rightarrow \mathbb{N}$ mit $g \in \Theta(n^c)$ gelte
	1. $t(1) = g(1)$
	2. $t(n) = a * t(n/b) + g(n)$
- Dann gilt:
	- $(i) \: t(n) \in \Theta(n^c)$        falls $a < b^c$
	- $(ii) \: t(n) \in \Theta(n^c \: log \: n)$        falls $a=b^c$
	- $(iii) \: t(n) \in \Theta(n^{(log \: a)/(log \: b)})$        falls $a > b^c$

## Anwendung
### Mergesort
- $g(n) = n, \quad T(n) = 2* T(n/2) + n, \: also \quad a=b=2, c=1$
- Fall $(ii)$ mit $c =1$
- **Laufzeit** $T(n) = \Theta(n \: log \: n)$
### Multiplikation
- $T(n) = 3 * T(n/2) + 2, \: also \quad a=3, b=2, c=1$
- Fall $(iii)$ ->  **Laufzeit** $T(n) \in \Theta(n^d)$ mit $d = log_2 \: 3 \approx 1.59$

## Beweis
-> Folie 7.4 ff.