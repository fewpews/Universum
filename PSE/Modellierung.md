# Modellierung
## Definition: Modellierung
- Erstellung von Artefakten zur Beschreibung(/Spezifizierung) von (Teilen von) Softwaresystemen wird als **"Modellierung"** bezeichnet

## Definition: Modell (Stachoviak)
- eine *zielorientierte* Abbildung eines Systems, das die Realität *vereinfacht*, indem es zu problemrelevanten Aspekten *abstrahiert*. 
- ermöglicht *ähnliche Beaobachtungen* und Aussagen wie das modellierte System

## Fachtermini
#### Artefakte
- Alle Arten von produzierten Teilen, die in der Software verwendet werden oder zum Verständnis oder der Wartung der Software beitragen
	- Code, Bytecode, Anforderungen, Modelle,...
#### Dokumente
- Artefakte, die von Menschen gelesen und bearbeitet werden sollen
#### Sprachtypen
- Dokumente können in **textuellen**, **visuellen** oder **hybriden** Sprachen erstellt werden
#### Grad der Formalisierung
- Sprachen können sein:
	- **informell** (z.B. natürliche Sprache)
	- **semi-formal** (z.B. Formulare)
	- **formal** (mathematische Semantik, z.B. Programmiersprachen)

## Notaionen für Softwaresichten
#### UML = Unified Modeling Language 
- Standard der **OMG** zum Modellieren von Software
- hybrid (visuell/textuell) und semi-formal
#### OMG = Obbject Management Group
- Industriekonsortium, das für die Standardisierung verantwortlich ist
### Diagrammtypen (View Types)
![[DiagrammTypen.png]]

![[DiagrammTypenBeispiel.png]]

## Modellierung von Objekten und Beziehungen
- Struktur von OO-Systemen ist oft durch ihre Objekte & Beziehungen gekennzeichnet
	- Objektdiagramme
- Diese Elemente werden dann in Objektklassen & Beziehungsklassen abstrahiert
	- Klassendiagramme
### Zusammensetzung
#### Objekt(Entität)
- ist Entität unserer Realität/Vorstellungskraft, die von allen anderen Entitäten unterschieden werden kann
- hat Identität (Objektidentifikator)
	- nicht anhand Attributewerte unterscheidbar sein
		- Objektgleichheit (dasselbe)
		- Wertegleichheit (das gleiche)
#### Beziehung(Link)
- ist *identifizierbare Verbindung* zwischen (mindestens) zwei (nicht notwendigerweise unterschiedlichen) Objekten
#### Attribute (=properties in UML)
- beschreiben Objekte und deren Beziehungen in weiteren Details
- charakterisiert eine *Eigenschaft* und besteht aus
	- Attributname (property name)
	- Attributwert (property value)
#### Klassifikation
- Klassifizierung:
	- Objekte der gleichen Art -> **Klassen**
	- Beziehungen der gleichen Art -> **Assoziationen**
![[SchemaInstanz.png]]
##### Besondere Assoziationen
- **Aggregation**
	- Zusammensetzung von Objekten(Komponenten) zu zusammengesetzten Objekt
	- "Teil-Ganzes Beziehung"
- ![[Aggregation.png|150]]
- **Komposition**
	- spezielle Aggregation, bei der Existenz der Teile(Komponenten) von Existenz des Ganzen abhängt
- ![[Komposition.png|200]]

### Klassendiagramm
- sollten wie modelliert implementiert werden
- den Code so gut wie möglich wiedergeben (und umgekehrt)
	- Enge Beziehung
![[KlassendiagrammÜbersicht.png]]
- {unique}, {ordered}
### Objektdiagramm
![[ObjektdiagrammÜbersicht.png]]

## Modellierung der Interaktion
### Sequenzdiagramme
- für Modellierung von **Szenarien**
- beschreiben mögliche Kommunikation von Objekten über die Zeit
### Übersicht
![[SequenzdiagrammÜbersicht.png]]
### Konzepte
- **Lebenslinien**
	- modellieren beliebig viele Interaktionspartner (Objekte/Akteure)
	- können **Aktivitätsboxen** haben
	- verschiedene **Nachrichtentypen**
		- ![[SequenzdiagrammNachrichtentypen.png|200]]
- **Nachrichten**
	- modellieren Informationsfluss 