# Clean Code
## Definition: Wartung
- Prozess der Modifikation eines Softwaresystems/einer Komponenente (nach Auslieferung)
- um Fehler zu beheben, Leistung/andere Attribute verbessern/anzupassen
- Typen:
	- Instandsetzung (~20%)
	- Adaptive Wartung (~20%)
	- Perfektionierende Wartung (~60%)

The only valid measurement of code quality: WTFs / minute

## Warum Clean Code
- Verständlichkeit und Einfachheit
	- von Menschen, für Menschen
- Leser != Schreiber
- ABER: Code wird nicht so erstellt
	- ausprobieren
	- Anforderungen/Designgs ändern sich
	- Zeit-/Kostendruck
	- Unterschiedliche Kenntnisse/Fähigkeiten
	- Sprachen/Technologien/Idiome/Muster entwickeln sich
- Code muss kontinuierlich gepflegt/verbessert werden

- Probleme entstehen "im Kleinen" und verursachen Probleme "im Großen"

## Symptome Verschlechterung Codequalität
Softwareerosion
- Abnehmendes Programmverständnis
- Schwierigere (komplexe) Wartbarkeit
- Jede Änderung zeitaufwändig (& teuer)
- Steigende Fehlerraten
- Leistungsabfall
- Code "smells"

## Weitere Konzepte
#### Bedeutungsvolle Namen
- Abischt-Enthüllende Namen
- Vermeide Desinformation
- Bedeutungsvolle Unterscheidungen
- Aussprechbare/Suchbare Namen
- Vermeide Kodierungen
	- Member Prefixes & Hungarian Notation
- Vermeide Mentales Mapping
- Operationsnamen
	- Methoden sollten Verb beinhalten
- Ein Wort pro Konzept; Keine Wortbeispiele
- Verwenden von Lösungsdomänennamen und Kontexten
	- Kein unnötige Kontext

#### Funktionen(Operationen)
- Größe und Umfang
	- klein
	- sollten eine Sache tun
- Eine Ebene der Abstraktion pro Funktion
- Leserichtung: Top to Bottom
- Vermeide Swtich/Case-Basierende Operationen
	- Klassen benutzen
- Beschreibende Namen
- so wenig Argumente wie möglich
- Monadische Formen
	- wenn Input-Argument transformiert -> appear as return value
- Vermeiden von Flag-Argumenten
- Vermeide Dyadische Funktion und Triaden
- Argument Objekte, Verben und Schlüsselwörter
- Keine Nebenwirkungen
- DONT REPEAT YOURSELF
- strukturierte Programmierung
	- one entry, one exit
	- functions small

#### Kommentare
- Erkläre dich im Code
	- Kommentare machen schlechten Code nicht wett
- Rechtliche und informative Kommentare
- Absichtserklärungen und Klärung
- Warnhinweise
- TODOs
- Amplifikation
- JavaDoc in öffentlichen APIs
- Kein Mumbling, Redundante Kommentare, Pflichtkommentare, Journal-Kommentare, "(Scary) Noise" Kommentare
- Lieber Funktion und/oder Variable als Kommentar
- Keine Positionsmarkierungen und schließende Klammer-Kommentare
- Keine Attribute, Bylines und Kommentierte-Ausgabe Code
- Keine HTML Kommentare
- Keine nicht-lokalen/zu vielen Informationen
- Keine Unverständlichen Verbindungs- und Funktionskopfzeilen

#### Formatierung
Grund: Kommunikation
Newspaper Metaphor: high-level -> details
- Vertikale/Horizontale Offenheit und Dichte, keine Ausrichtung
- Einrückungen richtig brechen
- Einigung über Formatierungsregeln (TeamRules)

#### Objekte und Datenstrukturen
- Datenabstraktion (Interfaces)
- Daten/Objekt Anti-Symmetrie
	- objects hide data behind abstractions and expose functions that operate on that data
	- data structure expose their data and have no meaningful funtions
- keine "Train Wrecks"

#### Fehlerbehandlung
- Ausnahmen über Fehlercodes
	- Prefer Exeptions to Returning Error Codes
- Extrahieren von Try/Catch-Blöcken
	- keyword try very first word in function, nothing after catch/finally block
- Definiere den Normalfluss
- Nicht Null zurückgeben/übergeben

#### Werkzeugunterstützung
