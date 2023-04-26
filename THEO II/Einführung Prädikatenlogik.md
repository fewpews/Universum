# Pradikatenlogik

## Grundbegriffe der Prädikatenlogik
Einschränkungen der Aussagenlogik:
- **Für alle** Objekte einer gewissen Art gilt...
- **Es gibt** ein Objekt einer gewissen Art mit...
- **Funktionen** und **Relationen**
-> Prädikatenlogik

Drei Sorten von Objekten:
- **Variable** hat die Form $x_i$ für ein $i \in \{ 1,2,... \}$
- **Prädikatsymbol** hat die Form $P^k_i$ für ein $i \in \{ 1,2,...\}$ und ein $k \in \{0,1,2,...\}$
- **Funktionssymbol** hat die Form $f^k_i$ für ein $i \in \{ 1,2,...\}$ und ein $k \in \{0,1,2,...\}$
	- $i$ ist (Unterscheidungs-)Index, beliebige Anzahl dieser Objekte
	- $k$ ist Stelligkeit/Stellenzahl von $P^k_i$ bzw. $f^k_i$

## Syntax der Prädikatenlogik
### Definition: Menge der Terme
- **Variablen** sind Terme
- Wenn $f$ ein $k$-stelliges Funktionssysmbol ist und $t_1,...,t_k$ Terme sind, dann ist auch $f(t_1,..., t_k)$ ein **Term**
	- Nullstellige Funktionssymbole auch Terme -> **Konstanten**
### Definition: Menge der Formeln
- Wenn $P$ ein $k$-stelliges Prädikatsymbol ist und $t_1,...,t_k$ Terme sind, dann ist $P(t_1,...,t_k)$ eine **atomare Formel**
- Mit $F$ und $G$ sind auch $\neg F, (F \wedge G)$ und $(F \vee G)$ **Formeln**
- Ist $F$ eine Fomel und $x$ eine Variable, dann sind auch $\exists xF$ und $\forall xF$ Formeln
	- Teilformel, gebundene/freie Variablen, geschlossene Formel, Aussage, Matrix

## Semantik der Prädikatenlogik
### Struktur
Prädikatenlogische Formeln interpretieren wir mit einer Struktur
- **Zweck**: benutzten Variablen/Funktionssymbolen/Prädikatsymbolen realen Sinn zuordnen
	- **Individuen**: mögliche Werte für Variablen/Terme
	- Zurordnung der Funktions-/Prädikatsymbole zu realen Funktionen/Prädikaten

- Paar $\mathcal{A} = (U_\mathcal{A}, I_\mathcal{A})$ -> **Struktur**
	- $U_\mathcal{A}$ heißt **Menge der Individuen**
	- $I_\mathcal{A}$ ist eine **Abbildung**, die jedem (in der Formel benutzten) Prädikatensymbol $P^k_i$ / Funktionssymbol $f^k_i$ ein/e dazu **passende/s** Prädikat/Formel zuordnet, sowie jeder benutzten Variable $x_i$ einen Wert aus $U_\mathcal{A}$

- Durch Paar $\mathcal{A} = (U_\mathcal{A}, I_\mathcal{A})$ können nun allen Termen **Werte aus $U_\mathcal{A}$** zugewiesen werden wie folgt:
	- Eine (freie) Variable $x_i$ erhält den Wert $I_\mathcal{A}(x_i)$
	- Ein Term der Form $f^k_i(t_1,...,t_k)$ erhält den Wert $I_\mathcal{A}(f^k_i)(u_1,...,u_k)$ wenn die $t_i$ jeweils den Wert $u_i$ haben
		- Wert des Terms $t$ in der Struktur $\mathcal{A}$ bezeichnen wir mit $\mathcal{A}(t)$ -> $\mathcal{A}(t) \in U_\mathcal{A}$ für alle Terme $t$

