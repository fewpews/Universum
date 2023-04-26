# Äquivalenz aussagenlogischer Formeln
- Formeln syntaktisch verschieden aber das gleiche bedeuten -> **semantische Äquivalenz**
## Definition
- $F$ und $G$ heißen **semantisch äquivalent**, wenn für alle zu beiden passenden Belegungen $\mathcal{A}$ gilt:
	- $\mathcal{A}(F) = \mathcal{A}(G)$
- Wir schreiben $F \equiv G$ ($F$ äquivalent zu $G$

## Ersatzbarkeitstheorem
### Satz (f2.7)
- Sei $H$ eine Formel, in der $F$ als Teilformel vorkommt
- Sei $G$ eine zu $F$ äquivalente Formel
- Sei $H'$  die Formel die aus $H$ entsteht, wenn $F$ durch $G$ ersetzt
- Dann sind $H$ und $H'$ äquivalent

## Äquivalenzen (f.3.2)
Idempotenz
- $F \equiv (F \wedge F ) \equiv (F \vee F )$
Kommutativität
- $(F \wedge G) \equiv (G \wedge F)$
- $(F \vee G) \equiv (G \vee F)$
Assoziativität
- $((F \wedge G) \wedge H) \equiv (F \wedge (H \wedge H))$
- $((F \vee G ) \vee H) \equiv (F \vee (G \vee H))$
Absorption
- $(F \wedge (F \vee G )) \equiv F \equiv (F \vee (F \wedge G ))$
Distributivität
- $(F \wedge (G \vee H)) \equiv ((F \wedge G ) \vee (F \wedge H))$
- $(F \vee (G \wedge H)) \equiv ((F \vee G ) \wedge (F \vee H))$
Doppelnegation
- $\neg \neg F \equiv F$
deMorgan-Regeln
- $¬(F \wedge G ) \equiv (¬F \vee ¬G )$
- $¬(F \vee G ) \equiv (¬F \wedge ¬G )$
Tautologie
- Falls $F$ Tautologie, gelten folgende Äquivalenzen
	- $(F \vee G ) \equiv F$
	- $(F \wedge G ) \equiv G$
Unerfüllbarkeit
- Falls $F$ unerfüllbar, gelten folgende Äquivalenzen
	- $(F \vee G ) \equiv G$
	- $(F \wedge G ) \equiv F$

### Assoziativität und Klammerung
- Klammerungen bei zusammengesetzten Formeln einfach weglassen

