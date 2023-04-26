# Collections
## Definition
- Objekt, dass andere Objekte gruppiert
- Nutzung:
	- Speichern, Abfragen, Manipulieren, Übertragen von aggregierten Daten

### Grundlegende Operationen
- **Insertion**: Hinzufügen Elemente
- **Removal**: Entfernen eines Vorkommens eines Elements (falls vorhanden)
- **Wipeout**: Entfernen aller Vorkommnisees eines Elements
- **Search**: Ermitteln, ob bestimmer Artikel vorhanden
- **Iteration(/Traversal)**: Anwenden bestimmter Operation auf jeder Element

Verschiedene Container-Implementiergungen bestimmen:
- **Fähigkeiten**
	- Welche grundlegenden Operationen verfügbar
- **Laufzeiteffizienz**
	- Performance einzelner Operationen
	- Speicherverbrauch gesamter Collection

## Collections-Frameworks
- Bibliothek für einheitliche Herangehensweise, um Collections darzustellen und zu manipulieren
- **Schnittstellen:**
	- Abstrakte Datentypen in Vererbungshierarchien für verschiedene Arten von Collections
- **Realisierungen:**
	- Wiederverwendbare Klassen, die abstrakte Schnittstellen implementieren
- **Algorithmen:**
	- Wiederverwendbare polymorphe Operationen (z.B. Sorieren/Suchen), die auf abstrakter Collection-Schnittstelle arbeiten
### java.util Collections-Framework
- Klassen/Interfaces zur Verwaltung von Objekten
- Mehrere implementierte Klassen für gängige Anwendungsfälle
- Individuelle Implementierung möglich
- Komfortable Operationen
#### Collection-Schnittstellen Beispiele
- ``List<E>`` - geordnet
- ``[Sorted]Set<E>`` - (sortiert) ohne doppelte Elemente
- ``Queue<E>`` - sortiert, FIFO-Zugriff
- ``Map<K,V>`` - Schlüssle/Wert-Zugriff
- Unterstüzende Schnittstellen
	- ``Iterator<E>`` und ``Iterable<E>`` - durch iterieren

## Variationsdimensionen
### Eigenschaften gespeicherter Elemente
![[CollectionsEigenschaften.png|400]]
### Generizität
- Typ der Collectionelemente steht erst zum Zeitpunkt der Collectionerstellung fest
- **Offener Typ** ist Typ mit einem/mehreren Typparametern 
- In Java mittels generischer Klassen
	- Verwendung von Typparametern 
		- ``final V value``
	- Generisches Interface
		- ``Collection<Hamster> hamsters``

## Hierarchie Collection-Interfaces/Klassen
![[CollectionsHierarchie.png|400]]

## Iterator, Iterable, foreach
### Iterator, Iterable
- Interface ``Iterator<E>
- Operationen
	- ``boolean hasNext()``
	- ``E next()``
	- ``void remove()``
- Aufzählung der Elemente einer Collection
- jede Collection hat Operation ``iterator()``
	- gibt ``Iterator``-Objekt zurück von Schnittstelle ``Iterable`` und deklariert Operation
	- $\ll$interface$\gg$Collection $\rightarrow$ $\ll$interface$\gg$Iterable
### Foreach loop
- kann für jede Klasse die ``Iterable`` implementiert benutzt werden
```
for(final Integer i : collection)[
	System.out.println(i);
]
```

## Ausgewählte Collections
### Listen
- ``public interface List<E> extends Collection<E>``
	- ordered, control where elements are inserted, access by index, search
	- ``void add(int index, E element)``
- ``puclic class LinkedList<E>``
	- additional operations: ``addFirst/addLast, descendingIterator()``
- ``public class ArrayList<E>``
	- resizable-array implementation
- ``public class SortedList<E>``
	- sorts on insertion
## Sets
- ``public interface Set<E> extends Collection<E>``
	- no dublicates (no elements that ``e1.equals(e2)``), on null element, models mathematical set abstraction
	- ``boolean add(E e)``
