# LoRaWAN Summary
LoRa is a low-power wide-area network protocol for the lower physical level. LoRaWAN is a protocol build on LoRa to define the upper levels of the networks.

Topology:
![topology picture](https://www.thethingsnetwork.org/docs/lorawan/LoRaWAN-Overview.png)
 It is a cloud based MAC layer but acts a network layer protocol to manage the communication between the gateways and the end nodes as a routing protocol.

**[List of countries with LoRa available](https://www.thethingsnetwork.org/docs/lorawan/frequencies-by-country.html)**
**[Frequency Map](http://iotfactory.eu/lorawan-world-frequency-map-lora-sigfox-nbiot-telecom-operators-per-country/)**

## End Nodes

* Microcontrollers 
* Sensors
* Data gathering devices

Devices must first be [registered](https://www.thethingsnetwork.org/docs/devices/registration.html) to an [Application](https://www.thethingsnetwork.org/docs/applications/add.html)

Payload should be as small as possible. No JSON or plain ASCII text but binary data.

Can only send small packets every couple of minutes. So send data only upon status change or within a sufficient time interval.

Data Range recommended in SF7BW125.

Available devices that support LoRaWAN:
* [LoPy](https://www.thethingsnetwork.org/docs/devices/lopy/)
* [FiPy](https://docs.pycom.io/datasheets/development/fipy/)
* ESP32
* [The Things Uno](https://www.thethingsnetwork.org/docs/devices/uno/)
* [The Things Node](https://www.thethingsnetwork.org/docs/devices/node/)
* More in the [Hardware section](https://www.thethingsnetwork.org/docs/devices/)

Libaries/Implementations available:
* [ Micropython: LoRaWAN with ABP](https://docs.pycom.io/tutorials/lora/lorawan-abp/)
    * For LoPy, FiPy
* [Arduino SDK](https://github.com/thethingsnetwork/arduino-device-lib)
    * For the rest
* [ESP32 running MicroPython sends data over LoRaWAN](https://lemariva.com/blog/2020/02/tutorial-micropython-esp32-sends-data-over-lorawan)

Links:
[Node Resources](https://www.thethingsnetwork.org/labs/stories/node)

## Concentrator/Gateway:
Packet forwaring devices

Must be [registered](https://www.thethingsnetwork.org/labs/stories/node) with [The Things Network](https://www.thethingsnetwork.org/docs/network/)

Available devices that support LoRaWAN and can serve as a gateway:
* [LoPy](https://www.thethingsnetwork.org/docs/devices/lopy/) (Custom, must be programmed)
* [FiPy](https://docs.pycom.io/datasheets/development/fipy/) (Custom, must be programmed)
* ESP32 (Custom, must be programmed)
* [The Things Gateway](https://www.thethingsnetwork.org/docs/gateways/gateway/)
* More in the [hardware section](https://www.thethingsnetwork.org/docs/gateways/)

Libaries/Implementations available:
* [Arduino SDK](https://github.com/thethingsnetwork/arduino-device-lib)
* [ Micropython: LoRaWAN Nano-Gateway](https://docs.pycom.io/tutorials/lora/lorawan-abp/) and [Building a LoRaWAN Nano Gateway to The Things Network](https://core-electronics.com.au/tutorials/building-a-lorawan-nano-gateway-to-the-things-network.html)
    * For LoPy, FiPy

Links:
[Build a gateway in a week-end with a Raspberry Pi and an iC880a concentrator board](https://github.com/ttn-zh/ic880a-gateway/wiki)
[Gateway Resources](https://www.thethingsnetwork.org/labs/stories/gateway)

## Network Server
[Account Server](https://www.thethingsnetwork.org/docs/network/account/)
* Manages the applications, gateways, users and rights for The Things Network.

[Discovery Server](https://www.thethingsnetwork.org/docs/network/discovery/)
* This is where routers, brokers and handlers announce themselves and where you can look them up.

## Application Server

1. [Add an Application](https://www.thethingsnetwork.org/docs/applications/add.html)
2. Build an application:
   Different ways to build an application and connect it to The Things Network:
    * [API](https://www.thethingsnetwork.org/docs/applications/apis.html)
        * Supports MQTT
    * [SDKs](https://www.thethingsnetwork.org/docs/applications/sdks.html)
    * [Integrations](https://www.thethingsnetwork.org/docs/applications/integrations.html)
        * E.g. AWS IoT



###### tags: `p3`