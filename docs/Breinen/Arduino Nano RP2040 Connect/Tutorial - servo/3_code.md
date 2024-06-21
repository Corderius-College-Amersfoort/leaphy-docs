---
sidebar_position: 3
---

# Code

```python
from machine import ADC
```

```python
adc = ADC("A0")
```

```python
from time import sleep 
while True: print(adc.read_u16()); sleep(1)
```
