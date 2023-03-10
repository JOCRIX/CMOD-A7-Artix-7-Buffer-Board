# **Buffer Board for the CMOD A7 Artix 7 family of FPGA development boards**

## ØØPurpose of the projectØØ
The development boards for these FPGA's, are costly and, sadly, a little fumbling around
could could claim it's life, so, the purpose of this project is to create a board that can buffer the I/O pins
on the Digilent CMOD A7 FPGA board. (Mfr: 410-328-35, Mouser.com nr:424-410-328-35).

## **How it works**
The board uses TXB0108 bidirectional and auto-direction sensing buffers to buffer all the I/O pins. Each pin
has a maximum I/O current og 50mA and a package total of 100mA per buffer IC. The purpose of the board is
that drivers will fail before the FPGA does, that is OK. The FPGA is connected to the buffers through
330 ohm resistors, so, if the buffers fail in a spectacular way the FPGA output current is limited to stay
within specification of the Artix 7 35T FPGA.

The rise and fall times of the output of the buffer board has been tested and both rise and fall times are < 5 nS.

The two ADC input pins AIN/NP15, AIN/NP16 are protected against overvoltage conditions with diodes.

## **Requirements / BOM**

1x CMOD A7 FPGA Board - https://www.mouser.dk/ProductDetail/Digilent/410-328-35?qs=iHX4uCgIbgPRh1v3D3f51A%3D%3D
6x TXB0108 [TSSOP20]
11x YC324, or similar, 330 ohm resistor array.
2x 24 Pin Female headers with 2.54mm pitch
2x 24 Pin Female/Male header with 2.54mm pitch
1x LD117S533TR [SOT223]
7x 100nF >6.3V [0805]
1x 0603 LED (Doesn't really matter but it looks cool!)
1x 560R [0805]
1x 10uF [0805]
4x BAT54 [SOD-123]

### Notes for users
Note: V1 of this board has a fault so **PIO26 [FPGA PIN: R3] is not connected**. This is to be fixed in a future revision.
