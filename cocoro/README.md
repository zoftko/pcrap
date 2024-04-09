---
title: Heart shaped RGB LED Array
brief: This board includes a heart shaped RGB LED array and the components to control said array through a simple user interface.
---

# cocoro
The idea behind this board is to function as a night light. It uses an STM8s MCU to control
different characteristics such as color or brightness. The user interface consists of a rotary
encoder and a small I2C OLED display, based on the SD1306 controller.

### Warnings
The P Channel Mosfets (FDN340P) placement to turn on the LEDs (high side switch) is wrong. Pin
assignment is wrong. For example, the PCB layout marks the source as being the gate. The part needs
to be rotated 90° to the left for pins to be properly placed.
