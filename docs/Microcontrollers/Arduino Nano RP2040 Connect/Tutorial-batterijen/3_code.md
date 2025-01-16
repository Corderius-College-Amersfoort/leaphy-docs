---
sidebar_position: 3
---

# Code
Ons doel is om de code op de micocontroller te zetten.
Als de microcontroller niet verbonden is met de laptop, dan willen we dat deze aangaat via de batterijen.

## Stap 1: Code op de microcontroller zetten
Kopieer de volgende code naar Thonny:

```python 
from machine import Pin
pin_van_lampje = Pin('LED', Pin.OUT)
pin_van_lampje.on()
```

## Stap 2: opslaan
- Click on "File" -> "Save as...".
- In the "Save as" dialog box, choose the location where you want to save the file:
  - "MicroPython device" (RP2040): Saves the file directly onto the microcontroller's file system. This is necessary for the microcontroller to run the code.

Important: When saving to the MicroPython device:
- The file must be named main.py if you want it to run automatically when the device powers up or resets.
- You might need to stop any running program on the device first. There's usually a stop button in Thonny's toolbar.

## Stap 3: loskoppelen en batterijen aanzetten
Koppel de microcontroller los van de laptop.
Als je nu de schakelaar van de batterijhouder omzet, zou het ingebouwde lampje aan moeten gaan.