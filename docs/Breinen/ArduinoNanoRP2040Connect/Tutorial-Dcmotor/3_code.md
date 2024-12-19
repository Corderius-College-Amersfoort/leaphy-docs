---
sidebar_position: 4
---

# Code met package

eerst moet je de juiste library importeren:

```py
from time import sleep
from leaphymicropython.actuators.dcmotor import DCMotor
```
Daarna zet je een loop op waarin de motor continu vooruit beweegt. Na 2 seconden maakt de motor een draai naar links voor 1 seconde. Vervolgens begint de cyclus opnieuw, waarbij de motor weer vooruit blijft bewegen.
```py
motor = DCMotor()

while True:
    motor.forward(255)  # Motor beweegt vooruit op volle snelheid
    sleep(2)  # Motor blijft 2 seconden vooruit bewegen
    motor.left(255, 1)  # Motor draait naar links voor 1 seconde
    sleep(1) 
```

## Uitleg hoe de functies werken

### DCMotor():
Initialiseert het DC motor-object, waarmee je de bewegingen van de motor kunt 
regelen.

### motor.left(speed, duration):
Laat de motor naar links draaien met de opgegeven snelheid (0-255) gedurende de 
opgegeven duur in seconden.

### motor.forward(speed):
Laat de motor vooruit bewegen met de opgegeven snelheid (0-255). De motor blijft 
vooruit bewegen totdat er een ander commando wordt gegeven.
