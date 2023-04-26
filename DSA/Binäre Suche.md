---
type: atomic
tags: search
status: 
aliases: 
date: 2022-07-12
mod date: 2022-07-12
---
# Binäre Suche
## Voraussetzungen
- Sortierte Folge ([[Sortieralgorithmen]])
> Backlinks werden automatisch generiert, wenn es die summarizing Datei für Suchalgorithmen gibt
- [[DSA/Definitionen/Wahlfreier Zugriff|Wahlfreier Zugriff]] auf beliebige Elemente

## Prinzip
- Wähle mittleren Eintrag
- Prüfe ob gesuchter Wert größer/kleiner
- Fahre rekursiv mit der Hälfte fort, in der sich der Eintrag befindet

## Beispiel
Suche Schlüssel "2":
- Untere Schranke n
- Obere Schranke 0
- mittleres Element m

| Position in Folge | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
| ----------------- | --- | ----- | ------- | --- | ----- | --- | --- | --- | --- | --- |
| |     | |         | |       | |     | |     | |
| | 0 | 1 | 2 | 5 | ==7== | 8 | 10 | 12 | 14 | 18 |
| | n |       | |     | ==n== | |     | |     | 0 |
| |     | |         | |       | |     | |     | |
| | 0 | ==1== | 2 | 5 | 7 | 8 | 10 | 12 | 14 | 18 |
| | n | ==m== | | 0 |       | |     | |     | |
| |     | |         | |       | |     | |     | |
| | 0 | 1 | ==2== | 5 | 7 | 8 | 10 | 12 | 14 | 18 |
| |     | | n,==m== | 0 |       | |     | |     | |

## Rekursiver Algorithmus
```
algorithm BinarySearchRec (F, k, u, o) -> p  
	Eingabe: sortierte Folge F der Länge n, Schlüssel k, untere und obere Schranken u und o  
	Ausgabe: Position p eines Elements aus F, das gleich k ist, sonst NO_KEY  
	
	if u > o then  
		return NO_KEY  
	fi 
	m := (u + o)/2;  
	if F[m] = k then  
		return m  
	else if k < F[m] then  
		return BinarySearchRec (F, k, u, m − 1);  
	else  
		return BinarySearchRec (F, k, m + 1, o);  
	fi
```

## Iterativer Algorithmus
```
algorithm BinarySearch (F, k) -> p  
	Eingabe: sortierte Folge F der Länge n, Schlüssel k  
	Ausgabe: Position p eines Elements aus F, das gleich k ist, sonst NO_KEY  
	
	u := 0, o := n − 1; /* Listenendpositionen */  
	while u <= o do  
		m := (u + o)/2;  
		if F[m] = k then  
			return m  
		else if k < F[m] then o := m − 1  
		else u := m + 1  
		fi  
	od;  
	return NO_KEY
```

## Aufwand
| Fall | Anzahl der Vergleiche |
| --------------------------------- | ---------------------------- |
| Bester Fall | $$1 $$ |
| Schlechtester Fall | $$ \approx log_2 \space n $$ |
| Durchschnitt (erfolgreiche Suche) | $$ \approx log_2 \space n $$ |
| Durchschnitt (erfolglose Suche) | $$ \approx log_2 \space n $$ |
