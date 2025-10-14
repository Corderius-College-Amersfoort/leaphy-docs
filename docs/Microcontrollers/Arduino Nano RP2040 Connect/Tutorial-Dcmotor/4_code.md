---
sidebar_position: 4
---

# De motoren aansturen

## Motoren testen

```python
from leaphymicropython.actuators.dcmotor import DCMotors

motoren = DCMotors()
motor_a = motoren.motor_a 
motor_a.test()
```
Wat gebeurt hier?
- `from leaphymicropython.actuators.dcmotor import DCMotors`: hiermee importeer je de functie van de library
- `motoren = DCMotors()`: hiermee vertellen we aan de computer welke pinnen we gebruiken voor de motoren
- `motor_a = motoren.motor_a`: we hebben nu toegang tot motor A (de letter A staat op het motor shield, maar waarschijnlijk kun je dit nu niet meer zien vanwege de jumper wires) 
- `motor_a.test()`: nu testen we kort vooruit en achteruit van motor A. Dan weet je ook meteen welke dat is.

Doe hetzelfde voor motor B.

```python
from leaphymicropython.actuators.dcmotor import DCMotors

motoren = DCMotors()
motor_b = motoren.motor_b
motor_b.test()
```

## Belangrijkste motorfuncties

`forward` en `backward` zijn de belangrijkste functies om de motoren aan te sturen. Je geeft een snelheid mee tussen 0 en 255. 

`Let op`: vanwege het gewicht van je robot kan het zijn dat de robot pas begint te rijden bij 200. Onder de 200 probeert de motor het wel (je ziet het lampje op je shield wel aan gaan), maar de robot komt niet in beweging.

<details>
    <summary>Voorbeeld van maximaal vooruit bij motor B</summary>


```python
from leaphymicropython.actuators.dcmotor import DCMotors

motoren = DCMotors()
motor_b = motoren.motor_b
motor_b.forward(255)
```

</details>


<details>
    <summary>Voorbeeld van maximaal achteruit bij motor B</summary>


```python
from leaphymicropython.actuators.dcmotor import DCMotors

motoren = DCMotors()
motor_b = motoren.motor_b
motor_b.backward(255)
```

</details>




