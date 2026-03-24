# Home Assistant FGFS Integration (Virtual Switch Panel)  

This project provides an interface between FlightGear Flight Simulator and Home Assistant. It allows you to control simulator switches directly from Home Assistant using MQTT Auto Discovery, without the need for physical Saitek hardware.

This setup utilizes the logic from the FGFS_Saitek_Switch_Panel archive to emulate a professional switch panel within your smart home ecosystem.

For problems or issues, please enter an issue on GitHub: https://github.com/zipperten/homeassistant-fgfs

---

## INSTALLATION

### Linux

I have only got this working with the apt version, the appimage version do not seam to fin my saitekswitch.xml file 

1. Download and install the saitek software from [here](https://github.com/daibach142/FGFS_Saitek_Switch_Panel). 
2. Import `ha-fgfs_noderedflow.json` into Node-RED.
3. Setup your ip and security for your mqtt broker in the mqtt node
5. Setup ip for your fgfs machine in the "UDP To FlightGear" node
6. Deploy, green connected icons should appear under mqtt nodes
7. Click the blue Auto-discovery node in the node red flow to generate the MQTT entities in homeassistant.
8. Create a homeassistantpanel with the generated entities, you can add the premade if you want.  `hadashboard.yaml`.


 
---

### Note

It's an early project, I'm glad to receive suggestions or help to improve the code. 

---

## RUNNING


Start FGFS with `fgfs --generic=socket,in,20,,60000,udp,saitekswitch` or add the following start option to FlightGear configuration:

	...
	--generic=socket,in,20,,60000,udp,saitekswitch
	...

---



### SWITCH elements

I Have a look at this later, I do not know if this is relevant with MQTT switches.  

There are 13 **`switch`** elements, edit each one to configure the panel switch to the aircraft configuration, possibly using the 'properties' window in the simulator. A switch toggles the specified property by sending 1 (on) or 0 (off); this works for FGFS bool, integral or double-precision values. Note that the current switch state is maintained within this driver software, and is not read from the simulator. It is **`MANDATORY`** to provide all 13 elements.


You can modify what switched you want by editing the XML File node in node-red. 
---
