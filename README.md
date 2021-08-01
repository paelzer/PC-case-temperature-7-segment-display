# PC case temperature 7 segment display

Not that it's really neccessary to have one... but I think it looks cool anyway :-)

** This description is not yet complete. Some more detailed pictures I still need to add... will be done soon. **

** This project allows you to show your PC case temperature on a 4 digit 7 segment display connected to an Arduino NANO **

</br>
<img src="https://i.imgur.com/EwXUg77.png">

It has been tested sucessfully with following setup:

* Windows 10 x64

* Arduino IDE 1.8.16

* Arduino NANO (other Arduino boards work as well with some modifications depending on the model)

## Required hardware components:

    7 segment display with 4 digits (common anode type)
    1x 8bit shift register 74HC595
    1x Resistor 3.3K Ohm
    8x Resistor 220 Ohm
    KTY81 110 temperature sensor
    Arduino NANO
      
## Pinout and schematic:

	74HC595 Pin	   Display Pin
	    Q0		       11		
	    Q1		       1
	    Q2		       2
	    Q3		       3
	    Q4		       4
	    Q5		       5
	    Q6		       7
	    Q7		       10
	
	74HC595 Pin	   Arduino NANO
	    MR			D12
	    SH_CP		D6
	    ST_CP		D7
	    DS			D8
	    
	Arduino NANO	   Display Pin
	    D2			12
	    D3			9
	    D4			8
	    D5			6
	    
	KTY81-110 Pin
	    1			5V
	    2			check in schematic below
	    
</br>
<img src="https://i.imgur.com/jWa8qOf.png" width="600">
<b>Click to enlarge:</b>

## Bring the display to life

* [Arduino IDE](https://www.arduino.cc/en/software) need to be installed

* Connect the Arduino via USB to your PC
> Since the Arduino is placed inside my PC case I have myself created a cable to connect it to one of the internal USB headers directly on the mainboard so I don't need to route the cable to a USB port outside of the case. The temperature sensor I have fixed with a cable tie somewhere in the middle of the case - pictures will follow.

* Flash the KTY81-110_7segm.ino file to the Arduino NANO

* If everything has been setup correctly the temperature in your PC case will show up on the display

## Check the temperature on the serial line (COM port)

* As soon as the Arduino is powered up it will continously send the calculated resistance value and the temperature accordingly over the serial line via the USB the Arduino is connected to. It can be read off by connecting to the COM port with e.g. the Arduinos serial monitor, putty or any other serial monitor you're familiar with.
      
* The COM port your Arduino is connected to can easily be found by checking your Windows device manager or by looking in the Arduino IDE.
  
</br>
