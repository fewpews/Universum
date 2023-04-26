---
type: atomic
tags: search 
status: 
aliases: 
date: 2022-07-12
mod date: 2022-07-12
---
# Sequenzielle Suche
#Suche
## Voraussetzungen
- Sortierte Folge ([[Sortieralgorithmen]])
- [[DSA/Definitionen/Wahlfreier Zugriff|Wahlfreier Zugriff]] auf beliebige Elemente

## Algorithmus:
```
algorithm SeqSearch (F,k)-> p
	Eingabe: sortierte Folge F der Länge n, Schlüssel
	Ausgabe: Position p des ersten Elements aus F, das gleich k ist, sonst NO_KEY

	for i:=0 to n-1 do
		if F[i]=k then
			return i
		fi
	od;
	return NO_KEY
```

## Aufwand
| Fall | Anzahl der Vergleiche |
| --------------------------------- | --------------------- |
| Bester Fall | $$1 $$ |
| Schlechtester Fall | $$ n $$ |
| Durchschnitt (erfolgreiche Suche) | $$(n+1)/2 $$ |
| Durchschnitt (erfolglose Suche) | $$ n $$ |
