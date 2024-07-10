# OT-2 hardware modifications

{{BOM}}


Perhaps surprisingly, you only need to make two modifications to a standard [OT-2 robot](OT-2Robot.md){Qty: 1}:

## Drill/tap mounting holes in removable OT-2 deck plate {pagestep}
* Remove the robot deck using the 2 screws on left and right side and a [3 mm hex key]{Qty:1 , Cat:tool}
*  drill and tap (using a [drill]{Qty:1, Cat:tool}, [#7 - 13/64" - 0.2010" drill bit]{Qty:1, Cat:tool}, and [1/4"-20 tap and handle]{Qty:1, Cat: tool}) two ¼—20 holes into the deck in slot 10 (top left) as hold down points for the loader. 

 It’s worth noting that this doesn’t make the slot unusable should you wish to remove the loader later.
To-do: add dimensions from rails.  Can read these for now from the loader frame drawing.
## Drill and tap two ¼”-20 mounting holes on the left side of the robot for the frame. {pagestep}

>! This is a little nerve wracking because 
>!
>!(a) you can’t just remove the part and do the drilling on a mill/drill press, it has to be done on the robot with a hand drill, and 
>!
>!(b) there are some relatively important wires in the areas you drill into, specifically the main robot power harness on the left side and the door interlock switch on the right.  
>!
>! BE GENTLE, you only need a few turns’ worth of depth, perhaps 1/8”.  
>!
>! If you go all the way through you should open the frame rails up and inspect the wiring harnesses for any signs of damage.  It would be safest to totally disassemble the robot side and remove the wiring but I haven’t done this previously.  
>!
>! Note that this is all low voltage wiring (36V for robot power, 3.3V or 5V for interlock) so there are no serious electrical safety concerns, but disconnect power first and if the drilled hole entered the wiring space, disassemble, inspect, and repair if needed before energizing the robot.


## build the left mounting frame {pagestep}


The frame rails are 1” square 80/20 style T slot extrusion in lengths given above.

*  Tap using a [1/4"-20 tap and handle]{Qty:1, Cat: tool}) the upper central holes of 4, [24" long 1" t-slot aluminum extrusion]{Qty: 4}. 
*  Using 2 [22" long 1" t-slot aluminum extrusion]{Qty: 2} and 4 [4" long 1" t-slot aluminum extrusion]{Qty: 4}, build a 24” high x 6” deep x 24” wide “U” frame using [1" t-slot single L brackets]{qty:12} 
*  Take the [26" x 6" x 3/16" Aluminum plate] and drill 4 clearance holes 1/2" in from each corner. (using a [drill]{Qty:1, Cat:tool}, [#H - 0.2660" drill bit]{Qty:1, Cat:tool}) 
*  Fasten the aluminum top plate across the top to make a box using 4 [1/4"-20 pan head screws, stainless, 1/4" long]{qty:4}.
*  Insert the final pair of [22" long 1" t-slot aluminum extrusion]{Qty: 2} with the base about 8” above the bottom.  

These rails will hold your modules, the bottom area will store wiring, and the top shelf is for cameras and any instrument specific devices.


* Mount the frame to the holes you drilled in the side of the OT2 using 2 [1" t-slot single L brackets]{qty:2}.  It should be secure.  Do not obstruct the robot network, power, and power switch connectors at the rear; adjust rail spacing if necessary.

* If you are using the optional traveling setup, cut out foam from the case bottom and rest the OT2 in the case and assemble the frame to fit in the case now.  This is also a good time to mount an AirTag or similar to the frame.
* You have a frame!  It may seem wobbly right now and that’s OK.  Each module will provide stiffness and reinforcement for the other modules.  Think of how the cardboard back holds an IKEA bookcase together.
* It can be wise to order and keep around some extra T-slot rail for sample environments, etc.  It’s useful stuff to have!
* At this stage, I also suggest installing the “dumb” accessories on the rail, those being two [AFL bottle holder](AFLbottleholder.md){qty:2} and a [AFL network switch holder](AFLswitchholder.md){qty:1}.  Bottle holders go all the way to the left, and network switch holder on the right.
