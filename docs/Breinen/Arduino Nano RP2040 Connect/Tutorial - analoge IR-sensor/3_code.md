---
sidebar_position: 3
---

# Code

Eerst moet je de juiste library importeren:

```py
from time import sleep
from leaphymicropython.utils.pins import read_analog
```
En dan gebruik je een loop om te zorgen dat de ir waaarde om de seconde
wordt geprint

```py
while True:
    print(read_analog(1))
    sleep(1)
```
