---
sidebar_position: 3
---

# Code

eerst moet je de juiste library importeren:

```py
from time import sleep
from leaphymicropython.actuators.dcmotor import DCMotor
from leaphymicropython.sensors.sonar import read_distance
```
Daarna gebruik je dan een loop om continu de afstand te meten en de motor
te besturen op basis van de afstand:

```py
while True:
    distance = read_distance()
    motor = DCMotor()
    if distance < 10:
        motor.left(255, 1)
        sleep(1)
    else:
        motor.forward(255)
```

## Uitleg hoe de functies werken

### read_distance():
Leest de afstand van de ultrasone sensor en retourneert de waarde in centimeters.

### DCMotor():
Initialiseert het DC motor-object, waarmee je de bewegingen van de motor kunt 
regelen.

### motor.left(speed, duration):
Laat de motor naar links draaien met de opgegeven snelheid (0-255) gedurende de 
opgegeven duur in seconden.

### motor.forward(speed):
Laat de motor vooruit bewegen met de opgegeven snelheid (0-255). De motor blijft 
vooruit bewegen totdat er een ander commando wordt gegeven.

### Voorbeeldgedrag:
Als de afstand die door de ultrasone sensor wordt gemeten minder dan 10 cm is, 
draait de motor 1 seconde lang op volle snelheid naar links. Als de afstand groter
dan of gelijk aan 10 cm is, beweegt de motor op volle snelheid vooruit.