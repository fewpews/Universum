# Optimale Klammerung

## Problem
- Berechnen Produkt von $k$ Matrizen $M_1 * ... * M_k$
	- $M_i$ ist eine $(n_{i-1} \times n_i)$-Matrix $(i=1,...,k)$
- Optimale Ausführungsreihenfolge **(=Klammerung)** gesucht
	- wegen Assoziativgesetz
	- möglichst wenige *Skalarmultiplikationen*

- einzelne Matrixmultiplikation
	- $M$ sei $(l \times m)$-, $N$ sei $(m \times n)$-Matrix
	- dann $l * m * n$


### Beispiel
- $M_1 * M_2 * M_3 \: (k=3)$
- Dimensionen $(10 \times 2), (2 \times 8), (8 \times 3)$
	- $(M_1 * M_2) * M_3$ -> 400 skalare Multiplikationen
	- $M_1 * (M_2 * M_3)$ -> 108 skalare Multiplikationen

### Plan Algorithmus
- Tabelle mit $k$ Zeilen und $k$ Spalten
![[algorithmus_klammerung_entwurf.png]]
### Pseudo-Code
![[algorithmus_klammerung_pseudo.png]]

### Beispiel Anwendung
- $M_1 * M_2 * M_3 * M_4$
	- Dimensionen $(3\times 2), (11 \times 5), (5 \times 7), (7 \times 2)$
- Ergebnis
![[alorithmus_klammerung_beispiel.png|400]]
- Optimale Klammerung
	- $M_1 * (M_2 * (M_3 * M_4))$
