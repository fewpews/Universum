# Syntax der Aussagenlogik
## Definition
1. Atomare Formeln ($A_i, i= 1,2,3,...$) sind Formeln
2. *Konjunktion/Disjunktion:* Falls $F$ und $G$ Formeln, dann auch $(F \wedge G)$ und $(F \vee G)$ 
3. *Negation:* Wenn $F$ einer Formel ist, dann auch $\neg F$ 
4. *Teilformel:* Formel $A_i$ -> $A_i$ einzige Teilformel -> induktiv weiter

## Abkürzungen
- Namen ohne Index:
- Implikation $F_1 \rightarrow F_2$ 
	- $(\neg F_1 \vee F_2)$
- Äquivalenz $F_1 \leftrightarrow F_2$ 
	- $((F_1 \wedge F_2 ) \vee (¬F_1 \wedge ¬F_2 ))$
- $n$-faches Oder $\bigvee^n_{i=1} F_i$ 
	- $(. . . ((F_1 \vee F_2 ) \vee F_3 ) · · · \vee F_n )$
- $n$-faches Und $\bigwedge^n_{i=1} F_i$
	- $(. . . ((F_1 \wedge F_2 ) \wedge F_3 ) · · · \wedge F_n )$


# Semantik der Aussagenlogik
#### Belegung
- $D$ sei eine (meist endliche) Teilmenge von $\{ A_1, A_2, A_3,... \}$
- Eine *Abbildung* $\mathcal{A} : D \rightarrow \{ 0,1 \}$ heißt **Belegung**
- Belegung gibt jeder atomaren Formel einen *Wert*

Wert einer atomaren Formel $A_i$ ist genau dann definiert, wenn $A_i \in D$ gilt, und er ist dann $\mathcal{A}(A_i)$ 
Sei $\mathcal{A}(F)$ und $\mathcal{A}(G)$ definiert:
- $\mathcal{A}(F \wedge G)$ sei das Minimum von $\mathcal{A}(F)$ und $\mathcal{A}(G)$ 
	- $\mathcal{A}(F \wedge G ) = 1$ gdw. $\mathcal{A}(F) = 1$ **und** $\mathcal{A}(G) = 1$
	- $\mathcal{A}(F \vee G ) = 1$ gdw. $\mathcal{A}(F) = 1$ **oder** $\mathcal{A}(G) = 1$
	- $\mathcal{A}(¬F ) = 1$ gdw. $\mathcal{A}(F ) = 0$, also nicht $1$


# Darstellung
## Verknüpfungstabellen
$\wedge, \vee, \neg, \rightarrow, \leftrightarrow$
## Baumstrukturen für Formeln
- **Knoten**: atomare Formel als Label
- $\neg F$: Knoten mit $\neg$ als Label und darunter Baum für $F$
- $F \wedge G / F \vee G$: Knoten mit $\wedge / \vee$ als Label und darunter Bäume für $F$ und $G$ 


# Modelle, Gültigkeit, Erfüllbarkeit, Tautologie
Belegung **passend** zu Formel
- $\mathcal{A}$ genau dann **passend** zu $F$, wenn alle in $F$ kommenden atomaren Variablen zum Definitionsbereich von $\mathcal{A}$ gehören
Belegung **Modell** für Formel
- $\mathcal{A}$ genau dann **Modell** für $F$, wenn $\mathcal{A}$ zu $F$ **passend** und $\mathcal{A}(F) = 1$ 
- Wenn $\mathcal{A}$ ein Modell für $F$, dann schreiben wir $\mathcal{A} \models F$ 
$F$ ist **erfüllbar**
- $F$ **erfüllbar**, wenn es ein Modell für $F$ gibt:
	- es existiert eine Belegung $\mathcal{A}$ passend zu $F$ mit $\mathcal{A}(F) =1$
$F$ ist **gültig**
- $F$ **gültig**, falls für alle $\mathcal{A}$ die passend zu $F$ sind, $\mathcal{A}(F)=1$ gilt
**Tautologie**
- eine **gültige** Formel $F$

## Zusammenhang Erfüllbarkeit/Tautologie
### Satz (f2.1)
- $F$ ist Tautologie $\Leftrightarrow$ $\neg F$ ist unerfüllbar
### Das Spiegelungsprinzip
- **gültige** Formeln werden durch Negation zu **unerfüllbaren** Formeln
- Umkehrung gilt auch
- **erfüllbare, nicht gültige** Formeln werden durch Negation zu **erfüllbaren, nicht gültigen** Formeln
- ![[Spiegelungsprinzip.png|300]]


# Wahrheitswerte Verlauf
- Wahrheitswert von $F$ unter Belegung $\mathcal{A}$ hängt nur vom Wahrheitswert der atomaren Formeln in $F$ ab
- Daher sind Erfüllbarkeit/Gültigkeit/ähnliche Eigenfschaften für Formel $F$ **algorithmisch** testbar durch **Wahrheitstafeln**
	- Spalten für $A_1,...,A_n$ und $F$
	- Zeilen für $\mathcal{A}_i$ mit $i =1,...,2^n$ 
- **Problem**: Größe der Tafel 
	- [[NP-Vollständigkeit]]
	- [[Exponentialzeit]]

