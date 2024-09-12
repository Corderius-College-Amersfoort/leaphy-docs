---
sidebar_position: 3
---

# Code

Eerst moet je de juiste library importeren:

```py
from leaphymicropython.actuators.servo import set_servo_angle
```

Gebruik dan de functie set_servo_angle om de servo naar de gewenste hoek te draaien:

```py
set_servo_angle(pin_number, angle)
```

## Uitleg hoe de functies werken

### Parameters:
Pin_number: Het GPIO-pinnummer waarop de servo is aangesloten.

Angle: De hoek waarop de servo moet draaien (0-180 graden).