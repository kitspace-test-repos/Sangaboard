# Ardunio code for the sangaboard

This is the arduino code for all supported versions of the Sangaboard. It is also sometimes refered to as our "arduino firmware" or the "Sangaboard firmware".

## Hardware

This code can be used with:
* A Sangaboard v0.3 either using the Arduino Leonardo bootloader or the Sangaboard custom bootloader.
* An Arduino nano ATmega328p plugged into a Sangaboard v0.2
* A [homemade motor controller using an Arduino Nano](https://build.openflexure.org/openflexure-microscope/v6.1.2/docs/#/6_motor_controllers?id=simple-controller-using-arduino-nano)

## Install with Arduino IDE

### Requirements
Requires version 1.6.2 or higher of the [Ardunio IDE](https://www.arduino.cc/en/Main/Software).  
(Note the Ubuntu/Debian package version 2:1.0.5, is version 1.0.5 and hence will not work!)

### Install libraries
**This is not needed for a normal Sangaboard, you can probably skip this step**

Three Adafruit libraries are required for light sensor support. These libraries can be installed in the Aruino library directory (normally `~/Arduino/libraries` on Linux or `My Documents\Arduino\libraries` on Windows) and can be found on the [adafruit github](https://github.com/adafruit).
If you have git your can run these commands to install it

	cd ~/Arduino/libraries
	git clone https://github.com/adafruit/Adafruit_TSL2591_Library.git
	git clone https://github.com/adafruit/Adafruit_Sensor.git
	git clone https://github.com/adafruit/Adafruit_ADS1X15.git

## Install with Arduino CLI

First, [install the Arduino CLI](https://arduino.github.io/arduino-cli/installation/)

### Install libraries
**This is not needed for a normal Sangaboard, you can probably skip this step**

`arduino-cli lib install "Adafruit TSL2591 Library" "Adafruit Unified Sensor" "Adafruit ADS1X15"`

### Install AVR core
`arduino-cli core update-index && arduino-cli core install arduino:avr`

### Attach the firmware to a board

**Find your boards COM port**

`arduino-cli board list`

`arduino-cli board attach {YOUR COM PORT} .`

For example:
`arduino-cli board attach /dev/ttyACM0 .`
or
`arduino-cli board attach COM1 .`


### Compile and upload

`arduino-cli compile --upload`


