:repository-owner: arduino-libraries
:repository-name: SD

= {repository-name} Library for Arduino =

image:https://github.com/{repository-owner}/{repository-name}/actions/workflows/check-arduino.yml/badge.svg["Check Arduino status", link="https://github.com/{repository-owner}/{repository-name}/actions/workflows/check-arduino.yml"]
image:https://github.com/{repository-owner}/{repository-name}/actions/workflows/compile-examples.yml/badge.svg["Compile Examples status", link="https://github.com/{repository-owner}/{repository-name}/actions/workflows/compile-examples.yml"]
image:https://github.com/{repository-owner}/{repository-name}/actions/workflows/spell-check.yml/badge.svg["Spell Check status", link="https://github.com/{repository-owner}/{repository-name}/actions/workflows/spell-check.yml"]

The SD library allows for reading from and writing to SD cards.

For more information about this library please visit us at
http://www.arduino.cc/en/Reference/{repository-name}

Modified by John Greenwell to adapt driver for custom HAL support, 2024.

## Usage

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
