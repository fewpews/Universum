# Dokumentation

## **Dokumentation** von [[Schnittstelle|Schnittstellen]]
- **Wichtig**: Nutzung, Fehlersuche, Wiederverwendung
- **Ziel**: Beschreibung Funktionalität
	- Bedeutung Variablen
	- Funktionalität Operationen 
	- Argumente, Rückgabewerte
- **Kommentare**: // und /* .... * / 

## **Javadoc Kommentare**: /** .... * / 
- für [[Klassen]] & [[Schnittstelle|Schnittstellen]], [[Operationen]], Klassen-/Objektvariablen
- [[Stilregeln#Javadoc Kommentare|Minimaler Qualitätsstandard]]
#### Tags
- Klassen & Schnittstellen
	- `@author` text
	- `@version` text
- Operationen
	- `@param param-name`` text
	- `@return` text
	- `@throws` *exceptionclass* text
	- `@see` (Rückgabewerte, "see also")

## JML
- Erweiterung für Verträge (OpenJML)
	- Syntax JML überprüfen
	- Vertragserfüllung zur Laufzeit testen
	- Programm beweisen
- JML Kommentar
```
/*@
@ requires ...
@ ensures ...
@*/
```