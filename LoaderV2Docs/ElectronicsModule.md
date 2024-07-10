[M4x10 screws]:Parts.yaml#M4x10PanSteel
[No. 2 Phillips screwdriver]:Parts.yaml#Screwdriver_Philips_No2
# Electronics Module

{{BOM}}


The role of the electronics module is to provide control over the loader system.  Specifically, it has at least 7 channels of 24V relays for solenoid valves, 3 digital inputs for interlocks (arm up / arm down / door closed), and can be used to drive a pressure controller, though we typically do that via a LabJack.
An alternative electronics module is entirely built around a LabJack using their relay module.  These are much higher cost, but avoid needing a separate computer/Raspberry Pi and network backend.

Materials:
	1 x AFL electronics module enclosure 
1 x front cover
1 x top plate cover
	3 x RJ45 jack 
		Switch: McMaster-Carr # 7395K29 or equivalent
		DB9 female connector, panel mount
		DC connector, 2.1 mm, McMaster # 8320N115 or equivalent
		24 V, 1 A, 2.1 mm, center - AC/DC adapter McMaster 70235K85 or equivalent
		Hookup wire
		Raspberry Pi
		64GB high endurance SD card
		PiPLATES RelayPLATE
		PiPLATES PowerPLATE24
		Short (1 ft) RJ45 patch cable or bare CAT5e cable and termination tools		
		4 x  #2-56 x ¼” screws (length need not be exact)
 
## Prepare the Housing {pagestep}
* 3D print the [AFL Electronics Module]{Qty: 1}, [AFL Electronics Module Cover]{Qty: 1}, and [AFL Electronics Module Top Cover]{Qty: 1} and tap the 4 cover mounting holes using a [#4-40 tap]{Qty: 1, Cat: tool}, and the 4 Raspberry Pi mounting holes using a [#2-56 tap]{Qty: 1, Cat: tool}.		
## Prepare the Raspberry Pi and other boards {pagestep}
The base of the electronics stack is a [Raspberry Pi]{Qty: 1}.  

* Follow the instructions in the [Pi flashing appendix](PrepareRaspberryPis.md) to prepare a [SD card (min. 64gb, high endurance)]{Qty:1} with hostname “piloader” and password.  Install that MicroSD card into the Pi.

* At this point it’s prudent to make any future connections needed to the Pi as getting to the connectors and SD card slot will be much more painful later!  In particular, attach a network cable ([1-3 ft CAT5e patch cable]{Qty: 1}) and any USB devices you might want, plus video if you want it.  Run these wires up and out the top hole of the enclosure.

* Install the Pi into the four #2-56 tapped holes in the bottom of the electronics board using [#2-56 screws, 1/4" long]{Qty: 4}.

* Align the 40 pin header of the [Pi-Plates PowerPLATE24]{Qty:1} to the Raspberry Pi and press down firmly to seat.

* Align the 40 pin header of the [Pi-Plates RelayPLATE]{Qty: 1} to the Raspberry Pi and press down firmly to seat.


## Prepare the housing and components {pagestep}


* Populate the connector positions with:
    * top side: main enable [switch]{Qty: 1}
    * side: [DB9 female connector, panel mount]{Qty: 1} to connect to valves/in-robot module
    * side: [DC connector, 2.1 mm]{Qty: 1} for power input
    * leave the two RJ45 connector positions unpopulated for now.  We will make up connections to those later.



* Attach the front and top covers using [#4-40 screws, 1/4" long]{Qty: 4}