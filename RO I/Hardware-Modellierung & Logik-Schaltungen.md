# Boolsche Algebra
- Schalt-/Mengealgebra
- 3-Tupel $(A,+,\cdot)$
	- Menge $A$
	- $+, \cdot$ :Abbildungen aus $A \times A \rightarrow A$

## Axiome
- Kommutativgesetz
	- **(K1)** $x \cdot y = y \cdot x$
	- **(K2)** $x + y = y+x$
- Distibutivgesetz
	- **(D1)** $x \cdot (y+z) = (x \cdot y)(x \cdot z)$
	- **(D2)** $x + (y \cdot z) = (x+y)(x+z)$
- Neutrale Elemente
	- **(N1)** $x \cdot 1 = x$
	- **(N2)** $x + 0=x$
- Inverse Elemente
	- **(I1)** $x \cdot \bar{x} = 0$
	- **(I2)** $x+ \bar{x} = 1$

## Schaltalgebra vs. Mengenalgebra
|         | Schaltalgebra | Mengenalgebra        |
| ------- | ------------- | -------------------- |
| $A$     | $\{0,1\}$     | $2^T$                |
| $\cdot$ | Konjunktion   | Schnittmenge($\cap$) |
| $+$     | Disjunktion   | Vereinigung($\cup$)  |
| $1$     | $1$           | Trägermenge($T$)     |
| $0$     | $0$           | $\emptyset$          |
| $\bar{x}$        |         $1-x$      |    Komplementärmenge($T\setminus x$)                  |

## Theoreme
- Elimination 
	- **(E1)** $x \cdot 0 = 0$
	- **(E2)** $x+1=1$
- Absorption
	- **(AB1)** $x \cdot (x+y) = x$
	- **(AB2)** $x+(x \cdot y) = x$
- Assoziativgesetz
	- **(A1)** $(x \cdot y) \cdot z = x \cdot (y \cdot z)$
	- **(A2)** $(x + y) + z = x + (y + z)$
- Idempotenz
	- **(ID1)** $x \cdot x = x$
	- **(ID2)** $x+x=x$
- Doppelnegation
	- **(DN)** $\overline{(\bar{x})} = x$
- DeMorgan
	- **(M1)** $\overline{(x+y)} = (\bar{x} \cdot \bar{y})$
	- **(M2)** $\overline{(x \cdot y)} = (\bar{x} + \bar{y})$

## Logik Gatter
- AND / OR / NOT(Inverter)
- NAND / NOR
- XOR / XNOR
#### Beispiel Schaltung
- Bit-Vergleich von zwei Zahlen
	- XNOR pro Bit und ein großes AND

## Hardware-Beschreibungssprache
- HDL = Hardware Description Language
	- VHDL
		- Elemente: inputs/outputs, entity/architecture, logic
		- Kompakte Darstellung mit Vektoren
		- Konzept/Modell der Zeit -> Taktzyklenebene
		- Anweisungen parallel ausgeführt
		- Compiler: Simulation & Synthese
- Vereinfacht Hardware Modellierung
	- Bau von Schaltungen
### Beispiel
- `not/and/or/nand/nor/xor/xnor` -> `F <= not X;`

## Relevante kombinatorische Schaltungen
###  Multiplexer
Definition:
- kombinatorische Schaltung, die binäte Information aus mehreren Eingängen auswählt und an einzige Ausgangsleitung $Y$ übergibt.
- Auswahl wird von bestimmter Eingangsleitung von Steuervariablen $S$ gesteuert
- 2:1 / 4:1 
### Decoder
- Enable-Variable
- 2:4
	- 2 Eingänge in einen der 4 Ausgänge
#### Beispiele
- 1-Bit Binäraddierer
	- 3:8 Decoder in 2 Binär-Ausgänge
- Oktal-nach-Binär-**Codierer**
	- 8 Eingänge in 3 Binär-Ausgänge
