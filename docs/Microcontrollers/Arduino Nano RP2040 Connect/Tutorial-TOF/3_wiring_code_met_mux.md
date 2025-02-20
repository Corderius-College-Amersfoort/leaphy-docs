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
Dat je **channel** op het goed getal zet. 
In het voorbeeld hebben we verbonden met channel 7. Zie het geval zeven boven de verbonden pinnen.