### Beispiel Strukturen/Werte von Termen
- gegebene Formel wie z.B. $F = \forall x \exists y \exists y' ((P(x, y ) \wedge P(x, y' )) \wedge \forall z(¬P(x, z) \vee (Q(y , z) \vee Q(y', z)))$
- Individuenbereich $U_\mathcal{A}$: häufig $\mathbb{N}$, muss aber nicht
- Durch $I_\mathcal{A}$ müssen alle freie Variablen/Prädikate/Funktionen definiert werden

- $U_\mathcal{A} = V$ für einen ungerichtete Graphen $G = (V,E)$
- $I_\mathcal{A}(P) = P^\mathcal{A} = \{ (u, v ) \mid u, v \in V$ und $\{ u, v \} \in E \}$ -> Kantenrelation
- $I_\mathcal{A}(Q) = Q^\mathcal{A} = \{ (u, u) \mid u \in V \}$ -> Gleichheit

## Wahrheitswerte von Formeln
- atomare Formel $F = P(t_1,...,t_k)$ ist *wahr*, falls $(\mathcal{A}(t_1),...,\mathcal{A}(t_k)) \in P^\mathcal{A}$ gilt
	- wir schreiben $\mathcal{A}(F) = 1$ oder wenn F *nicht wahr* $\mathcal{A}(F) = 0$
- Definitionen von $\mathcal{A}(\neg F), \mathcal{A}(F \wedge G)$ und $\mathcal{A}(F \vee G)$ analog zur [[Einführung Aussagenlogik#Semantik der Aussagenlogik|Aussagenlogik]]

- Ist $F = \forall x G$, so definieren wir $\mathcal{A}(F)$ so:
	- $\mathcal{A}(F) = 1$, falls für alle $\alpha \in U_\mathcal{A}$ gilt: $\mathcal{A}_{[x/ \alpha]}(G) = 1$
	- $\mathcal{A}(F) = 0$, sonst
- Ist $F = \exists x G$, so definieren wir $\mathcal{A}(F)$ so:
	- $\mathcal{A}(F) = 0$, falls für alle $\alpha \in U_\mathcal{A}$ gilt: $\mathcal{A}_{[x/ \alpha]}(G) = 0$
	- $\mathcal{A}(F) = 1$, sonst
- $\mathcal{A}_{[x/ \alpha]}$ ist die Struktur, die überall mit $\mathcal{A}$ übereinstimmt, nur für $x$ gilt jetzt $\mathcal{A}_{[x/ \alpha]} (x) = \alpha$, unabhängig vom ursprünglichen Wert $\mathcal{A}(x)$ 

### Zahlenbeispiel
- Formel $F = \forall x P(x, f (x)) \wedge Q(g (a, z))$
	- Grundbereich $\mathbb{N}$
	- $<$-Relation $P$
	- Primzahleigenschaft $Q$
	- Nachfolgerfunktion $f$ auf $\mathbb{N}$
	- Addition $g$
	- Konstante $a = 2$
		- $a$ ist nullstellige Funktion mit Wert $2$
	- geben Variable $z = 3$
- Interpretation:
	- Für alle Zahlen $x$ gilt: $x < x +1$, und die Summe von $a$ und $z$ ist eine Primzahl
- $F$ wahr?
	- $x < x+1$ ist richtig
	- Summe von $2$ und $3$ ist eine Primzahl
	- -> Formel unter gegebenen Interpretation **wahr**

### Abstraktes Beispiel (f.4.7)

## Modelle, Gültigkeit, Erfüllbarkeit
Struktur $\mathcal{A} (U_\mathcal{A}, I_\mathcal{A})$ ist eine zu $F$ **passende Struktur**, falls $I_\mathcal{A}$ jeder/m in $F$ vorkommenden
- Variablen einen Wert aus $U_\mathcal{A}$ zuweist
- Prädikatensymbol $P^k_i$ ein $k$-stelliges Prädikat über $U_\mathcal{A}$ zuweist
- Funktionssymbol $f^k_i$ eine $k$-stellige Funktion auf $U_\mathcal{A}$ zuweist

Eine zu $F$ passende Struktur $\mathcal{A}$ nennen wir **Modell für $F$**, wenn der Wahrheitswert der Formel in der Struktur $\mathcal{A}$ der Wert $1$ ist -> $F$ gilt in $\mathcal{A}$ -> $\mathcal{A} \models F$ 

- Eine prädikatenlogische Formel $F$ heißt **erfüllbar**, wenn es ein Modell für $F$ gibt
- Eine prädikatnelogische Formel $F$ heißt **allgemeingültig**, wenn alle zu $F$ passenden Strukturen Modelle für $F$ sind -> $\models F$ 
	- Wenn $F$ **nicht allgemeingültig** -> $\nvDash F$ 
