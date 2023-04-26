# Vererbung

## Definition
- erlaubt Klassen zu erstellen die auf existierenden basieren 
- neue Realisierung zu spezifizieren 
- Verhatlen wird beibehalten
- Code wiederverwenden
- ursprüngliche Software durch öffentliche Klassen und Schnittstellen erweitern

## Grundlagen
### Prinzip
- neue Klasse als **Erweiterung/Spezialisierung** von existierender Klasse (oder mehrere)
- **Modul Blickpunkt:**
	- alle angebotenen Klassenelemente (Operationen, Konstruktoren, Attribute,...) auch in Erbe verfügbar (andere Realisierung möglich)
- **Typ Blickpunkt:**
	- Wenn Instanz (Objekt) von Klasse benötigt auch Instanz (Objekt) von Erbe akzeptiert

## Arten von Operationen/Attributen
#### Geerbte Operation/Attribut
- von einem der Eltern der Klasse
#### Unmittelbare Opertation/Attribut
- in Klasse deklariert und nicht geerbt
- Klasse hat Operation/Attribut **eingeführt**

## Abstrakte Operationen
- Operation die **nur** aus **Spezifikation** besteht
	- Signatur
	- Vor-/Nachbedingungen
	- etc.
- Schlüsselwort ``abstract``
### Eigenschaften
- kein Operationsrumpf
- nicht **private**
- Klasse mit abstrakten Operationen (geerbt/unmittelbar) als abstract deklarieren
	- kann nicht mit ``new`` instanziiert werden
	- muss in **Subklasse** implementiert werden
		- Überschreiben ``@Override``

## Überschreiben existierender Operationen
- Implementierung Operation existiert in Elternklasse
- In Kindklasse aber zweckmäßiger implementieren
- ``@Override
### Überschreiben begrenzen
- Operation ``final``
	- kann von keiner Kindklasse überschrieben werden
	- alle die nicht *absichtlich* überschrieben werden sollen -> ``final``
- Klasse ``final``
	- keine (strikten) Nachkommen von Klasse

## Java "Interfaces"
- ``public interface`` und ``abstract``
- Klasse besteht nur aus Spezifikationen
- kann von mehreren Interfaces über ``extends`` erben

## Gemeinsamer Vorfahre: Object
- aller Klassen erweitern ``Object``
	- standardmäßige Elternklasse
- angebotene Operationen:
	- ``public String toString()``
	- ``public boolean equals(Object obj)``

## Fachtermini
- B erbt von A
	- B - **Erbe/Kind**
		- verhält sich mindestens wie Elternklasse
	- A - **Erblasser/Elternklassse** (``extends/implements``)
- Für Klasse A
	- **Nachkommen** von A 
		- A und rekursiv Nachkommen von As Erben
	- **Echte Nachkommen**
		- schließt A aus
	- **Vorfahren**
	- **Echte Vorfahren**
- **Direkte Instanzen** von A
- **Instanzen** von A
	- direkten Instanzen von A und Nachkommen
- **Subklasse**
- **Superklasse**
- **Basisklasse**

## Verträge und Vererbung
### Klasseninvariante
- Invariante eine Klasse **beinhaltet automatisch die Invarianten all ihrer Elternklassen** "und"-verknüpft
### Neudeklaration von Zusicherungen
- wenn Operation neu deklariert (überschrieben)
	- **Vorbedingung beibehalten oder abschwächen**
		- ``require else`` new_pre
		- Zusicherungen: original_precondition / new_pre
	- **Nachbedingung beibehalten oder verstärken**
		- ``ensure then`` new_post
		- Zusicherungen: original_postcondition / new_post

## Mehrfachvererbung
- verursacht Probleme bezüglich Modul Blickpunkts
- **Lösung:**
	- **Modul Mechanik**
		- Vererbung über ``extends`` auf eine Elternklasse beschränkt
	- **Typ Mechanik**
		- Vererbung von Interfaces erlaubt 0.. viele Elterninterfaces über ``implement`` 
