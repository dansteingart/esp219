## esp219
A basic (fast) esp8266 + INA219 voltage, current and power meareument device using reference
[adafruit INA219](https://learn.adafruit.com/adafruit-ina219-current-sensor-breakout/overview) implementation.


(this code should work with and *duino I'm currently mucking with a ESP8266 D1 type)

## How To Use

1. Connect to serial @ baud 115200
2. data fires in fast ~(200 Hz) in CSV format
    `millis (ms), bus voltage (V), current (mA), power (mW), shunt voltage (mV)`

There may be a little floaty float on the current near 0 mA, and if the bus voltage is float it will read `1.05 V`.

## Wiring
```
INA219  |  ESP8266
VCC        5V
GND        GND
SDA        D1
SCL        D2
```

For the load/battery,
```
INA219 Vin+ -> Power supply Positive
INA219 Vin- -> Battery Positive
INA219 GND -> Battery GND (will also be power supply GND)
```