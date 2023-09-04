---
title: Zero Cross Detector
brief: This board features a common circuit found in application notes for the LM393 comparator. It detects zero crossings on AC signals.
---

# zcd393
This is a zero cross detector which produces a square wave whose polarity changes whenever the AC
signal fed to it crosses the zero voltage line. The schematic used in this circuit can be found
in application notes from  different manufacturers and on "Motorola's 1993 Linear Interface ICs".

Component values may be changed to work with different voltage levels. The values in this
iteration were chosen and tested for 12V AC signals. In theory, with the proper voltage divider,
this circuit should work with mains voltage, just be sure not to electrocute yourself.
I personally preferred to use a 120 to 12V transformer.
