# Cellular Radio Communication

The scope of cellular technologies is vast, so for this application I started with a simple search of what is available for cellular modules as if I was building a device and then I research the associated technologies for understanding...
## Nordic Semiconductor ( https://www.nordicsemi.com/Products/Wireless/Low-power-cellular-IoT/What-is-cellular-IoT )
### LTE-M
```
Low power, mobility and low latency for your applications

LTE-M (also known as Cat-M1) is designed for low-power applications requiring medium throughput. It has a narrower bandwidth of 1.4 MHz compared to 20 MHz for regular LTE, giving a longer range, but less throughput. The throughput is 375 kbps uplink and 300 kbps downlink, providing approximately 100 kbps application throughput running IP. It is suitable for TCP/TLS end-to-end secure connections. Mobility is fully supported, using the same cell handover features as in regular LTE. It is currently possible to roam with LTE-M, meaning it is suitable for applications that will operate across multiple regions. The latency is in the millisecond range offering real-time communication for time-critical applications.

LTE-M is perfect for medium-throughput applications requiring low power, low latency, and/or mobility, like asset tracking, wearables, medical, POS and home security applications.
```

### NB-IoT
```
Low power, range and adaptability for your applications

NB-IoT (also known as Cat-NB1) is a narrowband technology standard that does not use a traditional LTE physical layer but is designed to operate in or around LTE bands and coexist with other LTE devices. It has a bandwidth of 200 kHz, giving it a longer range and lower throughput compared to LTE-M and regular LTE. The throughput is 60 kbps uplink and 30 kbps downlink. It is suitable for static, low-power applications requiring low throughput. With the introduction of Cat-NB2 in 3GPP release 14, you can achieve a throughput of 169 kbps uplink and 127 kbps downlink if the network supports it. 

NB-IoT is perfect for static, low throughput applications requiring low power and long-range, like smart metering, smart agriculture and smart city applications. It also provides better penetration in, for example, cellars and parking garages compared to LTE-M.
```

## Comparisons
```
                                LTE-M                                   NB-IoT
Also known as 	                “eMTC”,”LTE Cat-M1” 	                “LTE Cat-NB1” (3GPP rel 13)
                                                                        "LTE Cat-NB2" (3GPP rel 14)
Max Throughput ( DL/UL )        300/375 kbps    	                    30/60 kbps (NB1) - 127/169 kbps (NB2)
Range                           Up to 4x 	                            Up to 7x
Mobility/cell re-selection 	    Yes 	                                Limited
Frequency deployment 	        LTE In-band 	                        LTE In-band, guard band and GSM re-purposing
Deployment density 	            Up to 50,000 per cell 	                Up to 50,000 per cell
Module size 	                Suitable for wearables 	                Suitable for wearables
Power consumption 	            Up to 10 years of battery lifetime 	    Up to 10 years of battery lifetime
```
