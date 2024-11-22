---
sidebar_position: 3
---

# Ziet de sensor zwart of wit?
Ziet de analog IR-sensor zwart of wit?
Dat is eigenlijk best een lastige taak, want we krijgen een getal tussen 0 en 65536.
We gaan ons drie vragen stellen:
1. **onder** welk getal vinden we dat de sensor wit ziet?
2. **boven** welk getal vinden we dat de sensor zwart ziet?
3. tussen welke twee getallen zijn we niet zeker en vinden we het **onduidelijk**?

Hiervoor kunnen we de volgende functie gebruiken.

```python 
from time import sleep
from leaphymicropython.sensors.linesensor import calibrate_analog_line_sensor

while True:
    calibrate_analog_line_sensor(pin=14,
                                 below_white=4000,
                                 above_black=6000,
                                 test='yes')
    sleep(0.1)
```
Wat betekenen alle opties in de functie?
- **pin**: dit is de pin op je Arduino die het signaal uitleest, hierbij **D14**
- **below_white**: onder welk getal vind jij dat de sensor wit ziet?
- **above_blakc**: boven welk getal vind jij dat de sensor zwart ziet?
- **test='yes'**: als je testen op 'ja' zet, dan zie je in de Shell de waarde en welke kleur jij vindt die hoort bij de waarde.

Zodra we zeker zijn van de waardes, kunnen we de code op de volgende manier gebruiken in ons project:

```python
from time import sleep
from leaphymicropython.sensors.linesensor import calibrate_analog_line_sensor

while True:
    color = calibrate_analog_line_sensor(pin=14,
                                         below_white=4000,
                                         above_black=6000)
    print(color)
    sleep(0.1)
```