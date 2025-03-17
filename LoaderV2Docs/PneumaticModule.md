[M4x10 screws]:Parts.yaml#M4x10PanSteel
[No. 2 Phillips screwdriver]:Parts.yaml#Screwdriver_Philips_No2
# Pneumatic Module

{{BOM}}

The role of the pneumatic module is multi-fold: 

*   provide switched, high pressure (60-80 psig) nitrogen/air to the loader actuator in the robot
*	provide a series of streams of reduced pressure nitrogen to dispensing components: (15-20 psig to dispense bottles, 15-30 psig to electronic dispense regulator), including safety features like pressure relief valves
*	(in revision 2 and greater) house the electronic dispense regulator

It is worth noting that a number of configuration changes can be made in the pneumatic module to adapt the robot to locally available utilities; for instance, sometimes facilities have high-pressure filtered clean dry air available but nitrogen is only available at lower pressure.  In this case one can supply the actuator with air and the dispense system with nitrogen.

Materials:
	[AFL Pneumatic System Frame]{Qty: 1}
	[FiveWayValve]{Qty: 1}
	[AirRegulator]{Qty: 2}
	[PushConnector14NPTto14Tube]{Qty: 8}
	[PushConnector14NPTto18Tube]{Qty: 4}
	[PushConnectTee14]{Qty: 2}
	[NylonTube14OD]{Qty: 1, Unit: ft, Qty_Value: 10}
	[ETFETube18OD]{Qty: 1, Unit: ft, Qty_Value: 5}
	[M4x10 screws]{Qty: 8}
	[No. 2 Phillips screwdriver]{Qty: 1, Cat: tool}
	[RJ45 jack]{Qty: 1}

## Assemble the frame and main components {pagestep}

* 3D print the [AFL Pneumatic System Frame]{Qty: 1} if not already available.

* Mount the [FiveWayValve]{Qty: 1} to the designated position on the frame using [M4x10 screws]{Qty: 4} and a [No. 2 Phillips screwdriver]{Qty: 1, Cat: tool}. The valve should be oriented with the main port facing the input side of the frame.

* Install the two [AirRegulator]{Qty: 2} units to their designated positions on the frame using [M4x10 screws]{Qty: 4}. One regulator will be used for the actuator pressure (60-80 psig) and the other for the dispensing pressure (15-30 psig).

* Label each regulator clearly with its intended pressure range to avoid confusion during operation.

## Install pneumatic connections {pagestep}

* Install [PushConnector14NPTto14Tube]{Qty: 8} fittings to the appropriate ports on the valve and regulators. Ensure all connections are tight to prevent leaks.

* Install [PushConnector14NPTto18Tube]{Qty: 4} fittings to the ports that will connect to the smaller tubing used for dispensing.

* Connect the main air/nitrogen input to the first regulator using [NylonTube14OD]{Qty: 1, Unit: ft, Qty_Value: 2}.

* Using [PushConnectTee14]{Qty: 1}, split the output from the first regulator to feed both the five-way valve and the second regulator.

* Connect the output from the five-way valve to the port that will lead to the actuator in the robot using [NylonTube14OD]{Qty: 1, Unit: ft, Qty_Value: 3}.

* Connect the output from the second regulator to the [PushConnectTee14]{Qty: 1} that will split the flow to the dispensing components using [NylonTube14OD]{Qty: 1, Unit: ft, Qty_Value: 2}.

* Run [ETFETube18OD]{Qty: 1, Unit: ft, Qty_Value: 5} from the appropriate push connectors to where they will connect to the dispensing components.

## Install electrical connections {pagestep}

* Mount the [RJ45 jack]{Qty: 1} to the designated position on the frame. This will be used to connect the pneumatic module to the electronics module.

* Wire the RJ45 jack to the control inputs of the five-way valve according to the wiring diagram (to be provided separately).

## Test the pneumatic system {pagestep}

* Before connecting to the robot, test the pneumatic system for leaks by applying pressure and using soapy water to check all connections.

* Verify that the regulators can be adjusted to the required pressure ranges:
  * Actuator regulator: 60-80 psig
  * Dispensing regulator: 15-30 psig

* Test the operation of the five-way valve by applying control signals through the RJ45 connection.

* Ensure that all safety features, including pressure relief valves, are functioning correctly.

## Connect to the robot system {pagestep}

* Once testing is complete, the pneumatic module is ready to be connected to the robot system.

* Connect the actuator line to the in-robot module using the appropriate tubing and connectors.

* Connect the dispensing lines to their respective components.

* Connect the RJ45 cable from the pneumatic module to the electronics module to enable control of the pneumatic system.