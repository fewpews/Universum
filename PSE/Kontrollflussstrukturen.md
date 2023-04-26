---
cards-deck: 
tags: 
complete: true
aliases: Kontrollflussstrukturen
linter-yaml-title-alias: Kontrollflussstrukturen
date: 2022-11-28
mod-date: 2022-11-28
---
# Kontrollflussstrukturen

## Definition:
- Programmkonstrukte, die die Reihung der Basisschritte eines Algotihmuses beschreiben/bestimmen

## Fundamentale Kontrollflussstrukturen
### Sequenzen
- **Problemlösung:** $A \rightarrow C \Leftrightarrow A \rightarrow B, B \rightarrow C$
#### Syntax/Komposita
```
instruktion_1;
instruktion_2;
...;
instruktion_n
```
#### Korrektheit
- Vorbedingung `instruktion_1` initial gelten
- Nachbedingung jeder `instruktion_i` muss Vorbedingung von `i+1` implizieren
- Finaler Effekt: Nachbedingung `instruktion_n`
- ![[KorrektheitSequenz.png|200]]

### Verzweigung
- **Problemlösung:** getrennt für zwei Teilmengen des gesamten Eingaberaums
#### Syntax/Komposita
```
ALLGEMEIN:
if
	Bedingung                                          --Boolscher Ausdruck
then
	Instruktionen                                                 --Sequenz
else
	Andere Instruktionen                                          --Sequenz
end

JAVA:
if(Boolscher Ausdruck){
	Instruktionen
} else{
	Andere Instruktionen
}
```
#### Korrektheit
![[KorrektheitVerzweigungnen.png|550]]
##### Schachtelung
![[SchachtelungVerzweigungen.png|200]]
##### Kammartige Verzweigungen
![[KammVerzweigungen.png|200]]
```
switch (Ausdruck){                   --Typ: char,byte,short,int,String,enum
	case A:
		Instruktionen falls Ausdruck ist A
			break;
	case B:
		Instruktionen falls Ausdruck ist B
			break;
	default:
		Instruktionen falls weder A noch B
}
```

### Schleifen
- **Problemlösung:** durch aufeinanderfolgende Annäherungen des gesamten Eingaberaums
#### Syntax & Pragmatik
![[SchleifenTypen.png]]
#### Korrektheit
##### Schleifeninvarianten
- Bedingung mit folgenden Eigenschaften
	- erfüllt nach **Schleifeninitialisierung**
	- bewahrt von jedem **Schleifendurchlauf** der ausgeführt, weil **Schleifenabbruchbedingung** nicht erfüllt
		-  Wie weit Arbeit der Schleife vorangeschritten und welches Ziel am Ende erreicht ist
- JML: `@loop_invariant`, ``@decreasing``
##### Allgemein
![[KorrektheitSchleifen.png]]
##### Schleifenvarianten
- Korrektheit Terminierung
- **Schleifenvariante** ist Ganzzahl, für die gilt:
	- postitiv nach Schleifeninit. $(var_{Init} > 0)$
	- wird für jede Schleifeniteration verringert (mind. 1) und bleibt positiv, solang Abbruchbedingung nicht erfüllt $(var_{AfterLoopBody} < var_{BeforeLoopBody})$

### Goto (considered harmful)
- führen zu schlechten, schwer wartbaren Programmen
- kann auch ohne Goto unter Verwendung von Sequenzen/Schleifen ausgedrückt werden
#### Syntax/Komposita
![[SyntaxGoto.png|300]]