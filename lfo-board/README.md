### Longwave

[StompLFO][stomplfo] breadboard-friendly adapter board that
provides power to the chip and shifts control and output
voltages to be in the [2V, 7V] range that is more
pedal-friendly than [0V, 5V].

[stomplfo]: https://electricdruid.net/product/stomplfo/

[Schematic](./longwave-v1rev2.pdf)

#### Pins

1. +9V (Input)
2. GND (Input)
3. +4.5 (Input)
4. +5.0V (Output of the on-board 5V regulator)
5. GND (Input)
6. Out (Output of the LFO)
7. GND (Input)
8. Sync (Input, external clock signal to sync LFO to)
9. Tap (Input, tap tempo, connect to GND for tap)
10. Vfreq (Input, CV for LFO speed)
11. Vof (Input, CV for LFO offset)
12. GND (Input)
13. Vform (Input, CV for LFO waveshape)
14. Vdepth (Input, CV for LFO depth)
15. GND (Input)

For minimum operation, please connect these pins. Keep in
mind for duplicate pins like GND, it's sufficient to just
connect one of the pins.

* `Pin 1`: +9V;
* `Pin 2`: GND;
* `Pin 3`: +4.5V;
* `Pin 6`: LFO Out;

#### Control Voltage ranges

All CV inputs are effective on the [2V, 7V] range. They are
also clamped in a way that it is safe to use the full [0V,
9V] range.

* `Vfreq`: 2V corresponds to ~25Hz LFO frequency, 7V to
  ~50mHz;
* `Vof`: 2V corresponds to an offset of +2.5V on the LFO
  output (LFO will "oscillate" around 7V). 7V corresponds to
  -2.5V offset; to 0V peak-to-peak, effectively a constant
* `Vdepth`: 2V corresponds to 5V peak-to-peak LFO output, 7V
  to 0V peak-to-peak, effectively a constant voltage
  reference controlled by `Vof`
  voltage reference controlled by `Vof`
* `Vform`: controls the waveshape of the LFO. Approximate
  ranges:
    * [0V, 2.8V) - smooth random
    * [2.8V, 3.4V) - stepped random
    * [3.4V, 4.2V) - sweep
    * [4.2V, 4.8V) - triangle
    * [4.8V, 5.4V) - square
    * [5.4V, 6.7V) - ramp down
    * [6.7V, 7.0V) - ramp up

The easiest way to get control voltage for each of the
inputs is with a B10k potentiometer:

![Drawing of a potentiometer, pin one connected to 9V, pin
three to GND, pin 2 goes to CV In](./img/cv-pot.png)
