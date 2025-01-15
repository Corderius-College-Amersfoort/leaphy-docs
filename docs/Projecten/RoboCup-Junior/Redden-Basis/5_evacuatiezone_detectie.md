---
sidebar_position: 5
---

# Detectie evacuatiezone

## Via pull-up resistor
![aluminiumtape detectie](aluminium_tape_detectie_bb.png)

## Code
```python 
import machine
from machine import Pin
from time import sleep

pin = machine.Pin("D2", Pin.IN, Pin.PULL_UP)

while True:
    print(pin.value())
    sleep(0.1)
```

Zodra de twee draden verbinding maken met het aluminiumtape, zal pin D2 op 0 komen te staan.

## Via RGB sensor
Geeft de RGB sensor een andere waarde bij:
- wit
- zwart
- de aluminiumtape die hoort bij de overgang naar de evacuatiezone?








