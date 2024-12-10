---
sidebar_position: 2
---

# Een kleur kiezen bij ingebouwd lampje

We gaan het ingebouwde lampje aanzetten, maar dan een kleur kiezen.

## Stap 1: De code
Kopieer dit stukje code in je editor en draai het:

```python 
from machine import Pin
from time import sleep

# je kunt kiezen tussen:
# LED_GREEN, LED_BLUE of LED_RED
led_pin = Pin('LED_RED', Pin.OUT)

while True:
    led_pin.value(0) # zet het lampje aan
    sleep(1)         # wacht een seconde
    led_pin.value(1) # zet het lampje uit
    sleep(1)         # wacht een seconde
```
## Stap 2: Bedoel je niet 1 aan en 0 uit?
Helaas niet. Bij de ingebouwde RGB LED is:
- .value(0) --> AAN
- .value(1) --> UIT

## Stap 3: andere kleuren
- Kun je ook blauw en groen laten zien?
- Wat gebeurt er als je blauw en groen tegelijkertijd aan zet?


