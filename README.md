# FGFS DRIVER FOR SAITEK SWITCH PANEL

This project provides an interface between Flightgear Flight Simulator and the Homeassistant. Operation of switch(es) on homeasistant is reflected in the simulator. 


This software loads configuration which maps the MQTT topics to the **FSFG** simulator properties. 
and are for:


This project is the successor to daibach142/FGFS_Saitek_Switch_Panel on GitHub.
For problems or issues either enter an issue on Github, https://github.com/zipperten/homeassistant-fgfs

---

## INSTALLATION

### General

1. Download and expand the software from [here](https://github.com/zipperten/homeassistant-fgfs). 

 
1. Copy `saitekswitch.nas` to a the Nasal folder in fgroot.
2. Import `ha-fgfs_noderedflow.json` to nodered.
3. Klick the blue Auto-discovery node to generate the mqtt properies.
4. Add the generated entities to a HomeAssistant panel, you can have a look at hadashboard.yaml
5. Start fgfs with 'fgfs --generic=socket,in,20,0.0.0.0,60000,udp' or add --generic=socket,in,20,0.0.0.0,60000,udp in the launcher settings. 
6. Try the brakers, and keep the blue side up!.

 
---

### Note

Its an early project, im glad to have some sugestions or help improve the code. 
---

## RUNNING

Note that the Switch Panel software is configured at startup for a
specific aircraft using a configuration file. Files for the Cessna 172P and Piper 28-116 are currently provided, see `CONFIGURATION` for roll-your-own.

Start fgfs with 'fgfs --generic=socket,in,20,0.0.0.0,60000,udp' or add the following start option to FlightGear configuration:

	...
	--generic=socket,in,20,,60000,udp,saitekswitch
	...

Try the switches, and keep the blue side up!.  
---
  








---
Have a look at thsis later, I do not know if this is relevant with mqtt switches.  
### SWITCH elements

There are 13 **`switch`** elements, edit each one to configure the Panel switch to the aircraft configuraation, possibly using the 'properties' window in the simulator. A switch toggles the specified property by sending 1 (on) or 0 (off); this works for FGFS bool, integral or double-precision values. Note that the current switch state is maintained within this driver software, and is not read from the simulator. It is **`MANDATORY`** to provide all 13 elements.

---

