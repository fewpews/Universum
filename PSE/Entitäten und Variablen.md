# Entitäten und Variablen

## Defininition: Entität
- "Platzhalter"
- Bezeichner der Laufzeitwert bezeichnet
	- **Variable** falls Wert änderbar
		- **Objektvariable** wenn nur einen Wert pro Objekt

## Allgemeine Deklaration
```
String name;
Student marge;
[--> nur Variablendeklaration, in Java automatische Initialisierung mit Standartwerten]

Integer result = 12*5;
Exam pse = new Exam();
[--> Typ Variable, Variablenbezeichner, Direkte Initialisierung des Variablenwerts durch Zuweisung]
```

## Zuweisungen
### Pragmatik einer Zuweisung
- Ausführung einer Zuweisungsinstruktion `ziel = quelle;` besteht aus:
	- Bestimmen des Werts des Ausdrucks `quelle`
	- Dafür zu sorgen, dass Variable `ziel` ab jetzt für diesen Wert steht
- keinen Effekt auf `quelle`
- Vorraussetzung: Typ von `quelle` kompatibel mit Typ von `ziel` 
	- identisch oder durch Konvertierung identisch

## Arten von Entitäten in Java
![[ArtenEntitätenJava.png|500]]
- Attribut (aka Objektvariable,...)
- Klassenvariable
- lokale Variable einer Operation
- formaler Parameter einer Operation
- `this`, als Objektreferenz auf aktuelles Objekt

## Sichtbarkeitsbereiche (Scopes)
- Variablen innerhalb des ihren deklarietens Blocks **sichtbar**
- Wenn Variable Sichtbarkeitsbereich verlässt:
	- Objektreferenzen auf ungebunden (null) gesetzt
	- Speicher von primitiven Datentypen freigegeben
- Variblen freigeben:
	- wenn Objekt keine Objektrefenzen -> Garbage Collection gibt Objekt zeitnah frei (`new` wird rückgängig gemacht und Allokation aufgehoben)

## Konstanten
- Schreibgeschützte Variablen
- einige Variablen nur ein einziges Mal zugewiesen werden
	- Konstanten (Math.PI, Location.ORIGIN,...)
	- Semantisch nicht sinnvoll modifizierbare Varibalen (Hamster.territory)
	- Aus Stilgründen (niemals Parameter zuweisen)
		- `final` benutzen
- Beispiel
![[BeispielVariablenFinal.png|500]]
