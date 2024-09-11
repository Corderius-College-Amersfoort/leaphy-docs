---
sidebar_position: 2
---

# TODO: wiring


## Belangrijke informatie over de analoge pinnen

https://support.arduino.cc/hc/en-us/articles/7454007471004-About-the-analog-pins-on-Nano-RP2040-Connect


# Hoe sluit je een analoge IR-sensor aan op een Nano RP2040 Connect
## Pinnen van de analoge IR-sensor:
VCC: De plus (3.3v)

GND: Aarde (min)

AO: De analoge uitgang
## Aansluiten op de Nano RP2040 Connect
VCC: Verbind de VCC-pin van de IR-sensor met de 3.3V-pin op de Nano RP2040 Connect

GND: Verbind de GND-pin van de IR-sensor met een GND-pin op het board.

AO: Verbind de OUT-pin van de sensor met een analoge pin van de Nano RP2040 Connect, bijvoorbeeld A2.