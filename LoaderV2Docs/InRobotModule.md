[M4x10 screws]:Parts.yaml#M4x10PanSteel
[No. 2 Phillips screwdriver]:Parts.yaml#Screwdriver_Philips_No2
# In-Robot Module

{{BOM}}

The in-robot module is the combination of actuator, piston head, catch, frame, and dispense valves that physically sits inside your liquid handler - specifically, in slot 10 of an OT-2.


## Assemble the valve box {pagestep}

* 3D Print the [AFL in-robot valve box](ValveBox.md){Qty: 1} and tap the two, 1/4"-20 threaded holes on the side.
* Attach 2 [1/8" x 10-32 push connect fittings]{Qty: 6} to each of the 3 [low-flow solenoid valves]{Qty: 3} and tighten to engage the O-ring on the fitting.
* Insert the assembled valves into the box and thread their wires down through the grooves on the bottom into the "electronics area" on the rear of the box.  It can be helpful to label one wire from each valve (these will be the negative terminal and will all be tied together).  
>i **Note** 
>i These valves do not have a polarity, so you can just arbitrarily pick a negative wire.  The Burkert "whisper valves" used for post-sample and piston vent *do* have polarity, and for those valves the black wire should be used as negative.
* Take the [Burkert valve connector]{Qty: 1} and the [dangling RJ45 jack]{Qty: 1}, and fish the ends through the right side of the box into the connector space.
* Populate the [DB9M/F serial connector] using the new leads according to the following pin diagram.  You can terminate the wires using solder into a solder cup connector, but a screw terminal solution would be better.
    * Connector #1 - Electronics box to loader

    * (BLACK)  #1 RINSE 1
    * (BROWN)  #2 RINSE 2
    * (RED)    #3 BLOWOUT
    * (ORANGE) #4 PISTON VENT
    * (YELLOW) #5 CELL FLOW THRU
    * (GREEN)  #6 COMMON
    * (BLUE)   #7 LIMIT SUPPLY +5V
    * (PURPLE) #8 FULL-UP LIMIT
    * (GRAY)   #9 FULL-DOWN LIMIT

    (WHITE)  SH GROUND
* Secure the connector into place using [UV-set glue or epoxy].  Place the [AFL in-robot valve box cover]{Qty:1} into place.

## Assemble the interlock harness {pagestep}

This is a separate component because there is significant risk of inductive crosstalk between the 24V solenoid/relay lines and these switches which can fry DAQ hardware.  It’s happened, several times.

* 3D print the [robot door switch carrier](RobotDoorSwitchCarrier.md){Qty: 1}; multiple copies can be helpful as this is a fragile part.  
* Glue two strong [neodymium magnets]{Qty: 2} into the positions on the carrier using [UV-set glue or epoxy]{qty:some}.  These magnets hold the switch carrier to the robot frame.
* Screw a [limit switch](parts.yaml#LimitSwitch){Qty:1} to the switch carrier using 2 [#2-56 screws, 1" long]{Qty: 2} and 2 [#2-56 nuts, hex]{Qty: 2}
* Take a [3 ft RJ45 patch cable or equivalent bare CAT5 type cable and termination tools]{Qty: 1} and remove one end using a [wire cutter/stripper]{Qty: 1, Cat: tool}.  Determine the color convention of the cable, which will be TIA568A or TIA568B (see references online).  If it's (TBD), reverse the relevant color here.  Separate the 4 pairs of wires from each other with about a foot of slack on the bare cable, then solder them using a [soldering iron and solder]{Qty: 1, Cat: tool} to the door switch and the other two [limit switch](parts.yaml#LimitSwitch){Qty:2}es as follows.  Be sure to enclose splices and splits in [heatshrink tubing]{Qty:some} to provide abundant strain relief.  If you don't have heat shrink you can use [electrical tape]{optional,Qty:some} but... use heatshrink.
    * Blue / blue-white pair: connect BLUE to the blue wire on the door switch and BLUEWHITE to the black wire on the door switch.  Provide about a foot of extra slack on this pair due to the distance between the loader and the door.
    * Orange / orange-white pair: connect ORANGE to the blue wire on the up switch and ORANGEWHITE to the black wire on the switch
    * Brown / brown-white pair: connect BROWN to the blue wire on the down switch and BROWNWHITE to the black wire on the switch.
    * The final green / green-white pair will not be used.
* It is recommended to test this interlock harness using the continuity mode of a [multimeter]{Qty: 1, Cat: tool} but this is not strictly required... if you believe in yourself.


## Assemble the actuator frame {pagestep}

* 3D print the [AFL Actuator Frame](AFLActuatorFrame.md){Qty: 1}, [Actuator Piston Arm](AFLActuatorPistonArm.md){Qty: 1}, and [Actuator Full-Up Microswitch Arm](AFLActuatorFullUpMicroswitchArm.md){Qty: 1}.  Tap the two #4-40 holes in the microswitch arm using a [4-40 tap]{Qty: 1, Cat: tool} and the two #2-56 holes  each on the arm and frame using a [2-56 tap]{Qty: 1, Cat: tool}.
* Prepare the [pneumatic clamp]{Qty: 1} by removing the two 1/8" NPT plugs from the rear fitting holes using a [SIZE hex key]{Qty: 1, cat: tool}, switching them into the side holes, and installing two [1/8" NPT x 1/4" tube push connectors]{Qty: 2} into the NPT holes.  Use [teflon pipe thread tape]{Qty: some} on connections.
>! *Caution*
>!
>! The orifices inside the actuator are tiny, and bits of PTFE or other debris can become plugged in there.  This can be fatal to the actuator in the worst case, and in the best case results in a very tedious job unjamming the small holes.  Be careful to not put thread tape on the first few turns of the thread that engage to avoid shredding the tape and be vigilant to remove any debris.  Be diligent, too, about threading tape on in the correct direction (in the rotation direction of the fitting)
* Mount the two switches from the interlock harness to the frame (down switch) and arm (up switch) using [#2-56 screws, 1/2" long]{Qty:4} and a [SIZE FOR 256 hex wrench]{Qty: 1, Cat: tool}.  You may need to use [#2-56 nuts, hex]{Qty: 2} on the frame.
* Mount the prepared pneumatic clamp to the back of the actuator frame using 4 [1/4"-20 socket head cap screws, 2" long]{Qty: 4}, [1/4" washers]{Qty: 8}, [1/4"-20 nuts]{Qty: 4}.  Test the fit into the deck slot, you sometimes need [1/4" washers] between the frame and the actuator to increase the gap so that the assembly fits well.
* Mount the full-up microswitch arm with the attached switch to the left side of the frame using 2 [#4-40 screws, 1/2" long]{Qty: 2}.
* Using a [long 3/16" hex head driver]{Qty: 1, Cat:tool} and 2 [1/4"-20 socket head cap screws, 1/2" long]{Qty:2}, mount the assembled valve box to the left side of the frame.  Pay attention to the wire routing.
* Using a [wrench size for 3/8" bolt]{Qty: 1, Cat: tool}, mount the [Actuator Piston Arm] to the actuator.  Be cautious with this mounting.  It needs to be firm, but not so firm you crack the arm.  It should resist a moderate rotational force from the end of the arm without slipping.

## Install the piston and catch into the frame {pagestep}
* Take the [AFL piston](AFLPistonCatch.md){Qty: 1} and [AFL Catch](AFLPistonCatch.md){Qty: 1}.  Start with the catch alone first and rotate the piston arm to the fully-up position. 
* You may find it helpful to make up the fluidic connection on the catch bottom first using [1/16" PP or ETFE tubing]{Qty: some} and [1/4"-28 x 1/16" tube flangeless nuts and ferrules]{Qty: 1}  
>i **Note**
>i If you are using a machined PTFE catch, use great caution to avoid over-torquing the PTFE threads.  It would be prudent to use some [thread locker compound]{Qty: some} on these connections.

* Using two [#8-32 screws, 2" long]{Qty: 2}, two [#8-32 nuts]{Qty: 2}, and the 3D printed [AFL catch nut]{Qty: 1}, install the catch in the frame.  Route the tubing out the right or left side of the catch frame at the rear.
* Now, place the [AFL piston] with its [piston o-ring](AFLPistonCatch.md){Qty: 1} into the catch, and lower the catch arm.
* Pre-thread a [1/4"-20 nut]{Qty: 1} and a [1/4" washer]{Qty: 1} onto a a [1/4"-20 socket head cap screw, 2" long]{Qty: 1}, in the sequence bolt head > nut > washer > threaded end.
* On the arm bottom, loosely hold a [1/4"-20 nut]{Qty: 1} and a [1/4" washer]{Qty: 1}, and run the bolt through the arm and thread into the nut.  The sequence on the bolt should now be bolt head > nut > washer > arm > washer > nut.
* Gently thread the bolt into the top, 1/4"-20 threads on the piston.  See note above regarding PTFE threads.  The bolt should bottom out in the hole.  If space permits (depends on the nuts you use), you might find it useful to use a nut against the piston head to prevent rotation.
* Set the piston height by rotating the nuts above/below the catch arm.  You want the piston to be as deep as possible in the catch (for maximum engagement/compression of its o-ring seal) while still clearing the catch edge as it moves up and out of the catch.  It is best to manually move the catch arm into this intermediate position and set the height using the bolts so that it just clears.
* When the height is adjusted, use [SIZE wrenches]{Qty: 2, cat: tool} to tighten the two bolts against one another around the catch arm.

## Make-up internal plumbing/pneumatic connections. {pagestep}
* Attach three [1/4"-28 inlet check valves]{Qty: 3} to three fluidic ports on the piston.  You may wish to use some [thread locker compound]{Qty: some} to secure these.
* Attach a [Burkert whisper valve, type A]{Qty: 1} to the piston arm using [electrical tape or similar]{Qty: some}, with the ports facing out.
* Using [1/16" PP or ETFE tubing]{Qty: some} and [1/4"-28 x 1/16" tube flangeless nuts and ferrules]{Qty: 2} , make the shortest reasonable connection between one port on the valve and the check valve-free port on the piston head.  This is the piston top vent port, which allows the piston head to close without applying pressure shockwaves to the sample.
* Using [1/8" PP or ETFE tubing]{Qty: some} and [1/4"-28 x 1/8" tube flangeless nuts and ferrules] on the piston end only, attach short lengths (~ 1 ft / 20 cm) of tubing to two of the check valve-equipped ports. 
* One tube will directly connect to the central solenoid valve in the box (the "blowout") valve.  Cut (using a [plastic tube cutter]{Qty: 1, Cat: tool}) the tube to a precise length that allows the arm to rotate without excess slack, then push it into the push connect on the valve.
* The two rinse tubes are combined using a [1/8" push connect tee fitting]{Qty: 1} just after the valve box.  Cut two short 2-3" lengths of tubing and run them from the valve exit into the two co-linear ports of the tee.  Cut the dangling tube from the piston head to appropriate length, then attach to the perpendicular port of the tee.
* The final port goes to the dispense controller.  Run a longer length of [1/8" PP or ETFE tubing], perhaps as long as 1 m, from the piston head.







