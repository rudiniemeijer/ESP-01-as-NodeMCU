# Use the ESP-01 as a full-featured NodeMCU
The NodeMCU is a small, USB-powered Internet of Things development board, featuring an ESP-12 System on a Chip as the main central processing unit (which in turn consists of an [ESP8266 microcontroller](https://cdn-shop.adafruit.com/product-files/2471/0A-ESP8266__Datasheet__EN_v4.3.pdf) and 4MB of flash memory), plus an USB-to-serial converter and a voltage regulator.

The ESP-01 is the first generation of ESP System on a Chip boards, with the same internals as the later ESP-12, but with far less pins. The ESP-01 only has 8 pins, versus 22 pins for the ESP-12. The pinout of the ESP-01 is as follows (pins are numbered on the top side, from lower right as pin 1 and upper right as pin 2, et cetera): 

| ESP-01 pin number | Description | NodeMCU equavalent pin |
| :---------------- | :---------- | :----------------------|
| 1                 | GND         |                        |
| 2                 | IO1 TXD0 CS1 |                        |
| 3                 | IO2 TXD1    |                        |
| 4                 | EN CHPD     |                        |
| 5                 | CS2 IO0     |                        |
| 6                 | /RST        |                        |
| 7                 | RXD0        |                        |
| 8                 | VCC         |                        |
