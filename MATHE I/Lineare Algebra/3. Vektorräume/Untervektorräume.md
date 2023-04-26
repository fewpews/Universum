# Untervektorräume
## Definition
- $K$-Vektorraum $V$ 
- nichtleere Teilemenge $U \subseteq V$ heißt **Untervektorraum** von $V$,  wenn abgeschlossen unter Addition/Multiplikation mit beliebigen Skalaren
	- **(UV1)** $\forall v,w \in U$ ist Summe $v+w$ wieder Element von $U$
	- **(UV2)** Für alle Vektoren $u \in U$ und alle Körperelemente $\lambda \in K$
		- $\lambda u \in U$

## Weitere geltende Aussagen
- Untervektorraum $U \subseteq V$ mindestens ein Element $v$ von $V$ 
	- (UV2) mit $0 \cdot v = 0$ -> Nullelement von $V$ in $U$ 
	- $\{0\} \subseteq V$ kleineste Untervektorraum
- $V$ selbst ist Untervektorraum von $V$

## Beispiel
- Untervektorraum in $V := \mathbb{R}^3$ 
	- $xy$-Ebene $U := \{(x,y,0) \mid x,y \in \mathbb{R}\}$
		- nicht leer
		- Abgeschlossen unter Addition/Multiplikation mit beliebigen Skalaren
		- Jede Gerade in $\mathbb{R}^2$ wäre Untervektorraum von $\mathbb{R}$

## Satz 3.2.2.
- Vektorraum $V$, $\{U_j \mid j \in J \}$ Menge von Untervektorräumen von $V$
	- Schnittmenge $\bigcap_{j \in J} U_j$ wieder Untervektorraum von $V$
	- Vereinigung nicht
- ->Beweis s.37

