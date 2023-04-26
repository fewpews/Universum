# Modulare Arithmetik

## Restklassen
- Sei $n \in \mathbb{N}, n \geq 1$ 
- Für $k \in \mathbb{Z}$ die Menge $k+n \mathbb{Z}$:
	- $k+n \mathbb{Z} = \{..., k-2n, k-n, k, k+n, k+2n, k+3n,...\}$
		- Beachte: $(k + n \mathbb{Z}) ∩ (l+n \mathbb{Z}) \neq ∅ \iff k + n \mathbb{Z} = l + n \mathbb{Z} \iff n \mid (k − l)$
- Äquivalenzrelation $\equiv (mod \: n)$ 
	- $k \equiv l \: mod \: n \iff k \in l+n \mathbb{Z}$

## Restklassenring $\mathbb{Z}/n \mathbb{Z}$
- Addition:
	- $(k + n \mathbb{Z}) + (l + n \mathbb{Z}) = k + l + n \mathbb{Z}$
- Multiplikation
	-  $(k + n \mathbb{Z}) \cdot (l + n \mathbb{Z}) = k \cdot l + n \mathbb{Z}$
- Ringaxiome gültig
	- *multiplikative Gruppe* in $\mathbb{Z}/n \mathbb{Z}$ besteht aus invertierbaren Elementen $(\mathbb{Z}/n \mathbb{Z})^*$
		- -> *Einheiten* im Ring
### Chinesische Restsatz
-> Folie 20.7
- Für teilerfremde Zahlen $m,n$ ist folgende Abbildung ein **Isomorphismus von Ringen**:
	- $\mathbb{Z}/mn \mathbb{Z} → \mathbb{Z}/m \mathbb{Z} × \mathbb{Z}/n \mathbb{Z}$
	- $x + mn \mathbb{Z} \mapsto (x + m \mathbb{Z}, x + n \mathbb{Z})$
#### Standardanwendung - Gleichzeitige Kongruenzen
-> Folie 20.8
- Gegeben: paarweise teilerfremde Zahlen $m_1,...,m_n$
	- Produkt dieser $n$ Zahlen ist $m$
	- Für jedes $n$-Tupel ganzer Zahlern $x_1,...,x_n$ existiert geanus ein $x \in \{0,...,m-1\}$ sodass $x \equiv x_i \: mod \: m_i$ für alle $i$ erfüllt
#### Verallgemeinerung - Erweiterung auf $n$ Komponenten
- Korollar: paarweise teilerfremde Zahlen $m_1,...,m_n$ mit $m=m_1 \cdot ... \cdot m_n$ ist folgende Abbildung ein **Isomorphismus von Ringen**:
	- $\mathbb{Z}/m \mathbb{Z} → \mathbb{Z}/m_1 \mathbb{Z} × · · · × \mathbb{Z}/m_n \mathbb{Z}$
	- $x + m \mathbb{Z} \mapsto (x + m_1 \mathbb{Z}, . . . , x + m_n \mathbb{Z})$
#### Anwendung
-> Folie 20.9
- unendliche viele Primzahlen

### Wichtige Eigenschaften
-> Folie 19.3
**Satz:**
1. $(\mathbb{Z}/n \mathbb{Z})^∗ = \{k + n \mathbb{Z} \mid ggT(k, n) = 1\}$
2. $\mathbb{Z}/n \mathbb{Z}$ ist Körper, gdw. $n$ ist Primzahl
3. $x \mapsto kx$ auf $\mathbb{Z}/n \mathbb{Z}$ bijektiv, gdw. $ggT(k, n) = 1$

### Zentrales Lemma
-> Folie 20.1ff.
- $m,n$ zwei teilerfremde ganze Zahlen
- Folgende Abbildung $\pi$ ist surjektiv:
	- $π: \mathbb{Z} → \mathbb{Z}/m \mathbb{Z} × \mathbb{Z}/n \mathbb{Z}$
	- $x \mapsto (x + m \mathbb{Z}, x + n \mathbb{Z})$
		- Bei $ggT(m,n) = 1$ zwei gleichzeitige Kongruenzen in $\mathbb{Z}$ immer lösbar:
			- $\forall a,b \in \mathbb{Z} \: \exists x \in \mathbb{Z}$ so dass $x \equiv a \: mod \: m$ und $x \equiv b \: mod \: n$
