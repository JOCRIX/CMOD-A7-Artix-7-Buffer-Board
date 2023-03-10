# **Buffer Board for the CMOD A7 Artix 7 family of FPGA development boards**
![](https://github.com/JOCRIX/CMOD-A7-Artix-7-Buffer-Board/blob/main/Images/CMOD-Isolator2.svg)

## **Purpose of the project**
The development boards for these FPGA's are costly and, sadly, a little fumbling around
could could easily claim it's life, so, the purpose of this project is to create a board that can buffer the I/O pins
on the Digilent CMOD A7 FPGA board. (Mfr: 410-328-35, Mouser.com nr:424-410-328-35).

All design files are for KiCad. Feel free to export the GERBERS and do w/e with it.

## **How it works**
The board uses TXB0108 bidirectional and auto-direction sensing buffers to buffer all the I/O pins. The buffers
do not require any signal to set them as inputs or outputs, this is handled automatically on the fly. Each pin
has a maximum I/O current of 50mA and a package total of 100mA per buffer IC. The purpose of the board is 
that the drivers will fail before the FPGA does, that is OK. The FPGA is connected to the buffers through
330 ohm resistors, so, if the buffers fail in a spectacular way the FPGA output current is limited to stay
within specification of the Artix 7 35T FPGA.

The rise and fall times of the output of the buffer board has been tested and both rise and fall times are 4 < t < 5 [nS].

The two ADC input pins AIN/NP15, AIN/NP16 are protected against overvoltage conditions with diodes.


## **Requirements / BOM**

1x CMOD A7 FPGA Board - https://www.mouser.dk/ProductDetail/Digilent/410-328-35?qs=iHX4uCgIbgPRh1v3D3f51A%3D%3D
<br>
6x TXB0108 [TSSOP20]
<br>
11x YC324, or similar, 330 ohm resistor array.
<br>
2x 24 Pin Female headers with 2.54mm pitch
<br>
2x 24 Pin Female/Male header with 2.54mm pitch
<br>
1x LD117S533TR [SOT223]
<br>
7x 100nF >6.3V [0805]
<br>
1x 0603 LED (Doesn't really matter but it looks cool!)
<br>
1x 560R [0805]
<br>
1x 10uF [0805]
<br>
4x BAT54 [SOD-123]

## Hope you like Warhammer..

![](https://github.com/JOCRIX/CMOD-A7-Artix-7-Buffer-Board/blob/main/Images/CMOD-Isolator.svg)

### Notes for users
V1 of this board has a fault so **PIO26 [FPGA PIN: R3] is not connected**. This is to be fixed in a future revision.
The problem can be fixed with a jumper wire for now. (Or just edit the .sch but w/e :)).

The green trace shows the connection that should be made for R3 to work. Easily fixed in either case..
![](https://github.com/JOCRIX/CMOD-A7-Artix-7-Buffer-Board/blob/main/Images/CMOD-Isolator-error.svg)
