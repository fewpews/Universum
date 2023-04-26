# Streams
- Stream-API: ``java.util.stream``
- "Klassen, um Operationen nach dem funktionalen Stil auf Streams von Elementen zu unterstützen, wie bspw. Map-reduce Transformationen auf Collections."
## Schnittstelle ``Stream<T>`` am Beispiel
- "Folge von Elementen, die sequentielle & parallele Aggregatoperationen unterstützen."
```
Collection<Widget> widgets = ...;  

int sum = widgets.stream()  
	.filter(b -> b.getColor() == RED)  
	.mapToInt(b -> b.getWeight())  
	.sum();
```
1. Erzeugen Stream an ``Widget``-Objekt über ``Collection.stream()``
2. Filtern, um Strom zu erzeugen der nur rote Widgets enthält
3. In Strom von ``int`` Werten transformieren, die Gewicht jedes Widgets repräsentieren
4. Stream summiert für Gesamtgewicht

## Stream Operationen und Pipelines
**Stream Pipeline** besteht aus
- **Quelle** (bspw. Collection, Generatorfunktion, I/O Channel)
- gefolgt von ``null`` oder mehr **Intermediäroperationen** (z.B. ``Stream.filter``, ``Stream.map``)
	- neuen Stream zurückgeben
- und eine **Terminaloperation** (z.B. ``Stream.forEach``, ``Stream.reduce``)
	- kann Stream traversieren, um Ergebnis/Nebeneffekt zu erzielen
### Beispiel-Operationen
![[BeispielStreamOperationen.png|450]]
### Reduktions-Operationen
- nimmt Folge von Eingabeelementen und kombiniert sie zu einem einzigen zusammenfassenden Ergebnis
- **Beispiele**:
	- Summe/Maximum einer Menge von Zahlen zu finden
	- Elemente zu Liste akkumulieren
	- Allgemeine Reduktionsmaßnahmen von Streams
		- ``reduce()``, ``collect()``
	- Spezialisierte für z.B. ``IntStream``
		- ``sum()``, ``max()``, ``count()``
#### nicht-strombasiert vs. strombasiert
- Leicht als einfache sequentielle Schleifen darstellbar (nicht-strombasiert)
```
int sum = 0;
for (final int x : numbers){
	sum += x;
}
```
- Stream-basierte Implementierungen
```
int sum = numbers.stream().reduce(0, Integer::sum);

int sum = numbers.parallelStream().reduce(0, Integer::sum);
```

## Funktionale Schnittstellen
Besonders relevant für Streams:
- ``Interface Predicate<T> { boolean test( T t ); }``
- ``Interface Function<T,R> { R apply( T t ) }``

## Stream vergleich zu Collections
- keine Speicherung
- Funktionaler Charakter
- Laziness-suchend
- Möglicherweise unbegrenzt
- Verbrauchbar

## Arten von Streams
- ``Stream<T>`` allgemeiner Stream über Objekte
- API bietet spezialisierte Streams der primitiven Typen:
	- ``IntStream``, ``LongStream``, ``DoubleStream``
- ``Stream<T>`` bietet map-Funktionen, um spezialisierte Streams zu erhalten:
	- ``DoubleStream mapToDouble(ToDoubleFunction<? super T> mapper)``
	- ``IntStream mapToInt(ToIntFunction<? super T> mapper)``
	- ``LongStream mapToLong(ToLongFunction<? super T> mapper)``

## Parallelität
- Verarbeitung von Elementen von for-Schleife seriell
- Alle Stream-Operationen entweder seriell oder parallel
	- Stream-Implementierung im JDK erzeugen serielle Streams, außer Parallelität ausdrücklich gewünscht
	- ``...int sum = widgets.parallelStream()...``
	- Abgesehen der Nichtdeterminiertheit, sollte die Tatsache, ob Datenstrom sequentiell/parallel ausgeführt wird, das Ergebnis der Berechnung nicht verändern