# Normalformen
- **positives Literal** ist eine atomare Formel
- **negatives Literal** ist Negation einer atomaren Formel
## Definition
- Eine Formel $F$ ist in *disjunktiver Normalform* (DNF), wenn sie eine **Disjunktion** von **Konjunktionen** von Literalen ist.
- Eine Formel $F$ ist in *konjunktiver Normalform* (KNF), wenn sie eine **Konjunktion** von **Disjunktionen** von Literalen ist

## Satz (DNF/KNF) (f.3.5)
- Zu jeder Formel $F$ existieren äquivalente Formeln in DNF und KNF

## KNF-Algorithmus
1. Negationen nach *innen* schieben (deMorgan) und dabei Doppelnegationen eliminieren
2. Zweites Distributivgesetz nutzen, um $\vee$-Operationen an $\wedge$-Operationen vorbei nach innen zu schieben
### Beispiel 
$(¬(A \wedge ¬(C \vee ¬B)) \vee ¬(¬D \vee (B \wedge A)))$  
$\equiv (¬(A \wedge (¬C \wedge B)) \vee (D \wedge ¬(B \wedge A)))$  
$\equiv ((¬A \vee (C \vee ¬B)) \vee (D \wedge (¬B \vee ¬A)))$  
$\equiv (¬A \vee C \vee ¬B \vee D) \wedge (¬A \vee C \vee ¬B \vee ¬B \vee ¬A)$ -> KNF

## KNF aus Wahrheitstafel
- KNF für Formel $F$ 
- Mit Konjunktion alle Fälle auschließen, in denen $F$ den Wert $0$ annimmt
### Beispiel 
- $A(0), B(1), C(1)$ -> $F(0)$ 
- Um das zu vermeiden -> $(A \vee \neg B \vee \neg C)$ 

## DNF aus Wahrheitstafel
- Umgekehrt zur KNF, hier die positiven Fälle aussuchen und mit ODER verknüpfen