### Prioritätscodierer
Definition:
- kombinatorische Schaltung, die Prioritätsfunktion implementiert
- wenn 2 oder mehr Eingänge gleichzeitig Wert 1 annehmen, hat Eingangssignal mit höchsten Priorität Vorrang
- ![[Prioritätscodierer.png|200]]
### 7-Segmentanzeige mit BCD-Eingang
- Segmentdarstellung $a$-$g$
- BCD-Eingang
- Seven-Segment Dekodierer
	- 27 AND-Gatter -> 14 AND-Gatter durch Mehrfachnutzung

## Boolsche Funktionen
### Vereinfachung
- Duale Konsensusregel
	- $(𝑋+𝑌)(\bar{𝑋}+𝑍)(𝑌+𝑍)=(𝑋+𝑌)(\bar{𝑋}+𝑍)$
- Komplement von Funktionen
### Wahrheitstabelle
- Äquivalenzvergleich
### Diagramm Logikschaltung

## CMOS-Logik
Complementary Metal-Oxide-Semiconductor:
- Halbleitebauelemente mit p-Kanal & n-Kanal-Transistoren auf einem gemeinsamen Substrat/Chip
- Verwendeter Halbleiterprozess zur Realisierung von integrierten digitalen Schaltungen
- zwei Arten von Transistoren die als Schalter fungieren
### CMOS-Gatter
- **Pull-Up**-Netzwerk mit P-Transistoren
	- 1 -> Schalter offen
	- Vdd: positive Versogungsspannung
	- $f_P = f_P(x_1',x_2',...,x_{N-1}')$
- **Pull-Down**-Netzwerk mit N-Transistoren
	- 0 -> Schalter offen
	- Gnd: negative Versogungsspannung
	- $f_N = f_N(x_1,x_2,...,x_{N-1})$
- Input/Output
### Funktionen $f_N$ , $f_P$ bestimmen
- $f=f(a,b,c,...)$
	- $f_P(x_1',x_2',...)=f(\bar{a},\bar{b},\bar{c},...)$ 
		- Schalter im Pull-Up-Netzwerk geschlossen falls $x_i'=1$
		- P-Kanal Transistoren kurzgeschlossen falls $\bar{a},\bar{b},\bar{c},...=1$
	- $f_N = \bar{f}(a,b,c,...)$
#### Beispiel: NAND-Gatter: $f=\overline{a \cdot b}$
- $f_P=f(\bar{a},\bar{b})=\overline{\bar{a},\bar{b}}$
- $f_P = a +b$
	- Parallelschaltung
- $f_N= \bar{f}(a,b)= \overline{\overline{a \cdot b}}$
- $f_N=a \cdot b$
	- Reihenschaltung

## Halbaddierer - Volladdierer
![[HalbaddiererVolladdierer.png|400]]

## Terme und Normalformen
### Definitionen - Terme
- **Produktterm**
	- einfache Variablen oder **Konjunktion** mehrerer (ggf. negiert)
- **Summenterm**
	- einfache Variablen oder **Disjunktion** mehrerer (ggf. negiert)
- **Minterm**
	- **Produktterm**, in dem **jede Variable** einer booleschen Funktion **genau einmal** vorkommt
- **Maxterm**
	- **Summenterm**, in dem **jede Variable** einer booleschen Funktion **genau einmal** vorkommt
- **Summe von Produkten**
	- einzelner Produktterm oder Disjunktion mehrerer
- **Produkt von Summen**
	- einzelner Summenterm oder Konjunktion mehrerer
- **Disjunktive Normalform DNF**
	- eindeutige Darstellung boolescher Funktion $f$
	- Disjunktion aller **Minterme** $m$ mit $f(m)=1$
- **Konjunktive Normlform KNF**
	- eindeutige Darstellung boolescher Funktion $f$
	- Disjunktion aller **Maxterme** $M$ mit $f(M)=1$
- **Minimale Summe**
	- Wiederholte Anwendung von Axiomen/Theoremen
	- Karnaugh-Diagramme
	- Algorithmische Minimierung

## Karnaugh-Diagramme
- Wachsen exponentiell mit der Problemgröße
