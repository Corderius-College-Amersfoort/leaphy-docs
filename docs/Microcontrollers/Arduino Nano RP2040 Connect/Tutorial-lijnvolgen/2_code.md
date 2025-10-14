---
sidebar_position: 1
---

# Hoe schrijf ik dit in MicroPython?

## Voorbeeld code

```py
from leaphymicropython.sensors.linesensor import AnalogIR
from leaphymicropython.actuators.dcmotor import DCMotors

motoren = DCMotors()
motor_a = motoren.motor_a
motor_b = motoren.motor_b

a0 = AnalogIR("A0", 2500) # we gaan ervan uit dat A0 de linker sensor is
a1 = AnalogIR("A1", 2500) # we gaan ervan uit dat A1 de rechter sensor is

while True:
    a0_ir = a0.get_analog_value()
    left = a0.black_or_white()

    a1_ir = a1.get_analog_value()
    right = a1.black_or_white()

    if left == 'white' and right == 'white':
        motor_a.forward(255)
        motor_b.forward(255)
    if left == 'white' and right == 'black':
        # links bijsturen
        motor_a.forward(255) # welke motor wil je lager zetten om te sturen?
        motor_b.forward(255) # welke motor wil je lager zetten om te sturen?
    if left == 'black' and right == 'white':
        # rechts bijsturen
        motor_a.forward(255) # welke motor wil je lager zetten om te sturen?
        motor_b.forward(255) # welke motor wil je lager zetten om te sturen?
    sleep(0.01) # geef de robot even tijd om na te denken
```



