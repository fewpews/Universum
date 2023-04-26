# Testen
- shows the presence of bugs, but never their absence
- if not tested, it's broken
## Definition: Testen
- Experimentelle Überprüfung eines konkreten Softwaresystems hinsichtlich seiner (funktionalen/nicht funktionalen) Qualität
- Experimente basieren auf Testfällen
## Definition: Testfall
- Benannte Menge an Eigenschaften (und Vorbedingungen) zusammen mit einer Beschreibung der erwarteten Ausgabedaten (und Nachbedingungen)
- Besteht aus:
	- Name
	- Menge an Eingabedaten (und Vorbedingungen)
	- Prädikat übder die Ausgabedaten und die nachfolgenden Zustände

## Ebenen des Testens
![[TestenEbenen.png|400]]

## Test-Sequenzen
- Testfälle zu Test-Sequenzen (Test-Suiten) zusammengefasst
![[PSE/_files/TestSuiten.png|200]]

## Testablauf
- **Testvorbereitung**
	- Ermittlung von Testfällen
		- Automatische Ableitung für optimale Testsuiten nicht für jeden Fall möglich
		- Ziel: gute Heuristiken, um leistungsfähige Tests abzuleiten
- **Testdurchführung**
	- Ausführung (in evtl. simulierter Testumgebung)
	- Sammeln von Informationen
- **Testauswertung**
	- Soll-Ist-Vergleich
	- Dokumentation der Ergebnisse
		- Testbericht und Archivierung der Ergebnisse (bei Regressionstests)
	- Erstellung Teststatistiken

## Arten von Tests
- Black-Box/White-Box haben sich **ergänzende** Eigenschaften
- Testfälle sollten nach **beiden** Strategien entwickelt werden
### Black-Box
- Abgeleitete Testfälle aus **Anforderungen** und **Spezifikation** (z.B. aus Vor-/Nachbedingungen)
	- Für jede **Anfordeung** mindestens ein Testfall
	- Jedes **Szenario** mindestens einmal ausgeführt
	- Für jede **Spezifikation** mehrere Testfälle erstellt
#### Prüfung von Spezifikationen
##### Domänentests
- Strukturierung der Ein- und Ausgabedaten und der Funktionalität in **Äquivalenzklassen**
	- **Eingabeabdeckung**
		- Zerlegung des Eingabewertebereichs aufgrund von inhaltlichen/typspezifischen Überlegungen
	- **Ausagabeabdeckung**
		- Zerlegung nach dem Bereich der Ausgabewerte
	- **Funktionsabdeckung**
		- jeder Andwendungsfall, jede Anforderung, jede Methode/Klasse/Verknüpfung
- Repräsentative Prüfung von
	- einigen **Normalfällen**
	- möglichst vielen **Grenzfällen** (**Extremfällen**)
		- am wichtigsten
		- leere Eingabe, nur identische Daten, maximale Anzahl von Daten, etc.
	- einigen **Fehlerfällen**
##### Zufallsprüfung
- Zufallsgenerierung von Zufallsdaten
##### Statistische Prüfung
- Generierung von Daten entsprechend der erwarteten Datenverteilung

### White-Box (Glass-Box)
- Aus dem **Programmcode** (Systemstruktur) abgeleitete Testfälle
- Testdaten aufgebaut, dass **ausgewählter Kontrollflusspfad** im Programm durchlaufen wird
#### Überdeckungskriterien
- **Anweisungsüberdeckung** ($C_0$) jede Anweisung mindestens einmal
- **Zweigüberdeckung** (Bedingungsüberdeckung) ($C_1$) jede Bedingung mindestens einmal erfüllt & nicht erfüllt
- **Pfadüberdeckung** ($C_\infty$) jeder Pfad mindestens einmal ausgeführt
	- normalerweise nicht durchführbar
#### Vorgehen
- Bestimme **Programmpfade** die gewünschte Überdeckung gewährleisten
- Bestimme **Bedingungen** für jeden Pfad
- Finde **(Eingabe-)Daten** die Bedingungen erfüllen 
- Mit **Profiler-Werkzeugen** können nicht erreichte Programmteile gefunden werden

## Implementierung
- **Kontinuierliches** Testen der Implementierung
	- moderne (agile) Softwareentwicklung -> Komponenten nach jeder Änderung getestet
	- Idealfall: Test vor Programmierung erstellt
- Unterstüzende **Werkzeuge**:
	- Für einfache **Testerstellung** 
	- Tests **sammeln/strukturieren**
	- Für übersichtliche **Durchführung**
	- Zur automatischen **Auswertung**
### JUnit
- Open-Source-(Unit-)Testwerkzeug
	- **Framework**, das Definition von Testfällen unterstützt
	- **Werkzeug**, das Testfälle ausführt und Ergebnisse auswertet/reportet
#### Ablauf
- Test in separaten Klassen zusammengefasst
- Jede Klasse enthält Methode für Testfälle
- Die Methode...
	- hat **Namen**, der Test beschreibt
	- bereitet **Vorbedingungen** und **Eingabedaten** vor
	- bewertet **Ausgabedaten** und **Nachbedingungen**
#### Assert-Methoden
- Zur Überprüfung der Nachbedingung werden statische Methoden der Klasse benutzt:
	- ``org.junit.framework.Assert``
#### Unit-Test
- Können auf Komponenten unterschiedlicher Granularität durchgeführt werden:
	- Methoden
	- Klassen
	- Subsysteme
- Deshalb zu diesem Zweck jede Komponente mit **Testdaten** ausgeführt
- Testklasse wird von JUnit-Test-Runner-Werkzeug ausgeführt
- Für jeden Testfall XXX werden Methoden der folgenden Typen ausgeführt:
	- ``@Befor setUp()``
	- ``@Test testXXX()``
	- ``@After tearDown()``
- Einer Übersicht zeigt Erfolge/Misserfolge

## Besondere Tests
### Testen von Testsuiten
- Durch **Mutationen**
	- Einfügen kleiner Fehler in Code
	- Künstlich fehlerhafte Programme
- Mutation nicht erkannt -> Testdatensammlung erweitern
### Durch Zusicherungen (Asserts)
- Bedingungstests einfügen, die an diesen Stellen erfüllt sein müssen
- Beispiel: ``assert !(x > 0) && (z < maximum);``
