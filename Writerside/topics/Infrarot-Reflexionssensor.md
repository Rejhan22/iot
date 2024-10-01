# Infrarot Reflexionssensor

### IR-Reflexionssensor mit dem micro:bit

**Was macht die Komponente?**
- Ein IR-Reflexionssensor erkennt das Vorhandensein oder Fehlen von Objekten durch das Senden von Infrarotlicht und das Messen des zurückreflektierten Lichts. Dies wird häufig zur Abstandsmessung oder zur Erkennung von Farbkanten (z.B. bei Robotern) verwendet.

**Ist es ein Sensor, Aktor, …?**
- Es ist ein Sensor.

**Wie muss man es anschließen?**
- VCC (Stromversorgung, meist 3.3V oder 5V) an den 3V-Pin des micro:bit.
- GND (Masse) an den GND-Pin des micro:bit.
- Signal (analoges oder digitales Ausgangssignal) an einen analogen oder digitalen I/O-Pin des micro:bit (z. B. Pin 0).

**Wie sieht ein minimales Demo-Programm für diese Komponente aus?**

MicroPython Beispiel:
```python
from microbit import *

# Definiere den Pin für den IR-Reflexionssensor
ir_sensor_pin = pin0

while True:
    # Lese den IR-Wert (0-1023)
    ir_value = ir_sensor_pin.read_analog()
    
    # Beurteile ob ein Objekt erkannt wurde (Schwellenwert bei ~500)
    if ir_value < 500:
        display.show(Image.YES)
    else:
        display.show(Image.NO)
    
    sleep(500)
```

**Für was könnte man die Komponente einsetzen?**
- Der IR-Reflexionssensor könnte zur Linienverfolgung bei Robotern verwendet werden.
- Er kann zur Objekterkennung und Abstandsmessung eingesetzt werden.
- Er eignet sich gut für die Zählung von Objekten auf einem Förderband.
- Der Sensor kann in Robotikprojekten zur Kollisionvermeidung eingesetzt werden.
- Er kann auch verwendet werden, um Einbrüche zu detektieren oder die Anwesenheit von Objekten in einem bestimmten Bereich zu überwachen.