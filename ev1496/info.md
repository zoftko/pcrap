---
title: MC1496 Evaluation Board
tags: ["RF", "Mixer", "Modulator"] 
---
# Introduction
The MC1496 is a balanced modulator/demodulator, internally realized as a Gilbert Cell. This evaluation board
is meant to be used in lab environments to test the capabilities of this IC. It has female SMA connectors
and care has been taken to provide an RF friendly PCB layout.

The datasheet from On Semi and document AN531 (from On Semi too) have been the primary resources used for designing
the evaluation board.

# Design
## DC Biasing
This board has been designed to be used with a single 15V supply. These are the expected DC values for each pin:

| Pin (s) | Function | Voltage (V) |
|:-------:|:--------:|:-----------:|
|    5    |   Bias   |    1.25     |
|  1, 4   |  Signal  |      5      |
|  8, 10  | Carrier  |     8.2     |
|  6, 12  |  Output  |    11.1     |

### Power Dissipation
Current on pin 5 (I5) should be 1mA, following eq. 19 (AN531) the total power dissipation should be:
```
PD = 2 * I5(11.1) + I5(1.25)
PD = 0.02345W
PD = 23.45mW
```