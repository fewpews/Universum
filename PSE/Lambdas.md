# Lambdas
## Java-Code = Daten
- sollte genau wie Daten übergeben werden können
- verhalten von Algorithmen kann angepasst werden
- Beispiel:
	- Code, der von Thread ausgeführt werden soll, wird als ``Runnable``-Objekt übergeben
### Transport-Muster von Code mit Objekten
1. Klasse implementiert (nicht statische) Operation, die auszuführenden Programmcode enthält
2. Objekt dieser Klasse wird an andere Stelle transferiert (z.B. an andere Operation übergeben)
3. Operation/Algorithmus greift über Operation auf Programmcode zu


## Java-interne Realisierung
### Exkursion: Innere Klassen
- oftmals als annonyme Klassen verwendet
- dürfen keine statischen Eigenschaften haben
- Innere Klassen ähnlich zu Attributen
	- Objekte von Inneren Klassen existieren nur dann, wenn Objekt der äußeren Klasse existiert
- Objekte der Inneren Klasse haben Zugriff auf **alle** Teile ihres äußeren Klassenobjekts
- Objekte von Inneren Klassen haben implizite Referenz auf das Objekt ihrer äußeren Klasse
	- ``this``: inneres Objekt
	- ``OuterClassName.this``: äußeres Objekt

## Richtlinien für Verwendung
**Operationsdeklaration**
```
public int compare  
( String s1, String s2 ){ return s1.trim().compareTo( s2.trim() ); }
```
**Lammda Ausdruck**
```
( String s1, String s2 ) ->  
{ return s1.trim().compareTo( s2.trim() ); }
```
**Allgemeine Syntax**
``( LambdaParameter ) -> { Anweisungen }``

### Funktionale Schnittstellen
- Nicht jede Schnittstelle kann in Lambda-Ausdruck verwendet werden
- Schlüsselbedingung wann Lambda-Ausdruck anwendbar -> **Funktionale Schnittstelle**
	- Interfaces, die nur eine Operation (abstrakte Methode) haben, werden als funktionales Interface bezeichnet
	- Abstrakte Klassen mit genau einer abstrakten Methode zählen nicht dazu
	- Annotation ``@FunctionalInterface``

### Abkürzungen von Lambda-Ausdrücken
#### Typinferenz
- wenn Compiler Typen automatisch ableiten kann, sind Typdefinitionen optional
**Lange Version:**
```long-version:
Comparator<String> c =  
(String s1, String s2) -> { return s1.trim().compareTo( s2.trim() ); };
```
**Kurze Version:**
```short-version
Comparator<String> c = (s1, s2) -> { return s1.trim().compareTo( s2.trim() ); };
```

#### Lambda-Körper ist Einzelausdruck/Block
- nur aus einzigem Ausdruck -> Blockklammern/Semikolon sparen
**Lange Version:**
- ``( Lambda parameter ) -> { return expression; }``
**Kurze Version:**
- ``( LambdaParameter ) -> Expression``
**Beispiele:**
| Lange Version                                                | Kurze Version                                    |
| ------------------------------------------------------------ | ------------------------------------------------ |
| ``(s1, s2) -> { return s1.trim().compareTo( s2.trim() ); }`` | ``(s1, s2) -> s1.trim().compareTo( s2.trim() )`` |
| ``(a, b) -> { return a + b; }``                              | ``(a, b) -> a + b``                              |
| ``() -> { System.out.println(); }``                          | ``() -> System.out.println()``                   |

#### Einzelbezeichner statt Parameterliste & Klammern
| Lange Version                | Abgeleiteter Typ         | Vollständige Abkürzung |
| ---------------------------- | ------------------------ | ---------------------- |
| ``(String s) -> s.length()`` | ``(s) -> s.length()``    | ``s -> s.length()``    |
| ``(int i) -> Math.abs( i )`` | ``(i) -> Math.abs( i )`` | ``i -> Math.abs( i )`` |

## Methodenreferenz
- Referenz auf Operation **ohne deren Aufruf**
- Syntax: zwei Doppelpunkte trennen Klassennamen/Referenz links vom Methodennamen rechts
**Ohne Referenz:**
- ``Arrays.sort( words, (String s1, String s2) -> StringUtils.compareTrimmed(s1, s2) );``
**Mit Referenz:**
- ``Arrays.sort( words, StringUtils::compareTrimmed );``
