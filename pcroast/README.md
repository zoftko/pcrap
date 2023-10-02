---
title: Reflow Oven Controller
brief: This board uses a Pico W and integrates several components required to control a simple electrical oven and turn it into a reflow oven for SMD components.
---

# pcroast
This is an all in one PCB to control retrofitted electrical ovens. The only
component that is not part of the PCB is the SSR used to turn on and off the oven. Its main
features are:

* Simple UI with two buttons and 160x128 1.8' display.
* Integrated MAX6675 for temperature readings.
* Zero Cross Detector for counting AC cycles.

## Modules
The schematic splits components into logical modules, some of them, like user buttons or the LCD
header are self explanatory. This section explains modules which are more nuanced.

### Power input
The power input consists of a varistor for voltage spike supression and a PI filter to reduce
noise. An optional LED to indicate the power is ON can be soldered. The module ends with a
PNP diode used to isolate VSYS from VBUS. This makes it possible to connect the Pico W to a USB
port while the board is powered on.

When no USB connection is provided, the Pico W is powered from the DC barrel jack on the board,
when USB power is supplied, VBUS turns off the PNP diode and the Pico W obtains its power from
the USB port.

### Zero Cross Detector (ZCD)
This same schematic can be found as a separate board in this project (ZCD393). It provides a square
wave which makes it easy for the MCU to count AC cycles. It depends on a suitable AC signal being
provided on its set of screw terminals. The voltage can be further decreased by the voltage
divider on board. It should be kept below 1.8V (VCC - 1.5).

### GPIO Outputs
Most GPIO outputs are buffered by logic level NPN MOSFETs. This reduces current consumption when
driving parallel outputs and prevents current consumption to exceed safe limits.

## Testing
A previous revision of this board was fabricated and tested. The only issues found which are
corrected on this version were:

* Negative thermocouple probe was not grounded.
* ZCD used the 5V rail as its supply, instead of 3.3V. This meant its output was a 5V square wave.
  5V are not officially supported by RP2040 GPIO pins, however it does not blow it apart. Just
  to be safe it was changed to the 3.3V rail for safety.

Other than that the design was satisfactory and proved functional.
