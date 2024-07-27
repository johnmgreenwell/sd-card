
** SD - a slightly more friendly wrapper for sdfatlib **

This library aims to expose a subset of SD card functionality in the
form of a higher level "wrapper" object.

License: GNU General Public License V3
         (Because sdfatlib is licensed with this.)

(C) Copyright 2010 SparkFun Electronics

Now better than ever with optimization, multiple file support, directory handling, etc - ladyada!

Modified by John Greenwell to adapt driver for custom HAL support, 2024.

For this modified version, the following hardware abstraction layer (HAL) requirements must be satisfied:

* A header file `hal.h` providing access to HAL namespace classes and methods.
* A `GPIO` class within the `HAL` namespace with the following methods:
  - Set pin mode: `pinMode(uint8_t mode)`
  - Write logic level to pin: `digitalWrite(uint8_t val)`
* A `SPI` class within the `HAL` namespace with the following methods:
  - Perform SPI data transfer: `transfer(uint8_t data)`
* A millis() function in the HAL namespace that returns an accurate milliseconds counter to be used for timing.

Some further requirements may also be found. Typically, these will mirror the Arduino framework and should be added to `hal.h`.
* For example, this driver depends on the Arduino framework "Stream" class, and an equivalent will need to be provided, in the HAL or otherwise.

