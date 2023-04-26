# Logik
- Die Wissenschaft des Folgerns und Beweisens

## Boolische Ausdrücke
- Bedingung wird als boolischer Ausdruck dargestellt bestehend aus...
	- **Boolesche Variable** (Bezeichner für boolesche Werte)
	- **Boolesche Operatoren** (nicht,oder,und,=,impliziert)
- repräsentiert mögliche Boolsche Werte (Wahrheitswerte **wahr/falsch**)
- als AST darstellbar

## Boolesche Operatoren
#### Verneinung
- Für jeden boolschen Ausdruck $e$ und jeden Wert der Variblen
	- Genau einer aus $e$/nicht $e$ hat Wert **wahr/falsch**
	- Einer aus $e$/nicht $e$ hat Wert **wahr** (Satz vom ausgeschlossenen Dritten)
	- Beide aus $e$/nicht $e$ nicht den Wert **wahr** (Satz vom Widerspruch)
#### Disjunktion (Oder)
- nicht ausschließend und kommutativ
	- **wahr** außer beide Werte sind **falsch**
#### Konjunktion (Und)
- kommutativ
	- **falsch** außer beider Werte **wahr**
#### Gleichheit (=)
- kommutativ und reflexiv (a=a)
#### Implikation
- a **impliziert** b $\Leftrightarrow$ (**nicht** a) **oder** b
- immer **wahr** außer **wahr** impliziert **falsch**
- **Negation:** (**nicht** b) **impliziert** (**nicht** a)

### Dualität von Und/Oder
- Eigenschaften des einen ergeben Eigenschaften des anderen 
	- durch **Negierung** und **Tauschen** wahr/falsch

## Semistrikte Boolesche Operatoren
- nicht **kommutative** Version von **Und/Oder**
- definiert Auswertungsreihenfolge von Ausdruck (wichtig für Programmieren)
#### Und dann
- selbe Werte wie **Und** 
- immer **falsch** wenn Wert a **falsch**
#### Oder sonst
- selbe Werte wie **Oder**
- immer **wahr** wenn Wert a **wahr**

## Notation boolesche Operatoren
![[Notation_BoolescheOperatoren.png]]

## Syntaxkonventionen: Binden von Operatoren
- Reihenfolge Bindung **stark nach schwach:** 
	- **nicht, und, oder, impliziert, =**

## Wahrheitstabellen
- Wahrheitsbelegungen wahr/falsch 
	- -> erfüllen Ausdruck wenn Wert des Ausdrucks **wahr**
- $m$ Teilausdrücke mit $n$ Variablen
	- $n+m$ Spalten
	- $2^n$ Zeilen
![[Wahrheitstabelle_Basisoperatoren.png]]

## Tautologien
- boolischer Ausdruck **Wahr** für jede mögliche Wahrheitsbelegung
#### De Morgansche Gesetze
- (**nicht** (a **oder** b)) **=** ((**nicht** a) **und** (**nicht** b))  
- (**nicht** (a **und** b)) **=** ((**nicht** a) **oder** (**nicht** b))
#### Distributiv Gesetze
- (a **und** (b **oder** c)) **=** ((a **und** b) **oder** (a **und** c))  
- (a **oder** (b **und** c)) **=** ((a **oder** b) und (a **oder** c)
#### Assoziativ Gesetze
- a **und** (b **und** c) **=** (a **und** b) **und** c  
- a **oder** (b **oder** c) **=** (a **oder** b) **oder** c
	- ohne Klammern möglich

## Widersprüche
- boolische Ausdruck **Falsch** für jede mögliche Wahrheitsbelegung

## Erfüllbarkeit
- für mindestens eine Wahrheitsbelegung ergibt Ausdruck den Wert **Wahr**
	- jede **Tautologie** ist erfüllbar
	- kein **Widerspruch** ist erfüllbar

## Aussagen-/Prädikatenlogik
### Existenzaussagen
- **Existenzquantor:** es existiert/$\exists$
- $\exists$ s : EINE_MENGE | s.eine_Eigenschaft
	- MENGE leer -> immer **falsch**
### Allaussagen
- **Allquantor:** für alle/$\forall$
- $\forall$ s: EINE_MENGE | s.eine_Eigenschaft
	- MENGE leer -> immer **wahr**

![[Notion_Prädikate.png]]

### Dualität
- **nicht** ($\exists$ s : EINE_MENGE | P ) =  $\forall$ s : EINE_MENGE | **nicht** P  
- **nicht** ($\forall$ s : EINE_MENGE | P ) = $\exists$ s : EINE_MENGE | **nicht** P