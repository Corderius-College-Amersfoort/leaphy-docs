---
sidebar_position: 1
---

# Ingebouwd lampje aanzetten

We gaan het ingebouwde lampje aanzetten.

## Stap 1: De code
Kopieer dit stukje code in je editor:

```python 
from machine import Pin
pin_van_lampje = Pin('LED', Pin.OUT)
pin_van_lampje.on()
```

Wil je het lampje uitzetten? Dan gebruik je:
```python
pin_van_lampje.off()
```


