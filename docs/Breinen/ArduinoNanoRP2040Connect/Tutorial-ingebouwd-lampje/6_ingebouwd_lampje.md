---
sidebar_position: 6
---

# Ingebouwd lampje aanzetten

We gaan het ingebouwde lampje aanzetten.

## Stap 1: ga naar de REPL
Hoe werkte dat ook alweer? Zie één van de vorige stappen.

## Stap 2: from machine import Pin

Typ de volgende Python code en druk op Enter
````python
from machine import Pin
````
Je krijgt niets bijzonders te zien, maar we hebben **Pin** wel nodig om verbinding te maken met de Pin die verbonden is aan het lampje.

## Stap 3: Verbinden met de Pin van het lampje 

```python
pin_van_lampje = Pin('LED', Pin.OUT)
```
We hebben nu een variabele **pin_van_lampje** die verwijst naar de Pin die verbonden is met het lampje?

## Stap 4: het lampje aanzetten en uitzetten

Aan:
```python
pin_van_lampje.on()
```
Uit:
```python
pin_van_lampje.off()
```


