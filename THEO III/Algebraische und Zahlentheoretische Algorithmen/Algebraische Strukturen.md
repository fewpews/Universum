# Algebraische Strukturen

## Halbgruppen und Monoide
- Menge $M$, zweistellige Verknüpfung $\circ$ 
- $\circ : M \times M \rightarrow M, \quad (m,n) \mapsto \circ(m,n) / m \circ n$

$(M, \circ)$ bildet **Halbgruppe**, wenn
- $\circ$ assoziative Verknüpfung

Halbgruppe $(M, \circ)$ bildet **Monoid** $(M, \circ, e)$, wenn
- neutrales Element $e \in M$ existiert
	- $a \circ e = e \circ a = a$ für alle $a \in M$

## Gruppen
**Gruppe** $(G, \circ, e)$, wenn
- Monoid für jedes Element ein *beidseitiges Inverses* enthält
- **Gruppenaxiome:**
	- $\circ : G × G → G , \quad (g_1, g_2) \mapsto g_1 \circ g_2$
	- $(g_1 \circ g_2) \circ g_3 = g_1 \circ (g_2 \circ g_3)$ für alle $g_1, g_2, g_3 ∈ G$
	- $g \circ e = e \circ g = g$ für alle $g ∈ G$
	- Für jedes $g ∈ G$ gibt es ein $h ∈ G$ mit $g \circ h = h \circ g = e$
- **Kommutative/Abelsche Gruppe**, wenn
	- $g \circ h = h \circ g$ für alle $g , h ∈ G$

## Ringe
**Ring** $R$, wenn
- *additive* Gruppe mit neutralem Element $0$ 
	- *abelsche* Gruppe $(R,+,0)$ 
	- und Monoid $(R, \cdot, 1)$
	- und Distributivgesetze
		- $a · (b + c) = a · b + a · c$
		- $(a + b) · c = a · c + b · c$

## Körper
**Körper** $K$, wenn
- *kommutativer* Ring
	- Multiplikation kommutativ bei Ring
		- $a · b = b · a$ für alle $a, b$
- Menge $K \setminus \{0\}$ mit Multiplikation bildet Gruppe
	- für jedes $a ∈ K \setminus \{0\}$ gibt es ein Inverses $b ∈ K \setminus \{0\}$, so dass $a · b = b · a = 1$ gilt

## Unterstrukturen
- algebraische Struktur $X$ 
- Teilmenge $Y \subseteq X$ **Unterstruktur**, wenn
	- $Y$ geforderten Struktureigenschaften von $X$ hat
- Untergruppen, Untermonoide, Unterhalbgruppen, Unterringe, Unterkörper

## Homomorphismen
- ist *strukturerhaltende Abbildung*
#### Beispiel: Monoid-Homomophismus
- Abbildung $φ$ von Monoid $(M_1, \circ_1, e_1)$ in Monoid $(M_2, \circ_2, e_2)$
- und $φ(m \circ_1 m′) = φ(m) \circ_2 φ(m′)$ und $φ(e_1) = e_2$ gilt

- **Analog:** Gruppenhomomorphismen, Ringhomomorphismen, Körperhomomorphismen

#### Spezielle Eigenschaften
- **Monomorphismus**
	- injektiver Homomorphismus
- **Epimorphismus**
	- surjektiver Homomorphismus
- **Isomorphismus**
	- bijektiver Homomorphismus
