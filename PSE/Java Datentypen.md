# Java Datentypen
![[ÜbersichtJavaDatentypen.png]]

## Primitive Wertetypen
![[DatentypenÜbersicht1.png]]
- nicht-Klassentypen -> Wertetypen
	- Speichern direkt Werte, keine Referenzen
- absichtliche Verletzung des OOP Prinzips zugunsten effizienterer Speicherausnutzung
![[PrimitiveWertetypenBeispiel.png]]
### Numerische Datentypen
#### Ganzzahlen - byte,short,int,long
- Vorzeichenbehaftete positive/negative Ganzzahlen
- klassifiziert durch unterstützte Werte und ihrem Verhalten
#### Fließkommazahlen(Gleitkommazahlen) - float,double
- rationelle Zahlen mit unterschiedlicher Präzision darstellbar
### Nicht-numerische Datentypen
#### Zeichen - char
- Unicode um Zeichen zu codieren
- von 0 bis 65.536
#### Wahrheitswerte - boolean
- logische Werte true/false

### Mächtigkeit Primitive Datentypen
![[PrimitveDatentypenMächtigkeit.png|500]]
### Beispiele primitive Datentypen und ihre Literale
```Java
byte b = 17;
short s = -32562;
short s = -32_562;
int i = 16;
int j = 0xff;
int k = 0b111011;

long longA = 9123859328329343l;
long longB = 10l;

float f = 3.14f;
double d = 14.123943829123843859d;

char c = 'g';

boolean b = false;
```
### Berechnungen
| Operation      | Mathermatisches Symbol | Java |
| -------------- | ---------------------- | ---- |
| Addition       | +                      | +    |
| Subtraktion    | -                      | -    |
| Multiplikation | $\cdot$                | *    |
| Division       | :                      | /    |
| Modulo         | mod                    | %    |

| Langfassung     | Kurzschreibweise |
| --------------- | ---------------- |
| ``a = a + 7;``  | ``a += 7;``      |
| ``b = b * 5;``  | ``b *= 5;``      |
| ``c  = c / 2;`` | ``c /= 2;``      |
| ``d = d - 12;`` | ``d -= 12;``     |
| ``e = e % 2;``  | ``e %= 2;``      |
| ``f = f + 1;``  | ``f++;``         |
| ``g = g - 1;``  | ``g--;``         |

### Typumwandlung (Casting)
- vermeiden wann immer möglich!
```Java
//Beispiel:
byte small = 127;
short larger = (short) small;

float floating = 127.37f;
int noDecimals = (int) floating;
```

## Nicht-Primitive Datentypen
![[DatentypenÜbersicht2.png]]

#### Stringobjekte
- Unterstützen +-Operator: Stringkonkatenation
- Unterstützen Objektliterale
- Viele Typen unterstützen impliziete Konvertierung in Strings
- In Java: **immutable**(unveränderliche) Objekte 
	- Zustand wird nur bei Konstruktion festgelegt
#### Wrapper-Objekte
- einige Datenstrukturen nur mit Objekten umgegen
	- primitive Werte in Objekte kapseln
- Unterstützung Compiler:
	- Impliziete Konvertierung Objekte <-> primitive Werte
	- Wrapper-Objekte sind **immutable**(unveränderlich)
```Java
Integer anIntObject = 32;                                     //auto-boxing
int anPrimInt = anIntObject;                                //auto-unboxing
```
##### Klassentypen primitive Datentypen
| Primitive Typen | Wrapper Klassen     |
| --------------- | ------------------- |
| byte            | java.lang.Byte      |
| short           | java.lang.Short     |
| int             | java.lang.Integer   |
| long            | java.lang.Long      |
| float           | java.lang.Float     |
| double          | java.lang.Double    |
| boolean         | java.lang.Boolean   |
| char            | java.lang.Character |
#### Aufzählungsdatentypen (Enumerations)
- endliche, abgeschlossene Menge von Konstanten
- Menge der Werte ändert sich nicht
```Java
//Enums seit Java 1.7
enum Weekday {
	MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
}

class Weekday {
	static final Weekday MONDAY;
	static final Weekday TUESDAY;
	...
}

//If-Verzweigung
Weekday day = Weekday.MONDAY;
if (day == Weekday.MONDAY){
	paule.write("I hate Mondays'");
}

//Switch Verzweigung
switch (day) {
	case TUESDAY:
		...
		break;
	case SUNDAY:
		...
		break;
}

```

## Vergleiche von Varibalenwerten
### Wertegleichheit ``==``
- keine Objekte sondern direkt die Werte (primitive Werte/Objektreferenzen) speichern
### Referenzgleichheit ``equals``
- Prüft zwei Objekte auf Inhaltsgleichheit
#### Testen auf Objektgleichheit ==
- Wann zwei Objekte wertegleich (das Gleiche im Gegensazu zu dasselbe)?
![[EqualBeispiel1.png|500]]
#### Flache Objektgleichheit - Equals
![[EqualBeispiel2.png|500]]
- vergleicht ob Referenz die Gleiche
#### Tiefe Objektgleichheit - Deep Equals
![[EqualBeispiel3.png|500]]
- vergleicht ob Entitäten identisch

## Vergleiche auf Ordnungen
- elementaren Operatoren <,> für Wertevergleichheit
- ``CompareTo(...)`` Operation für Ordungen auf Objekten

## Veränderliche vs. Unveränderliche Typen
### Veränderliche Typen
- Objektzustand kann sich auch nach Konstrukturaufruf noch ändern
### Unveränderliche Typen
- Objekte, deren Zustand nur während Ausführung des Konstruktors gesetzt werden kann
#### Vorteile
- einfach zu konstruieren/testen/nutzen
- niemals kopiert werden
- nicht defensiv kopiert werden, wenn Attributwerte genutzt werden
- Klasseninvariante wird bei Konstruktion hergestellt und gilt für gesamte Objekt-Lebenszeit 
- Schlagen "atomar" fehl: wenn unveränderliches Objekt Ausnahme auslöst, ist es niemals in ungewollten/inkonsistenten Zustand
- Eignen sich als Schlüsselwerte für Maps/Sets (hier Schlüsselwerte nicht ändern dürfen)
#### Regeln für Code unveränderlicher Klassen
- Alle Objektvariablen ``private`` & ``final``
- Erzwinge vollständige Konstruktion alleine mit Konstuktoraufruf
- Auf API keine Operation die Zustand des Objekts verändern könnte
- Wenn veränderliche Objekte in Objektvariablen gespeichert, diese defensiv kopieren oder selbst unveränderlich sein
- Sicherstellen, dass Klasse nicht vererbt werden kann
	- z.B. durch ``final`` oder statische Fabrikmethoden mit privaten Konstruktoren
#### Beispiel: String
![[ImmutableBeispielString.png|500]]

## Record Typen
### Problemstellung:
- Unveränderliche Klassen in Java selbst erstelln mühsam
- gutes Programm brauch solche Klassen sehr oft aufgrund der vielen positiven Eigenschaften
### Lösung: Records
- spezielle Klassen
- per Definition unveränderlich
- sehr gute Eignung als Data Transfer Objects (DTO)
### Eigenschaften
- „it's forbidden to declare **instance fields** explicitly inside records (and reminder: all fields are final, which is a very impotent distinction);  
 - extends clause is not allowed with **records**, because every **record** implicitly extends abstract class Record;  
- **record** can't be declared with any of these modifiers: abstract, sealed, or non-sealed (as a consequence of being implicitly final);  
-  **records** can't declare instance initializers and native methods.“  
	- Records können jedoch Methoden überschreiben sowie überladene Konstrukturen haben