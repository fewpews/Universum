# Ausnahmen
- Kommandos aufgerufen, obwohl Vorbedingungen nicht erfüllt
- Speicher Java Virtual Machine erschöpft
- ...

## Ausnahmeobjekt
- Verzweigung
	- else behandelt Ausnahmefall
		- Werfen eines Ausnahmeobjekts
		- `...} else {throw new IllegalArgumentException();}`
## Behandlung
```Java
try{
	paule.move();
	paule.pickGrain();
} catch (FrontBlockedException exc) {          //wenn Ausnahme in try-Block
	//code handling exception
} catch (NoGrainOnTileExcetption exc){
	throw exc;
	//in nächsthöhere Ebene melden
	//weiterwerfen desselben Ausnahmeobjekts
} finally {                              //ausgeführt nach try-/catch-Block
	//code executed in each case
}
```
Oder:
```
} catch (FrontBlockedException | NoGrainOnTileException exc) {...}
```

## Dokumentation
```
/**
...
*@throws FrontBlockedException ... [Teil API]
*/

/*@
...
@ signals (FrontBlockedException e) position.equals(\old(position)) [JML]
@*/

public void move(){
...
}
```

## Checked Exceptions
- Wenn Error außerhalb der Kontrolle des Programms
- Java Compiler erkennt Fehler
## Unchecked Exceptions
- Error in der Logik des Programms
- Java Compiler erkennt Fehler nicht -> RuntimeException zur Laufzeit