- ``public class TreeSet<E>``
	- natural ordering or by Comparator provided at creation time
- ``public class HashSet<E>``
	- backed by hash table, no gurantee for iteration order/that order will remain constant
### Dispensers
- Behälterdatenstrukturen, die bestimmte Abrufrichtlinie vorschreiben:
	- Last In First Out (LIFO)
		- wähle zuletzt eingefügte Element aus
	- First In First Out (FIFO)
		- wähle älteste Element das noch nicht entfernt
	- Priority queue
		- wähle Elemente mit höchster Priorität
#### Stacks
- LIFO-Prinzip
- grundlegende Operationen
	- **Push**: Element nach oben legen
	- **Pop**: obere Element entnehmen
	- **Peek**: lesen des obersten Elements
- Anwendungen
	- Traversieren von Bäumen
	- Parsen von Ausdrücken
	- Verwaltung der Ausführung von Routinen
#### Queue
- FIFO-Prinzip
- Java-Interface ``Queue``; Klasse ``Deque`` (und ``LinkedList``)
- Operationen
	- ``boolean offer(E e)`` - Element an Ende anhängen
	- ``E poll()`` - Entfernen erstes Element
	- ``E peek()`` - Rückgabe erstes Element
### Maps
- ``public interface Map<K,V>`` - immutable Schlüsseltyp ``K``, Wertetyp ``V``
	- object that maps keys to values, no duplicate keys, each key map at most on value
	- ``V put(K key, V value)``
	- ``V get(Object key)``
- ``public class TreeMap<E>``
	- sorted according natural ordering of keys or by Comparator provided at map creation time
- ``public class HashMap<K,V>``2
	- Hash table based implementation
#### Hash-Tabellen
- erlauben ungeordnete Schlüssel
![[HashTabelleBeispiel.png|400]]

## Arrays
- Behälter, der Elemente in Reihe von zusammenhängenden Speicheplätzen speichert, jeweils durch ganzzahligen Index identifizierbar
- fehleranfällig
![[ArrayBeispiel.png|300]]
- Deklarieren Array
	- ``int[] a;``
- Erstellen Array
	- ``a = new int[5]``
![[ArrayBeispiel2.png|200]]
- Alternative Definition
	- ``int[] primes = new int[] {2,3,5,7,11};``
- Zugriff auf Element
	- ``a[3] = 0``
	- ``System.out.println(a[3])``
	- ``a[2*i+1] = a[i]*3``
- Zugriff auf Array-Länge
	- ``int len = a.size();``
### Beispiel-Abfolge
![[ArrayBeispielAbfolge.png|500]]
### Array foreach
- Index-basiertes Durchlaufen eines Arrays
```
for (int i = 0; i < arr.length; i++){
	// arr[i]
}
```
- Häufiges Problem: Setzen von ``i`` oder Zugriff auf ``arr[arr.lenght]`` (Out-Of-Bounds-Exception)
```
Wie bei Collections:
for (final Typ val : arr){
	// use val
}
```

### Beispiel: ``main``-Methode
```
public static void main (String [] args){
	for (String arg : args){
		System.out.println(arg);
	}
}
```

## Collection-Wahl für Benutzung
- (Linked)List
	- Reihenfolge der Elemente von Bedeutung
	- Hauptzugriff in dieser Reihenfolge
	- (Bonus) Keine fest verdrahtete Größenbeschränkung
- Array(List)
	- Jedes Element durch ganzzahligen Index identifizierbar
	- Hauptzugriff erfolgt über Index
	- Fest verdrahtete Größenbegrenzung
- Hash Map/Table/Tree
	- Jedem Element Schlüssel zugeordnet
	- Hauptzugriff über Schlüssel
- Stack
	- LIFO-Verarbeitung
- Queue
	- FIFO-Verarbeitung

