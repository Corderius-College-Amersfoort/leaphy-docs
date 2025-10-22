---
sidebar_position: 1
displayed_sidebar: null
---

# Debuggen

Hieronder vind je een lijst met veelvoorkomende problemen en tips om ze op te lossen.

## Stroom

<details>
  <summary>Mijn robot doet helemaal niets!</summary>
  
  - **Controleer het groene lampje op je microcontroller:** Brandt deze niet, dan krijgt de microcontroller geen stroom. 
  - **Controleer of de ON/OFF switch op ON staat op je `Murphy Shield`** 
  - **Controleer of de ON/OFF switch op ON staat op je `Motor Shield`** 
  - **Controleer of de ON/OFF switch op ON staat op je `batterijhouder`** 


</details>

<details>
    <summary>Mijn computer heeft geen verbinding met de robot</summary>
  - **Controleer de USB-kabel:** Is de kabel goed aangesloten op zowel de computer als de microcontroller? Probeer een andere USB-poort of een andere kabel.
  - **Controleer de interpreter**: Staat er rechtsonder in Thonny iets wat begint met `Micropython (RP2040)...`, dan is alles goed! Zo niet, klik dan rechtsonder en kies wat begint met `Micropython (RP2040)`.
  - **Controleer de poortinstellingen in Thonny:** Ga naar `Run > Configure interpreter...` en zorg ervoor dat de juiste poort is geselecteerd. Soms helpt het om de microcontroller los te koppelen en opnieuw aan te sluiten, en dan in Thonny op de 'Stop/Restart backend' knop te drukken.
</details>

<details>
  <summary>Mijn computer heeft alleen maar USB-C ingangen</summary>

Dan heb je een zeer moderne laptop! Heb je toevallig een USB-C naar USB-A adapter?
Overleg anders even met je docent!
</details>

## IR-sensoren
<details>
  <summary>Mijn sensor geeft rare of geen waardes.</summary>
  
  - **Krijgt de sensor stroom?** Is de sensor aangesloten op de juiste pinnen? Als het groene lampje op de sensor brandt, dan krijgt deze in ieder geval stroom!
  - **Print de sensorwaardes:** De beste manier om te zien wat een sensor doet, is door de waardes continu te printen in de 'Shell'.
    ```python
    from leaphymicropython.sensors.ir import IR
    from time import sleep
    
    # Vervang A0 door de pin waar jouw sensor op aangesloten is
    ir_sensor = IR("A0") 
    
    while True:
        print(ir_sensor.read_analog())
        sleep(0.1)
    ```
    Beweeg nu je hand boven de sensor of houd er een zwart/wit vel papier voor. Zie je de waardes veranderen?
</details>

<details>
  <summary>Mijn lijnvolger volgt de lijn niet.</summary>
  
  - **Kalibreer je sensoren:** De waardes voor 'zwart' en 'wit' kunnen verschillen per ondergrond en lichtinval. Print de waardes van je IR-sensoren boven de lijn en naast de lijn. Bepaal een goede 'drempelwaarde' (threshold) in je code om te beslissen of de sensor de lijn ziet.
  - **Controleer de sensorpositie:** Staan de sensoren niet te ver van de grond? Staan ze op de juiste breedte om de lijn te kunnen detecteren?
  - **Controleer je logica:** Wat moet de robot doen als de linker sensor zwart ziet? En de rechter? En als ze allebei wit zien? Loop je code stap voor stap na in je hoofd (of op papier).
</details>

## Motoren

<details>
  <summary>Eén of beide motoren werken niet.</summary>
  
  - **Gebruik de `test()` functie:** De `leaphymicropython` bibliotheek heeft een handige testfunctie.
    ```python
    from leaphymicropython.actuators.dcmotor import DCMotors
    motoren = DCMotors()
    motoren.motor_a.test() # Test motor A
    motoren.motor_b.test() # Test motor B
    ```
    Als de motor kort vooruit en achteruit beweegt, weet je dat de aansturing en bedrading goed zijn.
  - **Controleer de snelheid:** Een snelheid onder de `200` is vaak te laag om de robot in beweging te krijgen vanwege het gewicht. Probeer de motor met maximale snelheid aan te sturen: `motor_a.forward(255)`.
  - **Controleer de bedrading:** Zitten de draden van de motor goed in de schroefterminals van het motor shield? Zitten de jumper wires van het shield naar de Nano goed?
</details>

<details>
  <summary>De robot rijdt de verkeerde kant op.</summary>
  
  - **Draai de draden om:** De makkelijkste manier om de draairichting van een DC-motor om te draaien, is door de twee draden die van de motor naar het motor shield lopen om te wisselen.
  - **Pas de code aan:** Je kunt ook `forward()` en `backward()` in je code omwisselen. Dit is handig als je de draden niet wilt aanpassen.
</details>


