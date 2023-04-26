# Eulers φ-Funktion
## Fachtermina
#### Einheit
- ...in einem Ring bezeichnet man ein Element, das ein Inverses bzgl. Multiplikation besitzt

## φ(n)-Funktion
- $φ(n)$ ist die Anzahl der natürlichen Zahlen $k<n$, für die $ggT(k,n) = 1$ gilt
	- multiplikative Grupe $(\mathbb{Z}/n \mathbb{Z})^*$ des Ring $\mathbb{Z}/ n \mathbb{Z}$ besteht aus Einheiten von $\mathbb{Z}/ n \mathbb{Z}$. Ihre Größe ist $φ(n)$

## Beispiele
Werte für $φ(n)$ für $n=2,...,20$:
- φ(2) = 1, φ(3) = 2, φ(4) = 2, φ(5) = 4, φ(6) = 2, φ(7) = 6, φ(8) = 4, φ(9) = 6, φ(10) = 4, φ(11) = 10, φ(12) = 4, φ(13) = 12, φ(14) = 6, φ(15) = 8, φ(16) = 8, φ(17) = 16, φ(18) = 6, φ(19) = 18, φ(20) = 8
- Wenn $n$ Primzahl: alle natürlichen Zahlen $k<n$ teilerfremd zu $n$
- $φ(n) = n − 1 \Leftrightarrow n$ ist Primzahl

## Spezialfälle 
- $φ(n)$ $für $n=pq$ (Produkt zweier Primzahlen)
	- von 1 bis $n-1$ alle Zahlen Teilerfremd zu $n$, außer durch $p$ oder $q$ teilbar
	- $q-1$ Zahlen sind durch $p$ teilbar, $p-1$ Zahlen sind durch $q$ teilbar
	- $φ(pq) = pq − 1 − (q − 1) − (p − 1) = (p − 1)(q − 1)$
- $φ(p^e)$ für eine Primzahl $p$ und $e ≥ 1$
	- $p^e − 1$ Zahlen -> die durch $p$ teilbar, sind nicht teilerfremd zu $p^e$ -> $p^{e−1} − 1$ Zahlen
	- $φ(p^e ) = p^e − p^{e−1} = p^{e−1}(p − 1)$

## Satz von Euler
**Fermat**: alle zu $p$ teilerfremden Zahlen $a$ die Kongruenz $a^{p−1} ≡ 1 \: mod \: p$ erfüllen
**Spezialfall**: $φ(p) = p − 1$
- Für teilerfremde ganze Zahlen $a$ und $n$ gilt: $a^{φ(n)} ≡ 1 \: mod \: n$
**Beweis**
-> Folie 25.5

## Berechnung von $φ(n)$
