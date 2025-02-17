---
sidebar_position: 1
---

# Hoe schrijf ik dit in MicroPython?

## Voorbeeld code

```py
from machine import Pin, PWM
from time import sleep
from leaphymicropython.sensors.linesensor import calibrate_analog_line_sensor

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
    left = calibrate_analog_line_sensor(pin=14,
                                        below_white=4000,
                                        above_black=6000,
                                        test='no') # verander 'no' naar 'yes' voor het kalibreren
    right = calibrate_analog_line_sensor(pin=15,
                                         below_white=4000,
                                         above_black=6000,
                                         test='no') # verander 'no' naar 'yes' voor het kalibreren
    if left == 'white' and right == 'white':
        # vooruit
        pwm_a.duty_u16(65535) # motor a op de hoogste snelheid
        pwm_b.duty_u16(65535) # motor b op de hoogste snelheid
    if left == 'white' and right == 'black':
        # links bijsturen
        pwm_a.duty_u16(65535) # welke motor wil je op 0 zetten?
        pwm_b.duty_u16(65535) # welke motor wil je op 0 zetten?
    if left == 'black' and right == 'white':
        # rechts bijsturen
        pwm_a.duty_u16(65535) # welke motor wil je op 0 zetten?
        pwm_b.duty_u16(65535) # welke motor wil je op 0 zetten?
    sleep(0.01) # geef de robot even tijd om na te denken
```



