# Ultraschallsensor

### Ultraschallsensor mit dem micro:bit

**Was macht die Komponente?**
- Ein Ultraschallsensor misst die Entfernung zu einem Objekt, indem er Ultraschallwellen aussendet und die Zeit bis zum Eintreffen des Echos misst.

**Ist es ein Sensor, Aktor, …?**
- Es ist ein Sensor.

**Wie muss man es anschließen?**
- VCC (Stromversorgung, meist 5V) an den 3V-Pin des micro:bit.
- GND (Masse) an den GND-Pin des micro:bit.
- Trig (Trigger, um Ultraschall zu senden) an einen digitalen I/O-Pin des micro:bit (z. B. Pin 0).
- Echo (Empfängt das Echo) an einen anderen digitalen I/O-Pin des micro:bit (z. B. Pin 1).

**Wie sieht ein minimales Demo-Programm für diese Komponente aus?**

MicroPython Beispiel:
```python
from microbit import *
import time

# Definiere die Pins
trig = pin0
echo = pin1

def get_distance():
    # Sende ein 10µs Signal auf Trig-Pin
    trig.write_digital(0)
    time.sleep_us(2)
    trig.write_digital(1)
    time.sleep_us(10)
    trig.write_digital(0)
    
    # Warte auf das Echo und messe die Zeit in Mikrosekunden
    while echo.read_digital() == 0:
        pass
    start = time.ticks_us()
    while echo.read_digital() == 1:
        pass
    end = time.ticks_us()

    duration = end - start
    distance = (duration / 2) / 29.1  # Schallgeschwindigkeit

    return distance

while True:
    distance = get_distance()
    display.scroll('Distance: {} cm'.format(distance))
    sleep(1000)
```

**Für was könnte man die Komponente einsetzen?**
- Der Ultraschallsensor könnte zur Abstandsmessung verwendet werden.
- Er kann zur Objekterkennung eingesetzt werden.
- Er eignet sich sehr gut für die Füllstandsmessung in Behältern.
- Der Sensor kann zur Kollisionsvermeidung in Robotern verwendet werden.
- Er kann auch für die automatische Türöffnung eingesetzt werden.