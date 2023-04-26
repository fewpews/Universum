---
cards-deck: 
tags: 
complete: true
aliases: Operationen
linter-yaml-title-alias: Operationen
date: 2022-10-20
mod-date: 2022-11-07
---
# Operationen

## Definiton
- von eindeutig identifiziertem Objekt (Maschine) angeboten
- von Programmen angewendet auf diese
- eindeutig definiertes Verhalten -> zugreifen/verändern von Daten
- kann Argumente verarbeiten
	- *your_objectreference.your_operation(argument1, argument2, …, argument3)*
- elementare Operationen zur Laufzeit ausgeführt-> [[Konzepte von Sprachen#Instruktionen|Instruktionen]]
## Operationsarten
#### Abfragen
- [[Objekte#Eigenschaften: Objekt|Eigenschaften von Objekten]] abfragen -> lesen
- *idempotent*: ändert nicht Zustand jeglicher Objekte
- Form: **RETURN_TYPE** opertationsname()
#### Kommandos
- **Zustand** eines/mehrerer Objekte ändern -> modifizieren
#### Erzeugungsprozeduren([[Konstruktoren]])

## Prinzip Trennung Abfrage/Kommando
- Frage soll nicht Antwort ändern
- Verletzung -> Software schwerer verständlich/wartbar
