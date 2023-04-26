# Mehrband-Turingmaschinen
- Definiert wie 1-Band-TM, nur mehrere Bänder
	- pro Band ein Schreib-/Lesekopf
	- Übergangsfunktion von $Z \times \Gamma^k$ nach $Z \times \Gamma^k \times \{L,R,N\}^k$
## Satz
- Zu jeder Mehrband-Turingmaschine $M$ gibt es eine 1-Band-TM $M'$ mit $T(M)$ bzw. bei Funktionenberechnung so, dass $M$ und $M'$ diesselbe Funktion berechnen
### Beweis
- Idee: Spuren ersetzen die $k$-Bänder
- Problem: Viele Köpfe durch einen simulieren
- Lösung:
	- Zwei Bänder als zwei Spuren simulieren
	- Bandalphabet $\Gamma$ wird ersetzt durch $\Gamma' \times \Gamma'$ mit $\Gamma' = \Gamma \cup \{\hat{\gamma} \mid \gamma \in \Gamma\}$
	- **Hütchen** markierte eine *virtuelle Kopfposition*
	- ABER: für jeden Schritte der ursprünglichen TM muss man einmal das gesamte Band durchgehen
		- Einmal wird das gesamte Band (z.B. von links nach rechts) gelesen. Dabei werden alle Informationen gesammelt, die notwendig sind, um festzustellen, welcher Übergang durchzuführen ist.  
		- Nun wird das gesamte Band noch einmal (diesmal von rechts nach links) gelesen, wobei die zum durchgeführten Übergang gehörenden Änderungen ausgeführt werden.

## Notation für spezielle TM
- 1-Band-TM $M$
- $M(i,k)$: $k$-Band-Maschine, die wie $M$ arbeitet, Band $i$ als Arbeitsband
	- Übergang $\delta(z,a) = (z',b,y)$
	- Wird in $M(i,k)$ zu Übergang $\delta(z, c_1,...,c_{i-1},...,c_k)=(z',c_1,...,c_{i-1},...,c_k,N,...,N,y,N,...,N)$ 
- $M(i)$: wenn $k$ uninteressant

- $Band := Band + 1$ oder $Band := Band -1$
- $Band \: i := Band \: i +1$ oder $Band \:i :=Band \: i -1$
	- $M$ Inkrement-Funktion / $M'$ Dekrement-Funktion
	- Dann sind $M(i)$ und $M'(i)$ die obigen Machschinen
- $Band \: i := 0$
- $Band \: i := Band \: j$

## Hintereinanderausführung
- Flussdiagrammnotation
	- start $\rightarrow M_1 \rightarrow M_2 \rightarrow$ stop
- Programmiersprachen-Notation
	- $M_1;M_2$ 
	- Bedeutung
		- $M = (Z_1 \cup Z_2, \Sigma, \Gamma_1 \cup \Gamma_2, \delta, z_1, \square, E_2)$ mit $\delta = \delta_1 \cup \delta_2 \cup \{(z,a,z_2,a,N) \mid z \in E_1, a \in \Gamma_1\}$
		- $Z_1 \cap Z_2 = \emptyset$ 
### Anwendung/Variation
- Erzeugen der Konstante 5 auf Band 3 und 6 auf Band 5
	- Sei $M:$ $Band \: := \: Band \: +1$
	- $\hat{M}:$ start $\rightarrow M \rightarrow M \rightarrow M \rightarrow M \rightarrow M \rightarrow$ stop
	- $Band \: 3 := 0; \hat{M}(3); \: Band \: 5 := 0; \hat{M}(5); M(5)$
- Notation für Aufspaltung
	- start $\rightarrow M_0 \overset{z_{e_1}}{\rightarrow} M_1 \rightarrow$ stop
	- oder     $M_0$ $\overset{z_{e_2}}{\rightarrow} M_2 \rightarrow$ stop

## Nulltest
Turingmaschine, die abfragt, ob $Band \: i$ den Wert $0$ hat:
- $\delta(z,a) = (nein, a, N)$ für alle $a \in \Gamma \setminus \{0\}$
- $\delta(z,0) = (z_1,0,R)$
- $\delta(z_1,a) = (nein,a,N)$ für alle $a \in \Gamma \setminus \{\square\}$
- $\delta(z_1, \square) = (ja, \square, L)$
Wir schreiben $Band \: i = 0?$ 

## While-Schleife als TM
- Nulltest-Maschine für Ablaufkontrolle
![[MehrbandTuring.png|200]]
- $while \: Band \: i \neq 0 \: do \: M$