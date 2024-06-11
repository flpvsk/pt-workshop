### PTT

PT2399 adapter board for prototyping pedals.

For minimum operation, please connect these pins:

* Pin 1: +9V
* Pin 2: GND
* Pin 3: +4.5V
* Pin 9: Audio In
* Pin 10: Audio Out
* Ic In: this pin controls delay time, see below for details

#### Control delay time via a pot

This pin on the adapter board is hooked up directly to the
control pin on the PT2399. The easiest way to vary delay
time is to connect this pin to ground via a potentiometer.


The minimum necessary resistance to GND on PT2399 startup is
2k. Otherwise the chip latches up. [See details in this Electrosmash article.](https://www.electrosmash.com/pt2399-analysis)

#### Control delay time via voltage

There's an onboard voltage-to-current converter. To use it,
send control voltage via `Vtime` pin and get the
control current via the `Ic Out` pin. Connect `Ic Out` to
`Ic In` to control delay time using `Vtime`.




