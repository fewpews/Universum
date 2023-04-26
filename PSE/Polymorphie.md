# Polymorphie

## Definition
- **Bindung** ist **polymorph**, wenn Zielvariable und Quellenausdruck von unterschiedlichem Typ sind
- **Entität** oder **Ausdruck** sind **polymorph**, wenn sie zur Laufzeit an Objekte unterschiedlichen Typs gebunden werden
	- Resultat polymorphen Bindung
- **Polymorphie** ist Existenz dieser Möglichkeiten in Programmiersprache

## Beispiel: Einfache Zuweisungen
- ``ziel = ausdruck``
- **Ohne Polymorphie:**
	- ``ausdruck`` von **selben Typ** wie ``ziel``
- **Mit Polymorphie:**
	- Zuweisungen eines passenden **Nachkommenobjekts** zu Entität des Elterntyps ist zulässig
	- ``ausdruck`` jeder **Nachkommentyp** vom Typ von ``ziel``
- auch bei Argumentübergaben

## Definition: Statische/Dynamische Typen
- **statische Typ** einer Entität ist Typ, der **in ihrer Deklaration** in dem zugehörigen Klassentext steht
- wenn Wert der Entität, während Ausführung an Objekt gebunden wird, ist **Typ dieses (Laufzeit-)Objekts** der **dynamische Typ** der Entität zu dieser Zeit
### Grundlegende Typeigenschaft
- **dynamische Typ** einer Entität muss immer ihrem **statische Typ konform sein** 
	- ->**Nachfahre**

## Definition: Statische Typisierung
- Garantie, dass es **mindestens eine Version** von ``f`` gibt
- **Typsichere Aufrufe** (während Ausführung):
	- Opertationsaufruf ``x.f()`` 
	- das an ``x`` gebundene Objekt hat entsprechende Operation zu ``f`` 
	- auch Aufrufe mit Argumenten ``x.f(a,b)``
- **Statische Typprüfung:**
	- programmverarbeitendes Werkzeug (wie Compiler)
	- garantiert für jedes akzeptierte Programm, dass jeder Aufruf in jeder Ausführung  *typ-sicher* ist
- **Statisch typisierte Sprachen:**
	- Programmiersprache für die *statische Typprüfung* möglich zu schreiben
### Grundsätzliche Vererbungstypregel
- polymorphische Bindung (Zuweisung) zulässig, wenn Quelltyp mit Typ des Ziels **konform** 
	- grundlegendste Definition für Referenztypen:
		- U **konform** zu T falls U Nachkomme von T

## Dynamische Binden
- Garantie, dass jeder Aufruf die **am besten angepasste** Version von ``f`` verwendet
- jede Ausführung eines Operationsaufrufs wird die Version der Operation vewenden, die dem **dynamischen Typ** des Zielobjekts **am beste angepasst (die spezialisierteste)** ist

## Überblick:
![[VererbungÜberblick.png]]