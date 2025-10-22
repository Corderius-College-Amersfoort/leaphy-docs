---
sidebar_position: 3
---

# 2 Analoge IR sensoren uitlezen

Hierbij een voorbeeld van hoe je twee analoge ir-sensoren kunt aansluiten en kunt uitlezen.

![1 analog ir met shield](2_analog_ir_with_shield.png)

```python
from leaphymicropython.sensors.linesensor import AnalogIR
from time import sleep

a0 = AnalogIR("A0", 2500)
a1 = AnalogIR("A1", 2500)

while True:
    a0_ir = a0.get_analog_value()
    a0_color = a0.black_or_white()
    
    a1_ir = a1.get_analog_value()
    a1_color = a1.black_or_white()

    print()
    print(a0_ir, a0_color) # waardes verbonden aan A0
    print(a1_ir, a1_color) # waardes verbonden aan A1
    sleep(0.01)
```