# Use the ESP-01 as a full-featured NodeMCU
The NodeMCU is a small, USB-powered Internet of Things development board, featuring an ESP-12 System on a Chip as the main central processing unit (which in turn consists of an [ESP8266 microcontroller](https://cdn-shop.adafruit.com/product-files/2471/0A-ESP8266__Datasheet__EN_v4.3.pdf) and 4MB of flash memory), plus an USB-to-serial converter and a voltage regulator.

The ESP-01 is the first generation of ESP System on a Chip boards, with more-or-less the same internals as the later ESP-12 (2MB of flash memory, versus 4MB of later versions), but with far less pins. The ESP-01 only has 8 pins, versus 22 pins for the ESP-12. The pinout of the ESP-01 is as follows (pins are numbered on the top side, from lower right as pin 1 and upper right as pin 2, et cetera): 

| ESP-01 pin number | Description / function | NodeMCU equavalent pin |
| :---------------- | :---------- | :----------------------|
| 1                 | GND         | GND                    |
| 2                 | UTXD (GPIO1) | TX                    |
| 3                 | GPIO2       | D4                     |
| 4                 | CH_PD       |                        |
| 5                 | GPIO0 (FLASH) | D3                   |
| 6                 | /RST        | RST                    |
| 7                 | URXD (GPIO3) | RX                    |
| 8                 | VCC         | 3V3                    |

While in normal operation, pins 1 (GND), 4 (CH_PD), 6 (/RST) and 8 (VCC) are tied up for basic chip control. When using the serial port, also pins 2 (UTXD) and 7 (URXD) are used. That only leaves pins 3 (GPIO2) and 5 (GPIO0) for I/O. CH_PD needs to be pulled to VCC, it will power down the entire module when pulled low; /RST may be connected to VCC for normal operations, but it can be left floating.

When programming the ESP-01, pin 5 (GPIO0) needs to be pulled to ground when booting or powering up in order to enter flash mode.

## What use cases can be implemented with only two pins?
Only two I/O pins are available to read sensors or control actuators. But it doesn't mean the ESP-01 module is crippled though. Full internet contact is possible using the built-in wifi and there is as much RAM and flash memory as any ordinary NodeMCU. A short list of possible uses:
* Flash the NodeMCU firmware in order to be able to use Lua and the high level sensor/actuator modules for OneWire, SNTP, HTTP, RTCtime, I2C, WS2812B, and more
* Retreive info from the internet: sync and display realtime clock data, call webhooks, store and get cloud data 
* Controlling a string of WS2812B leds, connected on D4/GPIO2 (pin 3), for use in led matrix displays, ornaments, indicators



