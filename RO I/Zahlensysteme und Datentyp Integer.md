# Zahlensysteme und Datentyp Integer

## Zahlendartstellungen
### 1. Strichmengen
- Sehr aufwändig für große Zahlen
### 2. Römische Zahlen
- Kaum systematische Rechenregeln möglich
### 3. Stellenwertsysteme
= Poliadische Zahlensysteme
- Festlegung einer Basis
	- Basis $B$ 
	- Ziffer(Digit) $𝐶_𝑖:𝐶_𝑖≤𝐵−1;𝐶_𝑖≥0$ 
- Wert an Stelle $i$:
	- Wert der Zahl $𝑍=𝐶_{𝑛−1}∗𝐵^{𝑛−1}+𝐶_{𝑛−2}∗𝐵^{𝑛−2}+…+𝐶_1𝐵^1+𝐶_0∗𝐵^0$

#### Dual/Binärsystem
- bestehend aus zwei Ziffern mit Werten $0$ und $1$ 
- **Bits**: Stellen einer Binärzahl
- Zahl $𝑍=𝐶_{𝑛−1}\cdot 2^{𝑛−1}+𝐶_{𝑛−2}\cdot 2^{𝑛−2}+…+𝐶_1\cdot2^1+𝐶_0\cdot2^0 \quad 𝐶_𝑖=\{0,1\}$ 
- Binär <> Dezimal
	- $(110101.11)_2=32+16+4+1+0.5+0.25=(53.75)_10$
#### Oktales Zahlensystem
- Basis $8$ mit Werten $0,1,2,3,4,5,6,7$
- Jede Stelle entspricht drei Binärwerten
	- kompaktere Schreibweise
#### Hexadezimales Zahlensystem
- Basis $16$ mit Werten $0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F$ 
- Jede hexdezimale Ziffer entspricht vier Binärziffern
	- kompaktere Schreibweise

## Konvertierung von Zahlen zwischen Zahlensystemen
### Dezimal $\rightarrow$ Binär
- Dezimalzahl $N$ in Binärzahl
- Schritte wiederholen bis Differenz $= 0$ 
	- Finden der größten Zweierpotenz
	- Von $N$ subtrahieren $\rightarrow$ positive Differenz $N_1$ 
### Binär $\rightarrow$ Hexadezimal/Oktal
- Unterteilen der binären Zahl in Gruppen von vier/drei Bits, ausgehend vom binären Punkt nach links & rechts
### Hexadezimal/Oktal $\rightarrow$ Binär
- Jede Stelle wird in 4/3-Bit binärisches Equivalent umgewandelt
- Zusätzliche Nullen löschen

### Konvertierung in Fakorisierter Form
- $𝑍=𝐶_{𝑛−1}∗𝐵^{𝑛−1}+𝐶_{𝑛−2}∗𝐵^{𝑛−2}+…+𝐶_1𝐵^1+𝐶_0∗𝐵^0$
- $\rightarrow$ Faktorisierung $\rightarrow$ $𝑍=(((𝐶_{𝑛−1}∗𝐵+𝐶_{𝑛−2})∗𝐵+𝐶_{𝑛−3})∗𝐵+⋯+𝐶_0)$
### Konvertierung mittels Ganzzahldivision
- $𝑍=𝐶_{𝑛−1}\cdot 2^{𝑛−1}+𝐶_{𝑛−2} \cdot 2{𝑛−2}+…+𝐶_1\cdot2^1+𝐶_0 \cdot 2^0$
- $\frac{𝑍}{𝐵}=(𝐶_{𝑛−1}∗𝐵^{𝑛−2}+⋯+𝐶_1)\:𝑅𝑒𝑠𝑡\:𝐶_0$ 

### Dezimal $\rightarrow$ Binär/Oktal/Hexadezimal
Schritte Wiederholen bis **Ergebnis** $=0$ (ohne **Rest**) 
- Zahl durch Basis $r$ Zahlensystems teilen
- **Rest** ist Bit (von rechts nach links)
- neues **Ergebnis** wieder teilen
### Dezimal $\rightarrow$ Binär/Oktal/Hexadezimal
Schritte Wiederholen bis **Ergebnis** $=1.0$
- Zahl mit Basis $r$ multiplizieren
- **Vor dem Punkt:** Bit nach dem Punkt (von links nach Recht)
- **Nach dem Punkt:** neues Ergebnis wieder teilen

## Arithmetische Operationen
- Operationen mit Zahlen der Basis $r$ gelten gleiche Regeln wie für Dezimalzahlen
#### Binäre Addition
- Übertragung wenn Wert größer als $1$
- Übertrag zu nächst höherer Position hinzuaddiert
#### Binäre Subtraktion
- negativer Übertrag in gegebener Spalte addiert 2 zu Minuend-Bit hinzu
![[Pasted image 20230426120657.png]]
#### Binäre Multiplikation
- Wie schriftliche Multiplikation
- Werte entweder $0$ oder $1$ annehmen und entsprechend demnach $0$ oder Multiplikanden

## Komplementbildung

## Darstellung negativer Zahlen

## Alphanumerische Codierung
- Digitale Computer: Umgang/Verarbeitung numerischer/alphanumerischer Daten 
	- Binäre Codierung für die Buchstaben des Alphabets/Numerale/Sonderzeichen/$
### ASCII Character Code
- American Standard Code for Information Interchange
- 128 Zeichen in 7 Bits
	- 94 druckbaren Zeichen
		- 26 Großbuchstaben, 26 Kleinbuchstaben, 10 Numeralen, 32 Sonderzeichen
	- 34 nicht-druckbaren Zeichen
		- Kontrollfunktionen für Umleitung von Datenströmen und Arrangieren&Positionieren 
- Ein Zeichen in einem Byte (meist als 8-Bit (Byte) interpretiert)
	- Zusätzliches Bit für spezifische Anwendungen
![[Pasted image 20230426155930.png|400]]
![[Pasted image 20230426155958.png|400]]
### Unicode
- Industriestandard um verschiedenen gängige Symbole unterschiedlichster Sprachen darzustellen
- Konvertierung nicht mehr nötig
- Liefert eindeutige Nummerierung ("Code Point") und eindeutigen Namen für jedes Zeichen
	- Mehr als eine Millionen Code Points (UTF-8/16/32)
- Notation: "U+" und vier bis sechs hexdezimale Ziffern

## Parity Check
- **Paritätsbit**: Zusätzliches Bit, zeitweise benutzt, um Fehler innerhalb der Datenkommunikation zu finden 
	- Setzt Gesamtzahl der 1-en auf gerade/ungerade
	- gerade Parität häufiger als ungerade

## Gray Code
- Code 