# NTC Thermistor Library (fork with optional ADC_ref_v, bPULL_UP_schematics)

For Arduino ant STM32 boards.

The Library implements a set of methods for working with a NTC thermistor.
Provides a temperature reading in Celsius, Fahrenheit and Kelvin.

## Installation

1. [Download](https://github.com/pavel-b-kr12/NTC_Thermistor/archive/master.zip)
3. Paste to Library folder, replacing original lib, if it is here
4. Use new constructor method as described below
## Circuit Diagram

Connect to the analog side of an Arduino Uno. Run 5V through the thermistor, then a pull-down resistor (R0), and into ground. To measure the temperature pull a line off the junction of the thermistor and the resistor, and into an analog pin (A1 here).

![Diagram](Diagram.png)
![Diagram](Diagram_pull_dn.png)

## Methods

```cpp
    // Instantiation:
    /**
        pin - an analog port number to be attached to the thermistor.
        R0 - reference resistance.
        Rn - nominal resistance.
        Tn - nominal temperature in Celsius.
        B - b-value of a thermistor.
		optional:
		ADC_resolution = 1023 default
		ADC_ref_v = 5 default
		bPULL_UP_schematics = true for schematics as on image, or false for thermistor with pulldown resistor
    */
    NTC_Thermistor thermistor(pin, R0, Rn, Tn, B, ADC_resolution, ADC_ref_v, bPULL_UP_schematics);

    // Read a temperature in Celsius.
    double celsius = thermistor.readCelsius();
    // Read a temperature in Kelvin.
    double Kelvin = thermistor.readKelvin();
    // Read a temperature in Fahrenheit.
    double fahrenheit = thermistor.readFahrenheit();
    // For older devices.
    double farenheit = thermistor.readFarenheit();
```

### Examples

[Serial Reading](/examples/SerialReading/SerialReading.ino)

[Average Measurement](/examples/AverageMeasurement/AverageMeasurement.ino)

[Smooth Measurement](/examples/SmoothMeasurement/SmoothMeasurement.ino)

[STM32...](/examples/STM32/STM32.ino)

[All examples...](/examples)

Created by Yurii Salimov.
