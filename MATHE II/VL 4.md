## Satz 3.20 (Cauchysches Konvergenzkriterium)
- Folge reeler/komplexer Zahlen $(x_n)_{n\in \mathbb{N}}$ konvergiert genau dann, wenn sie eine Cauchy-Folge ist
	- $\forall \varepsilon > 0$ gibt es ein $n_0 \in \mathbb{N}$, so dass $\forall n,m \geq n_0$ gilt:
		- $|x_n - x_m| < \varepsilon$ 
**Vorteil des Cauchykriteriums:** Konvergenz einer Folge beweisen, ohne Limes

# Reihen
## Definition 3.22
- Sei $(a_n)_{n \in \mathbb{N}}$ eine Folge in $\mathbb{R}$/$\mathbb{C}$ 
- $\sum^\infty_{k=1} a_k$ heißt (unendliche) **Reihe** 
	- **Glieder** der Reihe $a_k$
- **Partialsumme:** endliche Summe $s_n = a_1 + a_2 + ... +a_n = \sum^n_{k=1} a_n$ 
- Konvergiert die Folge der Partialsummen $(s_n)_{n \in \mathbb{N}}$ gegen einen Grenzwert $s \in \mathbb{R}/\mathbb{C}$, dann sagt man  $\sum^\infty_{k=1} a_k$ konvergiert und schreibt $\underset{n \rightarrow \infty}{lim} s_n = s =: \overset{\infty}{\underset{k=1}{\sum}} a_k$  
- $(s_n)_{n \in \mathbb{N}}$ kein Grenzwert -> divergente Reihe
### Beispiele
#### Teleskopsumme
#### Geometrische Reihe
- $\overset{\infty}{\underset{k=0}{\sum}} q^k = 1 + q + q^2 + q^3 + ...$ 
- konvergiert gegen $\frac{1}{n-q}$ falls $|q| <1$, sonst divergent
#### Harmonische Reihe
- $\overset{\infty}{\underset{k=1}{\sum}} \frac{1}{k} = 1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + ...$ ist divergent

## Satz 3.24
- Reihe $\overset{\infty}{\underset{k=1}{\sum}} a_k$ sei konvergent
- **Nullfolge:** $(a_k)_{k \in \mathbb{N}}$ konvergiert gegen Null
#### Beweis
Aus dem Cauchy-Kriterium angewandt auf die Folge der Partialsummen $s_n$ folgt insbesondere, dass es ein $n_0 \in \mathbb{N}$ gibt, so dass $|s_{m+1} - s_m| < \varepsilon$ für alle $m \geq n_0$. Es gilt aber: $s_{m+1} - s_m = a_{m+1}$, was zeigt, dass $a_k$ eine Nullfolge ist. $\square$ 

## Hilfssatz 3.26
- Reihe mit nicht negativen Gliedern, für die die Folge der Partialsummen beschränkt ist, ist konvergent
#### Beweis
Da $a_k \geq 0$, gilt $s_n$ ist monoton wachsend, aber folgt der Behauptung aus Satz 3.17 (monoton und beschränkte Folgen sind konvergent). $\square$

## Definition 3.27
Reihe $\overset{\infty}{\underset{k=1}{\sum}} a_k$ heißt **alternierend**, wenn die Folge $(a_k)_{k\in \mathbb{N}}$ wechselnde Vorzeichen besitzt.

## Satz 3.28 (Leibniz-Kriterium)
Sei $(a_k)_{k \in\mathbb{N}}$ eine reele Folge, für die gilt: $a_k \geq 0, a_k \geq a_{k+1}$ und $\underset{k=0}{lim} \: a_k = 0$ 
Dann ist die **alternierende Reihe** $\overset{\infty}{\underset{k=0}{\sum}} (-1)^k a_k$ konvergent.

## Bemerkung 1:
Umordnung von Reihe: $\overset{\infty}{\underset{k=1}{\sum}} (-1)^{k-1} \frac{1}{k} = 1-\frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \frac{1}{5} - ...$ 
Wir ordnen um: 