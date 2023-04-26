# RSA-Verfahren
- Rivest, Shamir, Adleman
- asymmetrisches Verschlüsslungsverfahren

## Prozess
### Vorbereitung Empfänger
- Wähle große Primzahl $p$ und $q$ mit $p<q$
- Berechnen $n = p \cdot q$
- Setze $φ(n) = (p − 1)(q − 1)$, wähle $e > 1$ mit $ggT(e, φ(n)) = 1$ ([[Euklidischer Algorithmus]])
- Berechne Zahl $s<n$ mit $e \cdot s \equiv 1 \: mod \: φ(n)$
-> Paar $(n,e)$ öffentlichen, $p,q,s$ geheim
### Verschlüsseln: Nachricht Sender
- Zahl $x$ im Bereich $\{0,...,n-1\}$
- Berechne $y= x^e \: mod \: n$ ([[schnelle Exponentation]])
- Sende $y$ über beliebigem Kanal zum Empfänger
### Entschlüsseln: Nachricht Empfänger
- Berechne $x' = y^s \: mod \: n$, gehe von $x=x'$ aus
	- d.h. Nachricht korrekt entschlüsselt, $(x^e)^s\: mod \: n = x$ gilt

## Korrektheit 
- Zeigen, dass $(x^e)^s\: mod \: n = x$ gilt
- Da $p, q$ teilerfremd: 
	- $(x^e)^s\: mod \: p = x$ und $(x^e)^s\: mod \: q = x$
	- Beide Behauptungen nach selben Muster beweisen -> $mod \: p$ beweisen genügt
### Beweis:
- Falls $x$ durch $p$ teilbar:
	- $(x^e)^s ≡ 0 \: mod \: p$ gilt
	- Aber auch $x ≡ 0 \: mod \: p$
- Wenn $x$ nicht durch $p$ teilbar:
	- $ggT(x,p)=1$
	- Nach [[Fermats kleinem Satz]] folglich $x^{p−1} ≡ 1 \: mod \: p$
	- Daraus folgt $(x^e)^s = x^{es} = x^{1+k(p−1)(q−1)} = x · (x^{p−1})^{k(q−1)} ≡ x · 1^{k(q−1)} ≡ x \: mod \: p$
- Auf gleiche Weise erhalten wir auch $(x^e)^s ≡ x \: mod \: q$
- Da $p,q$ teilerfremd und $n= p \cdot q$ -> $(x^e)^s ≡ x \: mod \: n$
- Korrektheit der Entschlüsslung nachgewiesen

## Sicherheit
- Drei Probleme, deren Lösbarkeit dazu führen, dass nicht sicher
	- Faktorisiere $n$
	- Berechne $φ(n)$
	- Finde $s$ mit $e \cdot s = 1 \: mod \: φ(n)$
- Nicht klar wie komplex 
	- Aber effiziente Lösungen einer Aufgabe -> ebenso effiziente Lösung der anderen beiden
		- Wenn man $n$ faktorisiern kann -> Kenntnis von $p$ und $q$ -> leicht $φ(n) = (p-1)(q-1)$ berechnen
		- Wenn man $φ(n)$ finden kann -> Wert $p + q = n − φ(n) + 1$ berechnen -> daraus $p,q$ und im Anschluss wieder $s$ rekonstruieren
		- Kenntnis von $s$ reicht, um $n$ zu faktorisieren und $φ(n)$ zu berechnen
- Für $n$ in Größenordnung $2^{2000}$ alle drei Probleme praktisch unlösbar -> 300-stellige Primzahlen

## Beispiel
**Vorbereitung Empfänger**
- $p = 11, q=13 \Rightarrow p<q$
-  $n = 11 \cdot 13 = 143$
- $φ(n) = (11-1)(13-1) = 120$ und wähle $e>1$
	- 1. Versuch: $e=21 \rightarrow ggT(21,120) = 3$
	- 2. Versuch: $e=7 \rightarrow ggT(7,120)=1$
- Euklidischer Algorithmus:
	- $7 \cdot 103 = 721 = 1 \: mod \: 120$ daraus folgt $s=103$
-> Paar $(143,7)$ öffentlich
**Nachricht 42 verschlüsseln**
- $42^7 \: mod \: 143$
- $42 · 42 = 1764 ≡ 334 ≡ 48 \: mod \: 143$ 
- $48 · 48 = 2304 ≡ 874 ≡ 16 \: mod \: 143$ 
- $42^7 ≡ 16 · 48 · 42 = 48 · 672 ≡ 48 · 100 = 4800 ≡ 510 ≡ 81$
**Nachricht 81 entschlüsseln**
- $y^s \: mod \: 143$
- $81^{103} = 3^{412} = 3^{27·15} · 3^7 = (3^{15})^{27} · 9 · 243 ≡ 9 · 100 = 900 = 6 · 143 + 42 ≡ 42$
	- Zwischenrechnung: $3^{15} = (3^5)^3 = 243^3 ≡ 100^3 = 1000^2 ≡ (−1)^2 = 1 \: mod \: 143$