- Zwischen $\mathbb{Z}/mn \mathbb{Z}$ und $\mathbb{Z}/m \mathbb{Z} × \mathbb{Z}/n \mathbb{Z}$ wird dadurch bijektive Abbildung induziert:
	- $(x \: mod \: mn) \mapsto (x \: mod \: m, x \: mod \: n)$
		- Abbildung bleibt surjektiv und sogar injektiv -> bijektiv
			- wenn auf Zahlen $\{0,...,mn-1\}$ beschränkt

# Beispiel simultane Kongruenz
- Suchen Zahl eine Zahl $x$, sodass gilt $x \equiv y \: mod \: m$ und $x \equiv z \: mod \: n$
- -> $zam+ybn$ 
	- $am +bn = 1$ Euklidischer Algorithmus
- Sei $m=9, n=11$
	- $5m-4n =1$ 
	- Kongruenzen $x ≡ y \: mod \: 9$ und $x ≡ z \: mod \: 11$ durch Zahl $z \cdot 5m - y \cdot 4n$ gelöst
- Wollen wir $x$ mit $x ≡ 3 \: mod \: 9$ und $x ≡ 6 \: mod \: 11$
	- $x = 6 · 45 − 3 · 44 = 270 − 132 = 138$
	- Oder: $mn=99 \rightarrow 138-99=39$ 

## Der kleine Satz von Fermat
-> Folie21.1f.
- Grundlage für viele Primzahltests
- **Satz:** Für alle Primzahlen $p$ und alle $a \in \mathbb{Z}$ gilt:
	- $a^p \equiv a \: mod \: p$
- Falls $a$ und $p$ teilerfremd gilt:
	- $a^{p-1} \equiv 1 \: mod \: p$
### Primzahltest
```
Fermat-Test:

Eingabe: natürliche Zahl n
Frage: Ist n Primzahl

Wähle a ∈ {1,...,n−1} zufällig
Berechne x:=a^{n-1} mod n
Falls x !≡ 1 mod n:
	AUSGABE: n ist keine Primzahl
Sonst keine Aussage
```
#### Eigenschaften
- Wenn $n$ *zusammengesetzte* Zahl
	- Für das gewählte $a$ gilt zufällig auch $a^{n−1} ≡ 1$
	- Für das gewählte $a$ gilt $a^{n−1} \: \not\equiv 1$
#### Durchführung
- bei großen $n$ viele Multiplikationen $(2^n)$
- Größe Zwischenergebnisse auf $mod \: n$ reduzieren
	- $(a + b) \: mod \: n = ((a \: mod \: n) + (b \: mod \: n)) \: mod \: n$ 
	- analog Multiplikation
#### Algorithmus
- Berechnung $a^{n-1}$ im Fermat-Test durch Berechnung von $a^b$ (Input: a,b)
```
e:=1
while b>0 do
	if b ungerade then 
		e:= e·a mod n;
	a:= a^2 mod n;
	b:= _[b/2]_
return e
```
- Schleifeninvariante: Wert $e \cdot a^b$ zu Begin und Ende jedes Durchlaufs gleich
- Inputwert: $a_0, b_0$ -> Schleifeninvariante anfangs Wert $1 \cdot a_0^{b_0}$ 
	- Invariante und am Ende $b=0$  -> Ausgabewert $e = e \cdot a^0 = 1 \cdot a_0^{b_0}$ 
	- **Ausgabe korrekt, Laufzeit logarithmisch, Zwischenwerte klein**

## Anwendung
- Zahlendarstellung moderner Rechner (Bit/Byte)
- Zweierkomplement
- Fehelerkennung bei Artikelnummern (EAN)
- Matrikel-/Ausweis-/Bahn-Card-Nummern
- Prüfsummer beim ISBN-Code
	- Bedingung: $1 · x_1 + 2 · x_2 + · · · + 9 · x_9 + 10 · x_{10} ≡ 0 \: mod \: 11$
- IBAN aus BBAN (BLZ und 10-stellige Kontonummer)

