The liquid-handling core of an AFL is an Opentrons OT-2 liquid handler.

This is a commercial product that a lot of labs tend to have around; its original value proposition when it launched was acceptable liquid handling with great, open software at an incredibly low price ~ $3,000 - $5,000.  It is essentially a 3D printer gantry, some (in our opinion quite cheaply built) pipettes, a SmoothieBoard, and a Raspberry Pi that ties the platform together.  Their software is rather fast to get started with, but leaves a few things to be desired in on-the-fly concurrency and handling viscous/complex liquids which is why we supplement it with AFL-automation.prepare.OT2Driver.

The prices have crept up - over $10,000 at last update 05/2024 - and the features have remained about the same.  The newest version -  Opentrons Flex "OT-3" - is no longer priced for tinkering at ~$30,000 and does not seem to offer meaningful improvement in core liquid handling for that price.  One could probably get an AFL working with a Flex, but at that price point I would really recommend something more like a Hamilton or other high end liquid handler.  These machines purport to deliver substantially improved performance (capacitive liquid sensing, for one) at about the same price as a Flex, albeit with almost no support for non-manufacturer-provided workflows.  (But then, does Opentrons provide that?)

Some labs are exploring the Jubilee liquid handling robot, a fully open, home built platform that supports liquid handling among other applications.  Jubilee comes from the lab of Prof. Nadya Peek at the University of Washington and while building it is not for the faint of heart, the performance is promising and the mechanical engineering world-class.

If you are buying an OT-2 for an AFL, our suggestion is to get it with a P1000 GEN2 and P300 GEN2.  You could make do with just the P1000 or just the P300 depending on your target sample size and deck load out.

