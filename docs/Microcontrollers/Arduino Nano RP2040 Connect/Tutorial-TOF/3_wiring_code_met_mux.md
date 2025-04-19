---
sidebar_position: 2
---


# Wiring & Code met multiplexer

## Wiring
![wiring tof mux](tof_mux.png)

## Code
```python

from leaphymicropython.sensors.tof import TimeOfFlight
from time import sleep

tof = TimeOfFlight(channel=7)

while True:
    print(tof.get_distance())
    sleep(1)
```

## Let op
Dat je **channel** op het goede getal zet. 
In het voorbeeld hebben we de sensor verbonden met channel 7. Dit kun je weten vanwege het getal zeven boven de verbonden pinnen.

## Tips

### Tip: beschermend stukje plastic
Het kan zijn dat er nog een beschermend stukje plastic op de sensor zit.
Als je deze ervan af haalt, kan de sensor accurater zijn.

### Tip: letterlijk verbindingsproblemen
Het kan zijn dat er kort geen verbinding is met de sensor. Dit kan tot een foutmelding leiden.
We hebben dit weten te voorkomen in de software, maar als er verbindingsproblemen zijn, zie je dit in de Console als waarschuwing.
