# Software Engineering
## Was ist Software?
- Software >> Programm

## Definition: Softwaresystem
- Menge an Programmen 
- mit begleitenden **Artefakten** (für Nutzung notwendig/hilfreich)
	- z.B. Anforderungsbeschreibungen, Entwürfe, Spezifikationen, Testsuites, Skripte, ...

## Definition: Software Engineering
- Disziplin der Informatik, die sich mit der Entwicklung, dem Betrieb und der Wartung von Softwaresystemen befasst
	- **Große** Softwaresysteme in **industriellen** Kontexten
	- Oft stehen die Menschen (Entwickler, Anwender,...) im Fokus
- Mehr als nur Programmierung:
	- Hohe Komplexität
	- Zahlreiche Anforderungen
	- Interaktion vieler Menschen
	- Lange Entwicklungszeiten
	- Permanente Veränderung
	- Heterogene Umgebungen
	- ...
### Ingenieurwissenschaftliche Disziplinen
Chaos Report:
- 31% aller Projekte Abgebrochen
- 53% aller Projekte kosten mindestens 189% der veranschlagten Kosten
-> **ingenieurwissenschaftlicher Ansatz:**
- Anforderungen erfassen & definieren
- Modelle festlegen
- Lösungen konstruieren
- Überprüfung & Analyse der Ergebnisse

## Qualitätseigenschaften
### Software sollte ... sein
- Korrekt
- Erweiterbar
- [[Stilregeln#Programmformatierung: Lesbarkeit|Lesbar]]
- Wiederwerwendbar
- Funkt. Sicher
- Verfügbar
- Performant
- (Daten-) Sicher
- Privat
-> Wichtig! weil Projekte sehr groß und Fehler schwierig zu finden
### Erweiterbarkeit & Wiederverwendbarkeit
- **Erweiterbarkeit:** Einfachheit ein System sich ändernden Nutzerbedürfnissen anzupassen
- **Wiederverwendbarkeit:** Einfachheit existierende Software für neue Anwendungen zu verwenden
### extern vs. intern
- **Externe** Faktoren: für Kunden sichtbar
	- am Ende zählen nur externe Faktoren, interne machen es möglich zu erreichen
- **Interne** Faktoren: nur für Entwickler wahrnehmbar
### Produkt vs. Prozess
- **Produkt**: Eigenschaften der resultierenden Software
- **Prozess**: Eigenschaften der Verfahren zur Erstellung und Pflege der Software
### Weg zur hochwertigen Software
- Wichtigen **Prinzipien** folgend
	- Einfachehit, Analogie, Vollständigkeit, Trennung der Belange,...
- Anwendung geeigneter **Methoden**
	- Strukturdesign, objektorientierte Analyse, Black-Box-Tests,...
- Unter Benutzung entsprechender **Werkzeuge**
	- Compiler, Linker, Programmanalyse-Werkzeuge, IDE,...

## Software-Lebenszyklus
- Weg vom Problem zur Lösung erfordert verschiedene **Aktivitäten** und unterstützende **Methoden**
### Übersicht
![[SoftwareLebenszyklusÜbersicht.png]]
### Requirements Engineering
- **Frühe Phasen** eines Software-Projektes
	- Wissen über Produkt **unsicher/unpräzise/unvollständig/informell**
	- **Kommunikation/natürliche Sprache/Visualisierungen** spielen Schlüsselrolle

#### Definition
- systematische, disziplinierte und quantitativ messbare Vorgehensweise bei der Spezifikation (d.h. Erhebung, Dokumentation und Analyse) und Verwaltung von Systemanforderungen
	- **Funktionale und nicht-funktionale (Profukt-)Anforderungen** -> Code

#### Qualität von Anforderungen
- **eindeutig, korrekt, konsistent, machbar, überprüfbar,...**
- Management bezogene Aspekte:
	- Alle Stakeholder einbeziehen
	- Verfahren für kontrollierte Veränderungen festlegen
	- Mechanismen für Nachverfolgbarkeit einrichten
	- Behandeln des Anforderungsdokuments (Software Requirements Specification IEEE 830-1998) als einen der wichtigsten Bestandteile des Projekts: Klarheit/Präzision/Vollständigkeit

### Software-Architektur
- **structure/structures of the system**, which comprise **software elements**, the **externally visivle properties of those elements**, and the **relationships** among them
- **set of principal design decisions** made about the system
#### Zweck
- **Komplexität** beherrschen
- Grundlegende **Designentscheidungen** dokumentieren
- **Plan** zur Verfügung stellen, der relevanten Elemente & Beziehungen erklärt
- Ermöglicht **Analyse und Bewertung** des Systems hinsichtlich Korrektheit/Konsistenz/Performance/Usability/Verfügbarkeit/...
- Erleichtert **Verständnis** des High-Level-Designs des Systems durch Abstraktion
#### Architekturmodelle
- VL 20, Folie 55ff.

### Implementierung, Integration, Installation
**Aufgabe:** Das Design in Code umsetzen (&validieren)
- Einsatz von **Entwicklungsumgebungen** (IDEs)
- **Dokumentation** (JavaDoc)
- **Testen** (JUnit)
- "Design im Kleinen" (**Entwurfsmuster**)
- **Programmverbesserung/Tuning** (Refactoring)
- Fortgeschrittene Programmierkenntnisse in GUI-Programmierung, Multi-Threading, Netzwerkprogrammierung,...
- ...
#### Prinzipien & Regeln der Programmierung
- **Dekomposition**: Schrittweise Verfeinerung; kleine Klassen/Methoden
- **Abstraktion**: Methoden anstellen von wiederholtem Code; kein copy-paste
- **Lokalität**: Strukturierte Programmierung; verwandte Methoden in gleichen Klassen
- **Trennung der Belange**: kurze Code-Sequenzen; kurze Methoden und Klassen mit Verantwortung
- **Analogie**: Programmierrichtlinien und Styleguides beachten; einheitliche Sprache; konsistente Benennung
- ...

### Qualitätssicherung
- "A planned and systematic pattern of all actions necessary to provide adequate confidence that an item or product conforms to established technical requirements."
#### Konstuktive vs. analytisch
- **Konstruktiv**
	- gute Methoden/Werkzeuge/Prozesse/Personal
	- durch Automatisierung
- **Analytisch**
	- messen & prüfen
	- inspizieren
	- durch (formale) Verifikation
#### Validierung & Verifikation
- **Validierung**: Überprüfung der internen Konsistenz
	- "Überprüfen, ob System richtig eingebaut" (alle Regeln befolgt)
- **Verifikation**: Prüfung gegen eine übergeordnete Beschreibung
	- "Überprüfung, ob das richtige System gebaut" (Benutzerbedürfnisse erfüllt)

### Software-(Entwicklungs-)Prozesse
- Design und Implementierung bilden eigentlichen Produktionsprozess
- Produktion im Wesentlichen eine Vervielfältigung
#### Software-Vorgehensmodelle
- **Definition:** erfassen die Identifikation der Kernaufgaben im Rahmen des Softwarepojektes und deren Organisation
	- Wasserfall-Modell
		- V-Modell
	- Scrum(Agile)
- **Grund:** 
	- Team versteht was es tut
	- Entwickler verstehen was andere Entwickler tun
	- Manager verstehen was Entwickler tun
	- Wissen & Erfahrung vermitteln
	- Prozess planbar & wiederholbar machen
	- **Gleichgewicht** zwischen **Standardisierung** und Freiraum für **Kreativität**


