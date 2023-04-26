# Stilregeln

## Programmformatierung: Lesbarkeit
- White space (Space, Zeilenumbrüche, Tabs,...)
- Typrographische Elemente (Farben, Kursiv, Fett, etc.)

## Operationen 
- kein/ein Argument
- eine Instruktion pro Zeile
- ca. 10 Zeilen, nicht mehr als 20
- Operation klein halten
	- Anzahl Vor-/Nachbedingungnen überschaubar
	- -> erhöht Testbarkeit
- Operationen die Regeln verletzen zerlegen -> auslagern
- Operationsrumpf {}
- Operationsaufruf: Punkt nach Objekt, kein Whitespace

## Lexikalische Regeln für Bezeichner
- beginnt mit Buchstaben
- weiter Buchstaben/Zahlen
#### In Java:
- mind. ein Zeichen
- 1. Zeichen: {Buchstaben, Unterstrich, Dollarzeichen}
- Weitere Zeichen: {Buchstaben, Unterstrich, Dollarzeichen, **Zahlen**}
#### Stilregeln Bezeichner:
- Rolle von Element in Domäne beschreiben
- englisch, natürliche Sprache
- ganze Namen, keine Abkürzungen
- CamelCase
- Klassennamen: groß, CamelCasing, singular
- Objektnamen/Operationen: klein, camelCasing

## Kommentare (Javadoc, JML, Verträge)
- Zusammenfassung, kurzer Satz
- Detailierte Beschreibung
- Liste Tags mit Spezifikationen/Bedeutungen
- Operationen: Vor-/Nachbedingungen (nat. Sprache (& JML))
- Klassen: Klasseninvarianten (nat. Sprache (& JML))

## Pakete
- alle neuen Klassen in sinnvolle Pakete
- Paketname: URL Organisation und Domäne umgekehrt
- alle verwendeten Klassen importieren(nicht FQCN)
- Pakete können/sollen verschachtelt werden

## Referenz
- Zustände während Ausführung(Laufzeit)
	- **Gebunden** an bestimmtes Objekt
	- **null** (ungebunden)
- vermeiden Nutzung von Objektreferenzen mit **null**-Werten
	- Objektreferenzen immer direkt mit gültiger Referenz intialisieren
	- verwendung von **Optionals** und explizite **Konstruktoren**

## Konstruktor
- **Komfort:** Initialisieren bei Erzeugung
- **Korrektheit:** Invarianten von Beginn an gewähleistet
	- **Vor** Erzeugungsanweisung
		- Vorbedingung der Erzeugungsprozedur muss erfüllt (falls vorhanden)
	- **Nach** Erzeugungsanweisung durch Referenz $x$ vom Typ $C$ referenziertes Objekt erfüllt
		- $x \:\: != 0$
		- Nachbedingung Erzeugungsanweisung
		- Klasseninvariante von $C$

## Boolesche Ausdrücke
- schreiben ohne Klammern wenn assoziativ und Äquivalenzrelation (=)

## Variablen
- sollten **final** deklariert werden, außer gute Gründe, dass mehrere Zuweisungen notwendig

## Datentypen
- Wrappertypen nur nutzen, wenns nicht anders geht

## Static
- Klassenvariablen nicht thread-sicher (als globale Variablen missbraucht)
	- nicht verwenden
	- -> statischer Konstruktor auch nicht
- Klassenoperationen nur wenn Operationsaufruf idempotent

## Sichtbarkeiten
- immer so restiktiv wie möglich
	- Prinzip des Information Hidings

## Vererbung
- Komposition vor Vererbung
