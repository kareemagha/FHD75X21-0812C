# FHD75X21-0812C
VFD driver for FHD75X21-0812C 

## Preview
Backside
<img width="929" height="351" alt="image" src="https://github.com/user-attachments/assets/efda9d1a-19c1-4c3d-a3ee-5ba2f6569489" />

Frontside
<img width="933" height="351" alt="image" src="https://github.com/user-attachments/assets/23009084-96d2-40e0-83e3-4a3026f128e8" />

## Theory

The PT6315 IC is the brains of this driver. It is nothing more than some RAM and some shift registers. This IC uses SPI for communication, with the strobe, STB, pin acting as chip select (slave select). However, I would not reccomend using an SPI library to communicate with this IC, since the chip select functionality is non-standard.

The board contains an inverting boost converter. It generates -24V from a 5V input. This voltage is used for the filaments, grids and segments. Note that this voltage is just a reference/bias - nothing is driven from the -24V (put simply little current is drawn from the -24V source, a motor driver is used to pull current from the 5V input and a biasing circuit sets the voltage to -24V). A Schmitt trigger oscillator is used to simulate AC for the filament.
