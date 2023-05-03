# Arithmetische Schaltungen
## Arithmetik
- umfasst Rechengesetze (Add,Sub,Mult,Div etc.) ganzer/reeler Zahlen

## Halbaddierer - Volladdierer
![[HalbaddiererVolladdierer.png|400]]
0

### Transistorschaltung für Volladdierer
![[pulldownvolladd.png|400]]
![[pullupdownvolladd.png|400]]

### VHDL Volladdierer
```VHDL
library ieee use ieee.std_logic_1164.all;

entity full_adder is
port(
	A : in std_logic;
	B : in std_logic;
	C0 : in std_logic;
	C1 : out std_logic;
	S : out std_logic);
end entity full_adder;

architecture logic-arch of full_adder is begin
	S<= A xor B xor C_in;
	C1 <= (A and B) or (A and C0) or (B and C0);
end architecture logic-arch;
```

## 4-Bit Ripple Carry Adder
![[CarryRipple.png|400]]
### VHDL
```VHDL
library ieee use ieee.std_logic_1164.all;

entity ripple_carry_adder is
port(
	A :in std_logic_vector (3 downto 0);
	B :in std_logic_vector (3 downto 0);
	C0 :in std_logic;
	S :out std_logic_vector (3 downto 0);
	C4 :out std_logic);
end entity ripple_carry_adder

architecture structure of ripple_carry_adder is signal C :
std_logic_vector(4 downto 0);
begin -- architecture structural
	C(0) <= C0;
	ripple_adder_generation :
	for i in 0 to 3 generate full_adder_I :
	entity work.full_adder port map (
		A => A(i),
		B => B(i),
		Cin => C(i),
		Cout => C(i+1),
		S => S(i));
	end generate ripple_adder_generation;
	C4 <= C(4);
end architecture structure;
```

## Binärer Addierer-Subtrahierer
![[BinärAddSub.png|400]]
- XOR-Gatter mit Eingängen $S$ und $B_i$
	- Eingang $S$ gibt Vorzeichen an
		- Addierer falls $0$
			- $B_i \oplus 0 \Rightarrow A + B$ 
		- Subtrahierer falls $1$
			- $B_i \oplus 1 = not(B_i)$ und $C_0 = 1 \Rightarrow$ Addition von $A$ mit 2-Komplement von $B$ also Subtraktion von $B$

## Fließkommazahlen
- Format: $\pm 1.bbb...bb_2 \cdot 2^{ee...ee}$
- Wert: $(-1)^S \cdot (1+F) \cdot 2^E$ mit $E=e-B$
- Wert: $(-1)^S \cdot (1+M/2^p) \cdot 2^E$
![[zsmfFließkommazahlen.png]]

### Genauigkeiten und Datentypen
![[Genauigkeiten.png]]

### Addition und Subtraktion
1. Nullpfüfung
	- Wenn einer der Operanden den Wert $0$ annimmt, bildet der jeweils andere Operand das Ergebnis
2. Bildung der Mantisse
	- Die Mantisse des kleineren Exponenten wird solange nach rechts geschoben bis beide Exponenten identische sind
3. Addition
	- Erfolgt durch die Additon der Mantissen. Erkennung eines Überlaufs.
4. Normalisierung
	- Die Normalisierung erfolgt durch die Verschiebung der Bits der Mantisse Erkennung von Über- bzw. Unterlauf
5. Runden

#### Schaltung
![[FließAddSubSchaltung.png|400]]

### IEEE 754 Schutz- / Round-Bits
- zwei zusätliche Bits die für alle Zwischenadditionen verwendet werden
### IEEE 754 - Rundungsmodi
![[Rundungsmodi.png|400]]

### Multiplikation
1. Separieren des Vorzeichens
2. Addition der Exponenten
3. Multiplikation der Mantissen
4. Normalisieren, Runden, Über-/Unterlauf-Prüfung
5. Ersetzung des Vorzeichens

### Division
1. Separieren des Vorzeichens
2. Überprüfen der Sonderfälle: Null/Unendlich
3. Subtraktion der Exponenten
4. Division der Mantissen
5. Normalisieren & Detektion eines Über-/Unterlaufs
6. Runden
7. Ersetzen des Vorzeichens

