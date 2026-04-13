# BME680 STM32 Device Driver

A driver for the BME680 sensor, written in C23. Depends on the STM32CubeF4 HAL.

## Usage

- Declare BME680_HandleTypeDef and initialize to 0.
- Initialize I2C_HandleTypeDef and set hi2c field of BME680 handle to the initialized I2C handle.
- Initialize device with BME680_Init
- Get data from device with BME680_Poll. Output data can be accessed through the BME680 handle's output field.
- gas_resistance values are initially unreliable until after a 24 hour burn in (continuous usage).

## Output

The BME680_OutputTypeDef contains these fields as integers, with these units:

- humidity: % relative humidity
- temperature: degrees centigrade
- pressure: pascals
- gas_resistance: ohms
- time_stamp: this field is not set by BME680_Poll, may be set and used by user