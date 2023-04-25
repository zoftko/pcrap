---
title: 8th Order Bandpass Filter
tags: ["RF", "Filter"] 
---
# Introduction
This is a board designed to function as the layout for 8th order bandpass filters. It was designed with
VHF in mind (original design had a center frequency of 150 MHz).

It has been designed as a two layer board to reduce costs. Most components are 0603, some of the series
inductors are relatively big at VHF frequencies and therefore have been used in 0805 and 1008 sizes. A rare capacitor
value was only available in 0805 packaging at the time so that was used as well.

# Design
## Transmission Lines
The traces are relatively short, and at the target frequencies may not be considered as transmission lines, regardless
the traces were modeled as coplanar wave guides with a ground plane below it. 

Trace width is approximately 0.66mm, spacing between the planar planes is 0.13mm and spacing between
the trace and ground plane below it should be 1.6mm, according to Kicad this gives a Z0 close to 50 Ohms.

## Filter Synthesis
The original design was generated following Steve's Winder advice on Chapter 6 of his book
"Analog and Digital Filter Design". Below are the details:

* Center Frequency: 150 MHz
* Bandwidth: 20 MHz
* Type: Butterworth
* Rs, RL: 50 Ohms

| Component | Value | Package (in) |
|:---------:|:-----:|:------------:|
|    C1     | 160pF |     0805     |
|    L1     | 6.8nH |     0603     |
|    L2     |  1uH  |     1008     |
|    C2     |  1pF  |     0603     |
|    C3     | 390pF |     0603     |
|    L3     | 2.7nH |     0603     |
|    L4     | 390nH |     0805     |
|    C4     | 2.7pF |     0603     |
