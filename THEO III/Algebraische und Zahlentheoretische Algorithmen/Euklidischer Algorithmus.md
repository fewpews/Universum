# Euklidischer Algorithmus
- ermittlen des größten gemeinsamen Teilers (ggT)

## Algorithmus
```
function ggT(m,n)
begin
	if m=0 then return n
	else return ggT(n mod m,m) fi
end
```
### Korrektheit
- ``ggT(n mod m,m) = ggT(m,n)``
### Termination
- da Zahlen rekursiv immer kleiner werden

## Beispiel
```
ggT(171,68):
171 = 2 · 68 + 35  
68 = 1 · 35 + 33  
35 = 1 · 33 + 2  
33 = 16 · 2 + 1  
2 = 2 · 1 + 0

Variante mit negativen Zahlen:
171 = 3 · 68 − 33  
68 = 2 · 33 + 2  
33 = 16 · 2 + 1  
2 = 2 · 1 + 0
-> ggT(171,68) = 1

ggT(210,78):
210 = 2 · 78 + 54  
78 = 1 · 54 + 24  
54 = 2 · 24 + 6  
24 = 4 · 6 + 0
-> ggT(210,78) = 6
```

## Lemma von Bézout
->Folie 18.3f.
- Für alle $m,n \in \mathbb{Z}$ existieren $a,b \in \mathbb{Z}$, so dass
	- $ggT(m,n) = am+bn$

## Eindeutige Primfaktorzerlegung
-> Folier 18.5f.
- Folge aus Bézout's Lemma:
	- $ggT (n, m_1) = 1 ∧ ggT (n, m_2) = 1 ⇒ ggT (n, m_1m_2) = 1$
**Satz:**
- Sei $n \in \mathbb{N}$ und $n>0$. Dann lässt sich $n$ eindeutig darstellen als
	- $n = \prod_ {p \: Primzahl} p^{n_p}$
- Dabei ist $n_p \neq 0$ genau dann, wenn $p$ Teiler von $n$ ist

