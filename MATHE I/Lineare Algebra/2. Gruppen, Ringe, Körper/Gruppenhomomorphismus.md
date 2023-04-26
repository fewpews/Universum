# Gruppenhomomorphismus

## Definition: Gruppenhomomorphismus
- Gruppen $G, H$
- Abbildung $f: G \rightarrow H$ heißt **Gruppenhomomorphismus**, wenn
	- $\forall a,b \in G : f(ab) = f(a) \: f(b)$

## Definition: Kern von $f$
- Sei $f : G \rightarrow H$ Gruppenhomomorphismus, $e \in H$
	- $ker(f) := f^{-1}(\{e\}) = \{g \in G \: | \: f(g) = e \}$ ist **Kern** von $f$

## Beispiel 
- $G = \mathbb{R}^2$, komponentenweise Addition, *neutrales Element* $(0,0)$ 
- $f : \mathbb{R}^2 \rightarrow \mathbb{R}$ definiert durch $f(x_1,x_2) := x_1 - x_2$ ein **Gruppenhomomorphismus**
	- $f((x_1, x_2) + (y_1, y_2)) = f(x_1 + y_1, x_2 + y_2) = x_1 + y_1 − x_2 + y_2 = f(x_1, x_2) + f(y_1, y_2)$
- **Urbild** des *neutralen Elements* in $\mathbb{R}$ ist die Diagonale $\{(x, x) \: | \: x ∈ \mathbb{R} \}$
	- -> Untergruppe von $\mathbb{R}^2$

## Satz 2.1.6. 
- Gruppenhomomorphismus $f: G \rightarrow H$
- $f$ bildet *neutrales Element* von $G$ auf *neutrales Element* von $H$ ab
- $ker(f)$ und $Bild(f)$ Untergruppen von $G$ bzw. $H$
	- Beweis ->s.26

