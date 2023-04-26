# Gruppen

## Definition
- Menge $G$, Verknüpfung $* : G \times G \rightarrow G, \quad (a,b) \mapsto a * b$
- Menge $G$ & Verknüpfung $*$ heißt **Gruppe**, wenn
### Gruppenaxiome
- **(G1)** Verknüfung *assoziativ* 
	- $(a ∗ b) ∗ c = a ∗ (b ∗ c), \quad \forall a, b, c ∈ G$
	- $= a * b * c$
- **(G2)** $\exists$ *neutrales Element* 
	- $\exists e ∈ G \rightarrow \forall a ∈ G : a ∗ e = e ∗ a = a$
- **(G3)** zu jedem Element ein *inverses* Element
	- $\forall a ∈ G \rightarrow \exists b ∈ G : a ∗ b = b ∗ a = e$
- **(G4)** Hat Verknüpfung $*$ Eigenschaft der Kommutativität
	- $\forall a, b ∈ G : a ∗ b = b ∗ a$
	- -> Gruppe $G$ ist ***abelsch/kommutativ***

#### Neutrales Element
- nur ein *neutrales* Element $e$
- $f \in G$ mit $f * a = a$ für alle $a \in G$
- -> $e = f*e = f$
#### Inverses Element
- Für jedes $a \in G$ *inverse* Element $a^{-1}$ eindeutig
- Seien $b, c ∈ G$ mit $b ∗ a = e$ und $a ∗ c = e$
- -> $b = b ∗ e = b ∗ (a ∗ c) = (b ∗ a) ∗ c = e ∗ c = c$

## Beispiel
- Menge $\mathbb{Z}$ mit Verknüfung $+$
	- *assoziativ* -> $(a+b)+c = a+(b+c)$
	- *neutrales* Element -> 0
	- *inverse* Elemente -> negative Zahlen
	- *kommutativ* -> $a+b = b+a$


## Symmetrische Gruppe $Sym(M)$: Gruppe aller bijektiven Abbildungen
- Menge $M$, Verknüfung: Verkettung von Abbildungen 
- $Sym(M) := \{ f : M → M \: | \: f$ ist bijektiv$\}$
	- Beweis -> s.23

- Gruppe aus **Permutationen** (Elemente) von $M$ ($n$-elementige Menge)
- **Grad** der Gruppe $n$
- **Gruppenoperation:** Komposition $\circ$ (Hintereinanderausführung/Verkettung)
- **nichtabelsch/nicht kommutativ** für $2 > n$
- **neutrale Element:** identische Abbildung
- Gruppe ist **endlich** 
- **Ordnung:** $n!$

### Spezialfall $M = \{ 1,2,...,n \}$ 
- -> $Sym(n) := Sym(M)$
- Anzahl Elemente: $n! = 1 * 2 * 3 * ... * (n-1) * n$
- Definition Permutation $Sym(n)$ -> Bilder der Zaheln $1$ bis $n$ einzeln abbilden
	- z.B. $Sym(3)$ -> $1 \mapsto 3, \quad 2 \mapsto 1, \quad 3 \mapsto 2$
	- als Tabelle: erste Zeile Zahlen $1$ bis $n$, zweite Zeile Bilder

#### Würfelgruppe
- Menge alle Drehungen: Abbildungen der Ebenen
- Verknüpfung: Verkettung von Abbildungen
- 24 Elemente $(4!)$

## Fachtermini
#### Verknüpfung/Binäre Operation auf M
- Abbildung $M \times M \rightarrow M$
- weist einem Paar von Elementen aus $M$ wieder ein Element aus $M$ zu
- Beispiel Addition: Paar$(m,n)$ -> Summe $(m+n)$
