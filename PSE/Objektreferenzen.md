# (Objekt-)Referenzen
#### Synonyme
- Objektvariable
- Attribut
- Eigenschaft
- (Klassen-)Feld
- Entität

## Eigenschaften
- speichert Relation von Objekt zu anderem typisierten Objekt
- Zustände einer Referenz während Ausführung(Laufzeit)
	- **Gebunden** an bestimmtes Objekt
	- **null** (ungebunden)

## Definitionen
#### Bezeichner
- Name der bestimmte Elemente des Programms repräsentiert
	- Klassen
	- Operationen 
	- Laufzeitwert -> Objekt/Objektreferenzen

## Bindung Entität an Objekt
- während Ausführung kann **Entität** (im Programmcode) an **Objekt** (im Speicher während Ausführung) gebunden werden

![[ObjektEntität_Bindung.png]]
### Java-Spezifisch
- keine Möglichkeit Objekte selbst in Entität/Variable zu speichern
- Entitäten/Variablen von Klassentypen speichern immer nur (Objekt-)Referenzen

## Spezielle Referenzen
### ``null``-Referenz
- Initialer Zustand / Standardwert von (Objekt-)Referenzen
	- Objektreferenz nicht an Objekt gebunden
- Aufrufe fehlerhaft bei **null**-Referenzen

### ``this``-Referenz
- Referenz auf aktuelles Objekt
- Eigenschaften
	- **this** ist vom Typ der erhaltenden Klasse
		- Invariante: `this != null`

### ``optional``-Referenz
- **Problem:** Unterschied zwischen nicht-initialisierten Objekten/Programmfehlern/optionalen Referenzen nicht erkennbar
- **Lösung:** Klasse Optional
- **Beispiel:**
```
Optional<Person> spouse;

Person() {
	this.spouse = Optional.emtpy();
}

Person getSpouse() {  
	return this.spouse.  
	orElseThrow(IllegalStateException::new);  
}  

void marry(final Person spouse) {  
	this.spouse = Optional.of(spouse);  
	spouse.spouse = Optional.of(this);  
}
```

### ``final``-Referenzen
- macht nur den Wert der Objektreferenz konstant, nicht den Zustand des referenzierten Objekts
```Java
final Hamster john = new Hamster();
john = new Hamster(); //geht nicht
```
- referenziertes Objekt änderbar, außer Objekt **immutable**

---
**Related:**
[[Konzepte von Sprachen]