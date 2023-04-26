# Verträge: Korrektheit des Sprachmechanismusses

## Nutzung
- Debuggen
- Schnittstellendokumentation

## Defnition
- Menge an [[Sprachtheorie#Semantik $ approx$ Bedeutung gültige Sätze|semantischen]] *Bedingungen*
- -> charakterisieren Nutzungseigenschaften [[Klassen|Klasse]]/[[Operationen|Operation]]

## Vertragsarten 
### Vorbedingung
- sichert erfolgreichen Aufruf von Operation
	- Verpflichtung für die Aufrufer, Nutzen für die Anbieter
- [[Dokumentation#JML|JML]]:
	- `@requires`
#### Vorbedingungsprinzip
- Aufrufer von Operation muss sicherstellen, dass Vorbedingung davor erfüllt

### Nachbedingung
- sichert korrekte Realisierung der Operation für Aufrufer
	- Nutzen für die Aufrufer, Verpflichtung für die Anbieter
- [[Dokumentation#JML|JML]]: 
	- `@ensures`
	- `\old` -> Wert der Abfrage vor Ausführung Operation
#### Nachbedingungsprinzip
- Operationsrealisierung muss sicherstellen, dass
	- wenn Vorbedinung davor erfüllt
	- danach Nachbedingung erfüllt ist

### Klasseninvariante
- müssen zwischen beliebigen Operationsausführungen auf Objekten der Klasse gelten
- [[Dokumentation#JML|JML]]: 
	- ` @public instance invariant...´

## Umgang mit Vor-/Nachbedingungen
- sollten auch in Operationsrümpfen genutzt werden
#### Defensives Programmieren
- Explizite Prüfung der Bedingungen
- Nichterfüllung: werfen Exception und Zustand nicht geändert
- Für alle Programmteile die durch Dritte zugänglich
#### Offensives Programmieren
- Bedingungen mittels assert zur Entwicklungszeit geprüft und zur Produktionszeit deaktivieren
- Für alle internen Operationen eingesetzt