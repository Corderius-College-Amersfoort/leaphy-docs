---
sidebar_position: 3
---

# Code

Eerst moet je de juiste library importeren:

```py
from time import sleep
from leaphymicropython.sensors.sonar import read_distance
```
En dan gebruik je een loop om te zorgen dat de afstand in centimeter om de seconde
wordt geprint

```py
while True:
    print(read_distance(2,3))
    sleep(1)
```
