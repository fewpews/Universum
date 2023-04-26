# Pakete 

## Namensräume -> Pakete
- zwei Klassen gleicher Bezeichner -> Namenskonflikt
- Klassen in Namensräume(Pakete) legen
	- für Domäne der Klasse und Organisation eindeutig

#### Klasse in Paket legen
- ***package** de.unistuttgart.iste.rss.oo.hamstersimulator.datatypes;*
	- für Rest der Datei
	- Organisation und Domänenteil

#### Verwendung der Klasse
- ***import** de.unistuttgart.iste.rss.oo.hamstersimulator.datatypes.LocationVector;*
- ***class** MyLocationVector **extends** LocationVector*
	- importieren in Namensraum dieser Datei

## Vorteile: Verwendung von Paketen
-   Übersichtliche Organisation der Klassen 
	- -> Relationen
-   Einfache Imports anderer interner und externer Pakete 
	- -> Wiederverwendbarkeit & Erweiterbarkeit
-   Nur für Implementierung wichtigster Code sichtbar 
	- -> Vereinfachung & Information Hiding