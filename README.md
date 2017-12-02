# Use the ESP-01 as a full-featured NodeMCU
The NodeMCU is a small, USB-powered Internet of Things development board, featuring an ESP-12 System on a Chip as the main central processing unit (which in turn consists of an [ESP8266 microcontroller](https://cdn-shop.adafruit.com/product-files/2471/0A-ESP8266__Datasheet__EN_v4.3.pdf) and 4MB of flash memory), plus an USB-to-serial converter and a voltage regulator.

The ESP-01 is the first generation of ESP System on a Chip boards, with the same internals as the later ESP-12, but with far less pins. The ESP-01 only has 8 pins, versus 22 pins for the ESP-12. The pinout of the ESP-01 is as follows (pins are numbered on the top side, from lower right as pin 1 and upper right as pin 2, et cetera): 

| ESP-01 pin number | Description | NodeMCU equavalent pin |
| :---------------- | :---------- | :----------------------|
| 1                 | GND         |                        |
| 2                 | UTXD (GPIO1) |                        |
| 3                 | GPIO2       |                        |
| 4                 | CH_PD       |                        |
| 5                 | GPIO0       |                        |
| 6                 | /RST        |                        |
| 7                 | URXD (GPIO3) |                        |
| 8                 | VCC         |                        |

While in normal operation, pins 1 (GND), 4 (CH_PD), 6 (/RST) and 8 (VCC) are tied up for basic chip control. When using the serial port, also pins 2 (UTXD) and 7 (URXD) are used. That only leaves pins 3 (GPIO2) and 5 (GPIO0) for I/O. CH_PD needs to be pulled to VCC to enable wifi functions; /RST may be connected to VCC for normal operation.

When programming the ESP-01, pin 5 (GPIO0) needs to be pulled to ground when booting or powering up in order to enter flash mode.


