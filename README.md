# ethernet-wing
*Hardware design files for the Particle Ethernet Wing*

The Ethernet FeatherWing is the fastest way to add wired connectivity to your Argon, Boron, or Xenon and turns any Particle Mesh developer kit into an Ethernet gateway. Based on the WIZnet W5500 chip, this side-by-side FeatherWing maintains great RF performance even while adding Ethernet connectivity to any Particle Mesh device.

The form-factor is based around the Adafruit FeatherWing Tripler. The two side connectors allow you to plug in one Particle Mesh device along with a Feather accessory.

- 10BaseT/100BaseTX Ethernet 
- Support Auto Negotiation (Full and half duplex, for both 10BaseT and 100BaseTX)

## Pin Map

|Mesh Pin|Ethernet FeatherWing Pin   |
|:-------|:--------------------------|
|MISO    | SPI MISO                  |
|MOSI    | SPI MOSI                  |
|SCK     | SPI SCK                   |
|D3      | nRESET<sup>[1]</sup>      |
|D4      | nINTERRUPT<sup>[1]</sup>  |
|D5      | nCHIP SELECT<sup>[1]</sup>|

**Notes:**

<sup>[1]</sup> These pins are connected via jumper pads on the bottom. You can cut these jumper traces and rewire them to a different pin on the Mesh device if the need arises. However the Device OS does not allow use of other pins (as of 0.8.0-rc.27).

The Ethernet driver for this wing is baked into the Mesh Device OS. When you set up a new Particle Mesh device that is plugged into an Ethernet FeatherWing, simply select the _USE WITH ETHERNET?_ option on your Particle mobile app and it should recognize and talk over Ethernet automagically. It's that simple.

## PoE (Power over Ethernet)

The PoE (Power over Ethernet) adapter for the Ethernet FeatherWing plugs into the Ethernet side of the FeatherWing. 

It uses the Silvertel Ag9905M and can supply 1800 mA to your device and any Feather accessories. It is a Class 0 IEEE 802.3af device.

| Parameter | Minimum | Typical | Maximum | Units |
| --- | --- | --- | --- | --- |
| Input Supply Voltage | 36 | 48 | 57 | Volts |
| Operating Temperature<sup>1</sup> | -40 | 25 | 70 | &deg;C |
| Output Voltage | | 5 | | V |
| Output Current | | | 1800 | mA |

<sup>1</sup>Operating temperature of the Ag9905M module only. The operating temperature range of the Xenon is smaller, -20 to +60&deg;C.

Note that because the Ethernet FeatherWing with PoE supplies 5V to the device by the VUSB pin, you should not power it by both PoE and the USB serial port at the same time. 
