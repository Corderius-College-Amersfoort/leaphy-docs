---
sidebar_position: 2
---

# 1 Analoge IR sensor uitlezen


Hierbij een voorbeeld van hoe je een analoge ir-sensor kunt aansluiten en kunt uitlezen.

![1 analog ir met shield](1_analog_ir_with_shield.png)

```python
from leaphymicropython.sensors.linesensor import AnalogIR

a0 = AnalogIR("A0", 2500)

while True:
    a0_ir = a0.get_analog_value()
    a0_color = a0.black_or_white()
    
    print()
    print(a0_ir, a0_color)
```
Wat gebeurt hier?

```python
from leaphymicropython.sensors.linesensor import AnalogIR
```
Hiermee importeer je de functie van de library

```python
a0 = AnalogIR("A0", 2500)
```
1. "A0" is de pin waarmee we de sensor verbonden hebben
2. 2500 is de IR-waarde. We zeggen hiermee dat als de sensor een waarde van 2500 of meer uitleest, dat we vinden dat we zwart zien en alles eronder wit.

```python
while True:
    a0_ir = a0.get_analog_value()
    a0_color = a0.black_or_white()
```
1. "a0.get_analog_value()" --> dit geeft ons de precieze IR-waarde (een getal tussen 0 en 65353)
2. "a0.black_or_white()" --> elke IR-waarde boven jouw threshold (boven ingesteld op 2500) geeft "black". Anders "white"