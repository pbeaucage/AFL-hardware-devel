[M4x10 screws]:Parts.yaml#M4x10PanSteel
[No. 2 Phillips screwdriver]:Parts.yaml#Screwdriver_Philips_No2
# Pneumatic Module

{{BOM}}

The role of the pneumatic module is multi-fold: 

* provide switched, high pressure (60-80 psig) nitrogen/air to the loader actuator in the robot
*	provide a series of streams of reduced pressure nitrogen to dispensing components: (15-20 psig to dispense bottles, 15-30 psig to electronic dispense regulator), including safety features like pressure relief valves
*	(in revision 2 and greater) house the electronic dispense regulator

It is worth noting that a number of configuration changes can be made in the pneumatic module to adapt the robot to locally available utilities; for instance, sometimes facilities have high-pressure filtered clean dry air available but nitrogen is only available at lower pressure.  In this case one can supply the actuator with air and the dispense system with nitrogen.

Materials:
	AFL Pneumatic System Frame x 1
	Two-position control valve
	Compact regulator x 2
	Fittings to be enumerated
		RJ45 jack

## Assemble the frame and main components {pagestep}