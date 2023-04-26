# Landau-Symbole
- Klassen von Funktionen
## Definition
Seien $f, g : \mathbb{N} → \mathbb{R}^+ = \{r \:|\: r ∈ \mathbb{R}, r ≥ 0\}$ Funktionen
- $f ∈ O(g) \Leftrightarrow \underset{n→∞}{lim \: sup} \: \frac{f(n)}{g(n)} < ∞$   (größter Häufungspunkt)
- $f ∈ o(g) \Leftrightarrow \underset{n→∞}{lim} \: \frac{f(n)}{g(n)} = 0$
- $f ∈ Ω(g) \Leftrightarrow \underset{n→∞}{lim \: inf} \: \frac{f(n)}{g(n)} > 0$   (kleinster Häufungspunkt)
- $f ∈ ω(g) \Leftrightarrow \underset{n→∞}{lim} \: \frac{f(n)}{g(n)} = ∞$
- $f ∈ Θ(g) \Leftrightarrow f ∈ O(g) \wedge f ∈ Ω(g)$   (genau einen Häufungspunkt)

Alternative:
Seien $f, g : \mathbb{N} → \mathbb{R}^+$ Funktionen
- $f ∈ {\bf O(g)} \Leftrightarrow ∃c > 0, ∃n_0 ∀n ≥ n_0 : f (n) ≤ c · g(n)$
- $f ∈ {\bf o(g)} \Leftrightarrow ∀c > 0, ∃n_0 ∀n ≥ n_0 : f (n) ≤ c · g(n)$ 
- $f ∈ {\bf Ω(g)} \Leftrightarrow ∃c > 0, ∃n_0 ∀n ≥ n_0 : f (n) ≥ c · g(n)$
- $f ∈ {\bf ω(g)} \Leftrightarrow ∀c > 0, ∃n_0 ∀n ≥ n_0 : f (n) ≥ c · g(n)$
- $f ∈ {\bf Θ(g)} \Leftrightarrow f ∈ O(g) \cap f ∈ Ω(g)$

Umgangsprachlich:
- $f ∈ O(g) \Leftrightarrow f$ wächst asymptotisch höchstens so schnell wie $g$
- $f ∈ o(g) \Leftrightarrow f$ wächst asymptotisch echt langsamer als $g$  
- $f ∈ Ω(g) \Leftrightarrow f$ wächst asymptotisch mindestens so schnell wie $g$  
- $f ∈ ω(g) \Leftrightarrow f$ wächst asymptotisch echt schneller als $g$  
- $f ∈ Θ(g) \Leftrightarrow f$ wächst asymptotisch genauso schnell wie $g$