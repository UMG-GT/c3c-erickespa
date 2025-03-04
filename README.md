### Tarea C3C

---

De la máquina de estados finitos propuesta por usted (Tarea C3B), realice el Timing Analysis utilizando compuertas lógicas y flip-flops reales. Muestre los cálculos, deducción, procedimiento, etc. Para mostrar el cálculo de:

· Máxima frecuencia de operación de su circuito

· Cumplimiento de restricción hold

Realice este calculo entre la lógica (output logic 1st stage + next logic 2nd stage) de las dos maquinas de estado finito. 

* Archivo de excel [Ver el archivo](https://github.com/UMG-GT/c3c-erickespa/blob/main/Tarea%20C3C/setup%20time%20y%20hold%20time.xlsx)


## Setup Time (Maxima Frecuencia de Funcionamiento)

componentes usados:

- and        [link](https://www.digikey.com/en/products/detail/texas-instruments/SN74HCS21PWR/12165103)
- or         [link](https://www.digikey.com/en/products/detail/toshiba-semiconductor-and-storage/TC7SZ32FU-LJ-CT/870694)
- inverter   [link](https://www.digikey.com/en/products/detail/texas-instruments/SN74LVC1G14DBVR/385724)
- flip-flop  [link](https://www.digikey.com/en/products/detail/texas-instruments/SN74LVC2G74DCUR/467989)

segun su datasheet los valores con una alimentacion de 2 voltios son:

- tpd and = 22 ns
- tpd or = 3 ns
- tpd inverter = 6.5 ns
- tpcq flip-flop = 8.1 ns
- tsetup flip-flop = 1.7 ns

los calculos realizados van dentro el archivo excel

Tc = tpcq + tpd + tsetup

Tc = 16.2 ns + 116.5 ns + 3.4 ns

Tc = 136.1 ns

Fc = 1 / 136.1 ns = 7.35 MHz Frecuencia maxima a la que puede funcionar mi fsm con estos componentes

---

## Hold Time

segun el datasheet el thold del flip-flop es 0.3 ns, por lo que la suma de tccq y tcd tiene que ser mayor a esta.

los calculos realizados van dentro el archivo excel

el tcd para la primera parte logica (moore)

tcd = 22 ns

ya solo con el tcd se ve que tccq+tcd es mayor que el thold.

el tcd para la segunda parte logica (mealy)

tcd = 25 ns 

tambien solo con el tcd se ve que tccq+tcd es mayor que el thold.

ya que ambos son mayor que el thold del flip-flop no se necesitaria buffers.
