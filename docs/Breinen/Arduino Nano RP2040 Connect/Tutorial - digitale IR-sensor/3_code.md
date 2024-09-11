__---
sidebar_position: 3
---

# Code


Eerst moet je de juiste library importeren:

```py
from time import sleep
from leaphymicropython.sensors.linesensor import read_line_sensor
```

Dan gebruik je een loop om steeds de ir-sensor uittelezen en dan krijg je een
1 of een 0 terug want het is digitaal
```py
while True:
print(read_line_sensor(1))
sleep(1)
```
