![GitHub release (latest by date)](https://img.shields.io/github/v/release/maestry/eliokit-arduino)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
![GitHub all releases](https://img.shields.io/github/downloads/maestry/eliokit-arduino/total)


# Arduino library for ElioKit Board

The Eliokit library is a collection of functions and classes that simplify the development of Arduino projects based on ElioKit Dev Board. It includes features for serial communication, digital and analog pin management, as well as sensor and actuator management.

## Installation

To install the Eliokit library, follow the installation guide available at the following link: https://elioiot.com/docs/ELIO-Arduino-IDE.pdf

## Documentation

For more information on using the Eliokit library, consult the general documentation available at the following link: https://elioiot.com/guide/

## Example Code

Here is an example code that shows how to use the Eliokit library to turn on and off the vibration motor:

```js
#include "eliokit.h"

// Vibration Motor address
#define XL9335_ADD						0x20

void setup() {
  Serial.begin(115200);
  i2cPeripheralInitCustomSpeed(I2C_0_MASTER_NUM, I2C_0_MASTER_FREQ_HZ);
  i2cPeripheralInitCustomSpeed(I2C_1_MASTER_NUM, I2C_1_MASTER_FREQ_HZ);
  gpioExpanderInit();
  spiPeripheralInit();
}

void loop() {
  // put your main code here, to run repeatedly:
  gpioExpanderSetVibrationMotorOn();
  delay(1000);
  gpioExpanderSetVibrationMotorOff();
  delay(5000);
}

```


