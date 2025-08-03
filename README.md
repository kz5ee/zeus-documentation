# Overview
The goal of this project is to create a scalable, modular weather station

- Core
	- Wind
		- Direction
		- Speed
			- Max 120mph
	- Temperature
		- Range: -40°F - 150°F
	- Humidity
	- Barometric pressure
		- Range: 23 - 31 inHg
	- GPS position
	- Rainfall
		- Rate
			- Units: in/hr
		- Amount
			- Units: in
	- Communication
		- Wifi
		- Bluetooth
		- Service UART port
- Modules
	- Power
		- Interface
			- USB-C for power delivery only
		- Solar
		- Wind
		- Battery
		- Combination solar/wind/battery
	- APRS
		- For reporting weather station telemetry to APRS network
	- LoRA
		- For reporting telemetry within weather station cluster
- User interface
	- Web dashboard
	- Mobile app
	- Desktop app


