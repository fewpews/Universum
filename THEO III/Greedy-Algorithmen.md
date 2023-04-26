# Greedy-Algorithmen
- spezielle Form des [[Dynamisches Programmieren|Dynamischen Programmierens]]
- merkt sich nur ein Zwischenergebnis
- Anwendbar wenn Lösung aus Reihe von Komponenten besteht, die man sukzessiv (eins nach dem anderen) aus bestehenden Teillösungen zusammenfügen kann
- Auswahl nächstes hinzuzufügendes Element entscheidender Schritt
	- -> lokale Bewertungsfunktion

## Beispiele

### Geldbetrag zusammenstellen
- Geldbetrag mit minimaler Anzahl von Münzen/Scheinen kombinieren
```
INPUT: Geldbetrag
OUTPUT: Minimale Stückelung
Starte mit leerer Menge, setze Summe auf 0.
Solange SUmme kleiner als Zielbetrag
	Füge größtmöglichen Wert (mit einem Schein/Münze) hinzu.
	Erhöhe Summe auf den hinzugefügten Wert.
```

### Kürzeste-Weg-Suche
- z.B. Dijkstra
- kantengewichteter Graph $G = (V, E, \gamma)$, Startknoten $s \in V$
- drei Mengen von Knoten
	- $B$ -> fertig bearbeitete Knoten, initial $B = \{ s \}$
	- $R$ -> Randknoten, $R = \{ v \in V \: | \: v \notin B \wedge \exists u \in B: (u,v) \in E \}$
	- $U$ -> unbekannten Knoten, $U = V \setminus (B \cup R)$

![[dijkstra_beispiel.png]]