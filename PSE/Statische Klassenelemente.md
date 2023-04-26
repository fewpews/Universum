# Statische Klassenelemente
- in einigen Fällen will man Variablen, Kommandos, Abfragen, Konstruktoren nicht für einzelne Instanzen haben, sondern mit alle Instanzen der Klasse teilen
## Statische Attribute
- liegen in Speicherbereich der bei Definition der Klasse (Java: Class Loading) angelegt wird
- Schlüsselwort ``static``
	- Attribute
	- Operationen
	- spezieller ``static``-Konstuktor

## Eigenschaften Klassenvariablen
- existiert genau einmal pro Klassendefinition in VM
- Variablenwert geteilt unter alle Instanzen der definierenden Klasse
- Zugriff innerhalb der Klasse: nicht über ``this.`` sondern über eigenen Bezeichner
- Außerhalb der Klasse: ``<Klassenname>.<Varibalenbezeichner>``

## Eigenschaften Klassenoperationen
- nur Zugriff auf andere statische Klassenelemente
- keine ``this``-Referenz verfügbar
- Zugriff außerhalb Klasse: ``<Klassenname>.<Operationsbezeichner(Argument1,...)
-  Besondere Klassenoperation Java: main
	- ``public static void main (Sting...args)``

## Eigenschaften statischer Konstruktor
- Pro Klasse maximal einen
- Keine Parameter
- Zugriff nur auf andere statische Elemente der Klasse
- Keine ``this``-Referenz
- ``static{ hamsterCount = 0;}