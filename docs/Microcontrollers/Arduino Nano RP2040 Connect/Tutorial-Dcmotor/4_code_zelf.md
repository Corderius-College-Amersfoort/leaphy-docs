---
sidebar_position: 4
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


# motor a: kies getal tussen 0 en 65535
pwm_a.duty_u16(65535) # we zetten hem op de hoogste snelheid
sleep(2) # wacht 2 seconden
pwm_a.duty_u16(0) # we zetten de motor uit

# motor b
pwm_b.duty_u16(65535) # we zetten de andere motor op de hoogste snelheid
sleep(2) # wacht 2 seconden
pwm_b.duty_u16(0) # we zetten de andere motor uit

```
