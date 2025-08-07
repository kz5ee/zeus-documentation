# USB Type-C and USB Power Delivery ( https://www.usb.org/usbc )
## Physical Layer Wiki Entry ( https://en.wikipedia.org/wiki/USB-C )
```
USB‑C, or USB Type‑C, is a 24-pin reversible connector (not a protocol) that supersedes all previous USB connectors, designated legacy in 2014, and also supersedes Mini DisplayPort and Lightning[3] connectors. USB‑C can carry data, e.g. audio or video, power, or both, to connect to displays, external drives, mobile phones, keyboards, trackpads, mice, and many more devices; sometimes indirectly via hubs or docking stations. It is used not only by USB technology, but also by other data transfer protocols, including Thunderbolt, PCIe, HDMI, DisplayPort, and others. It is extensible to support future protocols.
```
```
The designation C refers only to the connector's physical configuration, or form factor, not to be confused with the connector's specific capabilities and performance, such as Thunderbolt 3, DisplayPort 2.0, USB 3.2 Gen 2×2. While USB‑C is the single modern connector for all USB protocols, there are valid uses of the connector that do not involve any USB protocol. Based on the protocols supported by all, host, intermediate devices (hubs), and peripheral devices, a USB‑C connection normally provides much higher data rates, and often more electrical power, than anything using the superseded connectors.

A device with a Type‑C connector does not necessarily implement any USB transfer protocol, USB Power Delivery, or any of the Alternate Modes: the Type‑C connector is common to several technologies while mandating only a few of them.[7] 
```
```
USB 3.2, released in September 2017, fully replaced the USB 3.1 (and therefore also USB 3.0) specifications. It preserves the former USB 3.1 SuperSpeed and SuperSpeed+ data transfer modes and introduces two additional data transfer modes by newly applying two-lane operations, with signalling rates of 10 Gbit/s (SuperSpeed USB 10 Gbps; raw data rate: 1.212 GB/s) and 20 Gbit/s (SuperSpeed USB 20 Gbps; raw data rate: 2.422 GB/s). They are only applicable with Full-Featured USB‑C cables and connectors and hosts, hubs, and peripheral devices that use them.

USB4, released in 2019, is the first USB transfer protocol standard that is applicable exclusively via USB‑C. 
```
* The specification for USB Type-C Connection Rev 2.1b ( https://www.usb.org/document-library/usb-type-c-connectors-and-cable-assemblies-compliance-document ) explains that there are versions for full featured and power only plug applications and a locking plug with one or two screws for additional secuire attachment.

## Power Delivery Wiki Entry ( https://en.wikipedia.org/wiki/USB_hardware#USB_Power_Delivery )
* Specification defined at ( https://www.usb.org/usb-charger-pd )
* Power negotiable from low power headset to full systems up to 240W
```
Power,      Minimum USB‑C cable,    Voltage,    Current
≤ 15 W 	    Any                     5 V         ≤ 3.0 A
≤ 27 W 	    Any                     9 V         ≤ 3.0 A
≤ 45 W 	    Any                     15 V        ≤ 3.0 A
≤ 60 W 	    Any                     20 V        ≤ 3.0 A
≤ 100 W 	5 A, or 100 W[B] 	    20 V        ≤ 5.0 A
≤ 140 W[C] 	240 W 	                28 V        ≤ 5.0 A
≤ 180 W[C] 	240 W 	                36 V        ≤ 5.0 A
≤ 240 W[C] 	240 W 	                48 V        ≤ 5.0 A
```
* Bidirectional power transfer ( Roles can also be negotiated swapping host and device )
