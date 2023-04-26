# Matrizen

![[Matrix.png]]
- $n \times m$-**Matrix** in einem Ring $R$ -> $(a_{nm})$
	- rechteckiges Schema von Elementen $a_{nm} \in R$ 
	- $n$ Zeilenindex, $m$ Spaltenindex
- **Menge** der $n \times m$-Matrizen mit Einträgen in $R$ -> $M_{n,m}(R)$

## Matrizenprodukt
- $AB = \sum^n_{k=1} a_{ij}b_{kj}$
	- Matrizen $A,B$ aus selben Ring $R$ 
	- Spaltenanzahl $m$ stimmt mit Zeilenanzahl $n$ überein
- nicht ***kommutativ***
	- $AB \neq BA$
	- 
### Hilfssatz 2.3.2.
->Beweis s.30
- $A ∈ M_{m,n}(R), \quad B ∈ M_{n,p}(R), \quad C ∈ M_{p,q}(R)$
- Matrizenmultiplikation ***assoziativ***
	- $(AB)C = A(BC)$
- ***Distributivgesetze*** gelten
	- $A(B+C) = AB+AC$
	- $(A+B)C = AC+BC$


## Komponentenweise Addition
- $A,B \in M_{n,m}(R)$
	- $A+B$
	- $a_{ij} + b_{ij}$ Eintrag in $i$-ter Zeile / $j$-ter Spalte
- **abelsche** Gruppe, wenn
	- $M_{n,m}(R)$
	- komponenteweise Addition
	- neutrales Element
#### Nullmatrix
![[Nullmatrix.png]]
- *neutrales Elemenet* von Addition

## Quadratische Matrizen
- $n=m$ -> $M_n(R)$ 
- zwei $M_n(R)$ verknüpfen mit Addtion/Multiplikation -> Ring mit Eins
#### Einheitsmatrix $E_n$
![[Einheitsmatrix.png]]
- *neutrales Element / Einselement* von Multiplikation
- Diagonale 1, Rest 0

##### Kronecker-Symbol
![[Kronecker-Symbol.png]]
- $E_n = (δ_{ij})$

## Matrizenring
- Menge $M_n(R)$ der $n \times n$-Matrizen in Ring $R$
- ->bilden selbst Ring
#### Nullteiler
![[Nullteiler.png]]
- falls $n ≥ 2$
- $\exists a, b ∈ M_n(R) : ab = 0$
	- $a,b \neq 0$
