---
sidebar_position: 3
---


# Code

eerst moet je de juiste library importeren:

```py
from leaphymicropython.actuators.buzzer import set_buzzer
```

Daarna gebruik je de set_buzzer functie om het geluid te maken:

```py
set_buzzer(pin_number, pwm_value, frequency)
```
## Uitleg hoe de functies werken:
### Pin_number:
Het pinnummer waaraan de buzzer is verbonden.

### Pwm_value:
De duty cycle voor de buzzer, die het volume van de piep bepaalt. Deze waarde ligt tussen 0 - 255.

### Frequency:
De frequentie van de piep, die de toonhoogte van het geluid bepaalt

