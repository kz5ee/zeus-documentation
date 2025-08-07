# LoRa "Long Range" Radio Communication ( https://www.semtech.com/lora )

# This only scratches the surface but needs to be discussed BEFORE diving deeper into the details

## Wiki Entry ( https://en.wikipedia.org/wiki/LoRa )
### Physical Layer ( LoRa )
```
LoRa (from "long range", sometimes abbreviated as "LR") is a physical proprietary radio communication technique.[2] It is based on spread spectrum modulation techniques derived from chirp spread spectrum (CSS) technology.[3] It was developed by Cycleo, a company of Grenoble, France, and patented in 2014.[4] In March 2012, Cycleo was acquired by the US company Semtech.[5] 
```
* 915 MHz license-free sub-gigahertz band 'US915 (902–928 MHz) in North America'
* LoRa provides longer range at the cost of lower data rates compared to other wireless networks like ZigBee and BlueTooth
```
According to the LoRa Development Portal, the range provided by LoRa can be up to 3 miles (4.8 km) in urban areas, and up to 10 miles (16 km) or more in rural areas (line of sight).[17]
```
### Protocol Layer ( LoRaWAN )
```
LoRaWAN (long range wide area network) defines the communication protocol and system architecture. LoRaWAN is an official standard of the International Telecommunication Union (ITU), ITU-T Y.4480.[6] The continued development of the LoRaWAN protocol is managed by the open, non-profit LoRa Alliance, of which Semtech is a founding member. 
```
# "By your powers combined, I am CAPTAIN PLANET!"
```
Together, LoRa and LoRaWAN define a low-power, wide-area (LPWA) networking protocol designed to wirelessly connect battery operated devices to the Internet in regional, national or global networks, and targets key Internet of things (IoT) requirements, such as bi-directional communication, end-to-end security, mobility and localization services. The low power, low bit rate, and IoT use distinguish this type of network from a wireless WAN that is designed to connect users or businesses, and carry more data, using more power. The LoRaWAN data rate ranges from 0.3 kbit/s to 50 kbit/s per channel.[7]
```
## Mode of operation ( https://www.thethingsnetwork.org/docs/lorawan/classes/ )
- Class A - Device sends data when needed and has two predefined listening windows of which  the gateway may use only one... Hope it responds in time!!!
    * Lowest power consumption at the cost of the highest downlink latency since the device MUST transmit in order for the server to be able to send it additional data
- Class B - Class A plus "ping slots" at regular intervals, i.e. additional listening windows based on gateway beacons
    * Gateway beacons add a time reference for the end devices
    * Devices are configured with "ping slots" between beacons where they open an additional listening window
    * More power used due to the additional receive windows for the beacon and "ping slot" receive windows
- Class C - Class A but the seconds receive windows is always active unless an uplink or the first receive window is active ( uplinks delayed if a downlink is active )
    * Lowest latency at the cost of the most power usage ( device is ALWAYS ON )
## Limitations ( https://www.thethingsnetwork.org/docs/lorawan/limitations/ )
#### Suitable use-cases for LoRaWAN: 
* Long range - multiple kilometers
* Low power - can last years on a battery
* Low cost - less than 20€ CAPEX per node, almost no OPEX
* Low bandwidth - between 250bit/s and 11kbit/s in Europe using LoRa modulation (depending on the spreading factor)
* Coverage everywhere - you are the network! Just install your own gateways
* Secure - 128bit end-to-end encrypted

#### Not Suitable for LoRaWAN: 
* Realtime data - you can only send small packets every couple of minutes
* Phone calls - you can do that with GPRS/3G/LTE
* Controlling lights in your house - check out ZigBee or BlueTooth
* Sending photos, watching Netflix - check out WiFi

#### Sending data from a Node to your Application (uplink) 
```
[ TTN ] We want you to create products that are as efficient as possible. This will get the most out of your battery, and doesn’t require you to buy many gateways. If you follow these recommendations, you’ll definitely build an amazing product!
```
* Payload should be as small as possible.
    - This means that you should not send JSON or plain (ASCII) text, but instead encode your data as binary data. ( i.e. Cayenne Low Power Payload format ).
* Interval between messages should be in the range of several minutes, so be smart with your data.
    - You could for example transmit a min|avg|max every 5 minutes, or you could only transmit when you sensor value changed more than a certain threshold or have it triggered by motion or another event.
* Data Rate should be as fast as possible to minimize your airtime.
    - SF7BW125 is usually a good place to start, as it consumes the least power and airtime.
    - If you need more range, you can slowly increase until you have enough.
    - You can also enable adaptive data rate (ADR), the network will then be able to automatically optimize your data rate.

#### Sending responses from your Application to your Node (downlink) 
```
[ TTN ] We want to be able to handle as many Nodes as possible per Gateway. But as full-duplex radios are not widely available yet, a Gateway is not able to receive transmissions from Nodes while it is transmitting. This means that if a gateway is transmitting 10% of the time, it’s not able to receive anything for that 10% of the time. This is even worse when you realize that a gateway can receive at 8 channels simultaneously. Except when it’s transmitting. So while an idle gateway can receive transmissions from 8 devices, those 8 devices are worthless when the gateway is transmitting.
```
* Full-Duplex operation on a private network may be possible depending on the hardware used
```
[ TTN ] We want to build a network that offers high reliability. If your device transmits, the gateway should receive it. In order to keep the gateway availability as high as we can, we ask you to follow these recommendations.
```
* Data Rate should be, just as with uplink, as efficient as possible. The downlink data rate is based on the uplink data rate, so if you send efficient uplinks, the network will respond with efficient downlinks.
* Downlink messages should be avoided if possible, and if you send downlink, keep the payload small.
* Confirmed Uplink is often not necessary. Try to make your application work without confirmations.

## Link Budget ( you have limited "Time-On-Air" )
* Governmental and LoRaWAN limits the amount of time a device can be transmitting to allow fair usage of the air waves ( typically 1% duty cycle ) ( even less if using a public network )

### NOTES:
- [ TTN ] The Things Nertwork
