---
sidebar_position: 3
---

# Code

Eerst moet je de juist library importeren:

```py
from time import sleep
from leaphymicropython.actuators.rgbled import RGBLed
```
Maak een rgbled object en vul de pinnen in tussen de strings voor de rode, groene en 
blauw pin

```py
led = RGBLed(9, 10, 11)
```
Dan ga je een loop gebruiken om constant de kleur te laten veranderen

```py
while True:
    led.set_color(255, 0, 0) 
    sleep(1)
    led.set_color(0, 0, 0)
    sleep(1)
```
## Uitleg hoe de functies werken

### RGBLed(red_pin, green_pin, blue_pin)
Initialiseert het RGB LED-object door de GPIO-pinnen te specificeren die verbonden zijn met de rode, groene en blauwe componenten.

#### Parameters:

Red_pin: Het GPIO-pinnummer verbonden met het rode LED-kanaal.

Green_pin: Het GPIO-pinnummer verbonden met het groene LED-kanaal.

Blue_pin: Het GPIO-pinnummer verbonden met het blauwe LED-kanaal.
### set_color(red, green, blue)
Stelt de kleur van de RGB LED in door de intensiteit van de rode, groene en blauwe kanalen te specificeren. Elke parameter moet een waarde tussen 0 en 255 zijn.

#### Parameters:
Red: Intensiteit van het rode kanaal (0-255).
Green: Intensiteit van het groene kanaal (0-255).
Blue: Intensiteit van het blauwe kanaal (0-255).