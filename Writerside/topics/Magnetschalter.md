# Magnetschalter

Magnetschalter mit dem micro:bit
Was macht die Komponente?
Ein Magnetschalter (auch Reed-Schalter genannt) ist ein Sensor, der auf ein magnetisches Feld reagiert, indem er seinen Schaltzustand ändert. Er kann verwendet werden, um die Anwesenheit oder Abwesenheit eines Magneten zu erkennen.
Ist es ein Sensor, Aktor, …?
Es ist ein Sensor.
Wie muss man es anschließen?
Ein Ende des Schalters an einen digitalen I/O-Pin des micro:bit (z. B. Pin 0).
Das andere Ende des Schalters an den GND-Pin des micro:bit.
Optional: einen Pull-up-Widerstand (ca. 10k Ohm) zwischen dem I/O-Pin und dem 3V-Pin, falls der interne Pull-up-Widerstand des micro:bit nicht verwendet wird.


## Wie sieht ein minimales Demo-Programm für diese Komponente aus?

![image_2.png](image_2.png)

# Definiere den Pin für den Magnetschalter
magnet_switch_pin = pin0

while True:
# Lese den Zustand des Magnetschalters
if magnet_switch_pin.read_digital() == 1:
display.show(Image.YES)
else:
display.show(Image.NO)

    sleep(500)
Für was könnte man die Komponente einsetzen?
Der Magnetschalter könnte zur Überwachung von Türen und Fenstern verwendet werden, z.B. in Alarmanlagen.
Er kann zur Positionserkennung in Maschinen und Robotern eingesetzt werden.
Er eignet sich gut für detektionen, ob ein Bauteil oder Objekt an einem bestimmten Platz ist.
Der Sensor kann in Zähl- und Messsystemen verwendet werden, die den Durchgang von Objekten erfassen.
Er kann auch in Magnetspielzeugen oder interaktiven Projekten zur Erkennung von Magneten verwendet werden.