Kapitel 3 Analysis (Grundbegriffe)

# Konvergenz in metrischen Räumen
- Intuitiv: schrittweise Annäherung an ein festes Element
	- Messen wie weit von Grenzelement entfernt
	- -> Abstandsbegriff
		- Durch Einführung der Metrik auf einer Menge $X$ realisiert
		- -> $X$ wird zu metrischem Raum

## Definition 3.1 (Metrik, metrischer Raum)
- Menge $X$ 
- Abbildung $\rho : X \times X \rightarrow \mathbb{R}$ heißt **Metrik** auf $X$, wenn folgende Eigenschaften $\forall x,y,z \in X$ besitzt:
	- **(M1)** $\rho(x,y) \geq 0$ , $\rho(x,y) = 0$, genau dann wenn $x=y$ ist
	- **(M2)** $\rho(x,y) = \rho(y,x)$, d.h. Metrik ist **symmetrisch**
	- **(M3)** $\rho(x,z) \leq \rho(x,y) + \rho(y,z)$, d.h. eine **Dreiecksgleichung** ist erfüllt
- Die Menge $X$, versehen mit einer Metrik $\rho$, heißt **metrischer Raum**

### Beispiele
Euklidischer Abstand im Raum $\mathbb{R}^n$ 
- $\rho_2(x,y) = \sqrt{\sum^n_{i=1} (x_i - y_i)^2} = \parallel x-y \parallel = \sqrt{\langle x-y, x-y \rangle}$ 
- Rechtwinklige Straßen: $\rho_1(x,y) = \sum^n_{i=1} |x_i - y_i |$ 

Maximummetrik:
- $\rho_\infty(x,y) = \underset{n}{max} |x_i - y_i |$ 

Diskrete Metrik auf jeder nichtleeren Menge $X$:
- $d(x,y) = \cases{1, \mathop{falls} x\neq y\cr 0, \mathop{falls} x=y}$
- $X$, versehen mit dieser Metrik heißt **diskreter Raum**


## Definition 3.2
- $x_0 \in X, \varepsilon > 0$ einer reele Zahl
- **Kugelumgebung** mit Radius $\varepsilon$ und Mittelpunkt $x_0$ 
	- $K_\varepsilon(x_0) = \{ x \in X : \rho(x,x_0) < \varepsilon\}$
- Grundlage, um **offene/abgeschlossene** Mengen in einem metrischen Raum zu definieren

## Definition 3.3 (offene/abgeschlossenen Mengen in metrischem Raum)
- Metrischer Raum $X$
- Teilmenge $X_0 \subset X$ ist **offen**, falls zu jedem $x_0 \in X_0$ eine Kugelumgebung von $x_0$ existiert, die in $X_0$ liegt
- $X_0 \subset X$ ist **abgeschlossen**, falls $X \setminus X_0$ offen ist

### Beispiele
Kreis ohne Rand in $\mathbb{R}^2$ 
- $K_1(0) = \{ x \in \mathbb{R}^2 : |x| = \sqrt{x^2_1 + x^2_2} < 1 \}$ 
- offene Menge
Kreis mit Rand
- $\overline{K_1(0)} = \{ x \in \mathbb{R}^2 : |x| = \sqrt{x^2_1 + x^2_2} \leq 1 \}$
- abgeschlossene Menge

## Definition 3.4 (Folge)
- Folge ist eine Abbildung von $\mathbb{N}$ in $X$, so dass jedem $n \in \mathbb{N}$ ein Element $x_n \in X$ zugeordnet wird
	- $(x_n)_{n\in \mathbb{N}}$ 

## Definition 3.5 (Konvergenzbegriff)
-  Folge $(x_n)_{n\in \mathbb{N}}$ aus dem metrischen Raum $X$ konvergiert gegen das Element $x \in X$, falls es zu jedem $\varepsilon > 0$ einen Index $n_0 = n_0(\varepsilon)$ gibt, so dass
	- $x_n \in K_\varepsilon(x) \quad \forall n \geq n_0$
- Element $x$ heißt **Grenzwert** der Folge $(x_n)_{n\in \mathbb{N}}$



bis 3.7 fertig

erkläre mir bitte wie ich die determinante von 3x3 matritzen berechne