# Objekterzeugung

## Basisprozess
- **Allokiere** neues Objekt im Haldenspeicher (Heap)
	- "Platz im Speicher reservieren"
- **Initialisiere** das Objekt mittels Erzeugunsprozedur
- **Verbinde** Entität / Variable mit neuem Objekt
	- "Daten zum reinschreiben"

## Prinzip der Erzeugung
- falls Klasse nicht-triviale Invariante besitzt
- muss einen/mehrere Konstruktoren anbieten welche sicherstellen
	- Invariante jeder Instanz erfüllt nach Ausführung des Konstruktors

## Beispiel: ohne Konstruktor
- `Location location = paule.getLocation();`
	- Lokale Objetkreferenz und Zuweisung
- `paula = new Hamster();`
	- Objektvariable und Zuweisung
	- `new` -> erzeugt neues Objekt
		- neuer Hamster + Objektreferenz auf diesen
	- Sinnvolle Standartwerte
- `paula.init(territory, location, direciton, 1);`
	- Explitzite Initialisierung mit kopierten Werten

## Erzeugungsprozedur: Konstruktor
- Jede Operation hat `/*@ requires isInitialized @*/` als Vorbedinung
- Initialisierungscode ausführen während Objekt erzeugt wird und Nutzung erzwingen
	- **Komfort:** Initialisieren bei Erzeugung
	- **Korrektheit:** Invarianten von Beginn an gewähleistet
- In Java:
	- Operation gleicher Name wie Klasse
	- Keine Rückgabetypen

## Beispiel: mit Konstruktor
- `Hamster(Territory territory, Location location, Direction direction, int newGrainCount) {`
- `paula = new Hamster(territory, location, direction, 1);`

## Überladen
- mehrere Operationen (mit unterschiedlichen Argumenttypen und -anzahlen) die alle dasselbe Verhalten realisieren
- Operationen/Konstruktoren mit gleichen Namen, aber Argumenten unterschiedlicher Anzahl/Typ werden vom Kompiler als unterschiedliche behandelt

## Konstruktorenverkettung
- Konstruktoren werden grundsätzlich nich an Kindklasse vererbt
- jedoch aufgerufen werden
- verwende ``super(arg_1,...,arg_n)``-Aufruf um Konstruktor der Elternklasse aufzurufen
	- muss erster Aufruf im Konstruktor sein
	- falls kein Standardkonstruktor in Elternklasse vorhanden muss Aufruf **explizit** erfolgen
	- können **überladenen Aufrufe** sein
### Zugriff auf Attribute/Operationen der Superklasse
- **Super-Zugriff:**
	- Code aus überschriebenen Operationen wiederverwenden 
		- ``super.method()``
	- auf sichtbare Attirbute zugreifen falls Kindklasse gleiche Attribut hat (vermeiden)
		- ``super.attribute``