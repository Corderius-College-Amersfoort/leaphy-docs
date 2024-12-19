---
sidebar_position: 3
---

# Code zonder package

eerst moet je de juiste library importeren:

```py
from machine import Pin, PWM
from time import sleep

# motor a
pwm_a = PWM(Pin("D3"))
pwm_a.freq(5000)
enable_a = Pin("D2", Pin.OUT)
enable_a.value(0) # wissel tussen 0 en 1 voor vooruit en achteruit

# motor b
pwm_b = PWM(Pin("D11"))
pwm_b.freq(5000)
enable_b = Pin("D4", Pin.OUT)
enable_b.value(0) # # wissel tussen 0 en 1 voor vooruit en achteruit

while True:

    # motor a
    pwm_a.duty_u16(220 * 257) # getal tussen 0 en 65534
    
    # motor b
    pwm_b.duty_u16(200 * 257) # getal tussen 0 en 65534
    
    sleep(1)
```
