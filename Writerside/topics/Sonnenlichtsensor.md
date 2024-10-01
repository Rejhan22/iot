# Sonnenlichtsensor

### Sonnenlichtsensor mit dem micro:bit

**Was macht die Komponente?**
- Ein Sonnenlichtsensor misst die Intensität des Umgebungslichts und kann zur Erkennung von Helligkeit, Sonnenlicht und zur Steuerung von Beleuchtungssystemen verwendet werden.

**Ist es ein Sensor, Aktor, …?**
- Es ist ein Sensor.

**Wie muss man es anschließen?**
- VCC (Stromversorgung, meist 3.3V oder 5V) an den 3V-Pin des micro:bit.
- GND (Masse) an den GND-Pin des micro:bit.
- Signal (analoges Ausgangssignal) an einen analogen I/O-Pin des micro:bit (z.B. Pin 0).

**Wie sieht ein minimales Demo-Programm für diese Komponente aus?**

MicroPython Beispiel:
```python
from microbit import *

# Definiere den Pin für den Sonnenlichtsensor
light_sensor_pin = pin0

while True:
    # Lese den Lichtwert (0-1023)
    light_value = light_sensor_pin.read_analog()
    
    # Zeige den Lichtwert auf dem Display
    display.scroll('Light: {}'.format(light_value))
    
    sleep(1000)
```

**Für was könnte man die Komponente einsetzen?**
- Der Sonnenlichtsensor könnte zur Automatisierung von Beleuchtungssystemen verwendet werden.
- Er kann in intelligenten Jalousien oder Vorhängen eingesetzt werden, die sich je nach Lichtintensität öffnen oder schließen.
- Er eignet sich gut für Solarenergieprojekte, um die optimale Ausrichtung von Panels zu ermitteln.
- Der Sensor kann zur Überwachung und Anpassung der Beleuchtung in Gewächshäusern verwendet werden.
- Er kann in Geräten zur Messung der Umgebungshelligkeit und Wetterstationen eingesetzt werden.