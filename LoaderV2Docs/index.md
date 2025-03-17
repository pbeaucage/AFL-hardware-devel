# Autonomous Formulation Lab (AFL) Platform

## Overview

The Autonomous Formulation Lab (AFL) is a modular hardware system designed to be the make complex liquid formulations on-the-fly and transfer them pneumatically to one or more measurement instruments.  It is the physical world "body" of the AFL-agent codebase, which seeks to provide orders-of-magnitude acceleration in mapping complex soft matter phase diagrams. It is built around a pipetting robot, presently only Opentrons OT-2 robots are supported (but Jubilee support is in development), but the pneumatic sample transfer system is custom, open hardware.  This manual describes the construction of a complete AFL platform

>!! A forward: these instructions assume some basic "scientific handyperson" skills: use of hand and power tools such as drills and screwdrivers, basic soldering, etc. These tasks have different hazard profiles than many scientific/experimental activities, but are hazardous nonetheless, in fact far more people lose eyesight due to chips from drilling than from laboratory chemical spills. Be vigilant and get help if you don't know how to do something safely, follow your institution's rules, and stay safe.

## System Architecture

The AFL platform consists of several modular components that work together:

1. **OT-2 Robot**: Commercial Off-The-Shelf Pipetting, the heart of the system.
2. **In-Robot Module**: Components installed inside the OT-2 robot, including the catch mechanism, piston, and valve box.

The remaining modules are typically installed in a "side rack" of 80/20 rail bolted to the OT-2 frame:
3. **Pneumatic Module**: Controls air pressure for fluid dispensing and actuator movement.
4. **Electronics Module**: Houses the main control system, including Raspberry Pi and interface boards.
5. **Video-UI Module**: Provides video capture/recording and user interface capabilities.
6. **Rinse Bottles**: One or two bottles of rinse solvent for automated cell washing/reset.

## Build Options

The AFL system can be built in different configurations with different supoprt hardware depending on your specific needs:

1. **Pneumatic Controller** can be either a Nordson EFD Ultimus regulator, or a McMaster-Carr regulator (which requires a 0-10 V digital out on the system).  We suggest the McMaster-Carr option if you are comfortable with custom electronics

2. **Relay Control** can be done with one of: 
a. a Pi-Plates RELAYplate attached to a Raspberry Pi, powered by a Pi-Plates POWERplate2.  (Collectively, the "classic electronics module")
b. a LabJack RB12 connected to a LabJack T4 device.  Slightly more robust control, but a separate device, more components, substantially higher cost.
c. a generic USB relay board from Amazon.  Performance of this alternative is not well tested.


## Manufacturing Methods

The AFL is designed to be as commercial as possible, but several components need to be custom made.  In particular, most housings and nearly all of the in-robot module components are custom printed for space management.
1. **3D Printing**: Most parts can be 3D printed using SLA (resin) or FDM (filament) printers.
   - Critical components requiring high strength: SLA in Rigid10k or similar high-precision resin
   - Fluidic components: SLA in any resin with good chemical compatibility, or machined (see below).
   - Enclosures and other components: PLA/ABS FDM or any SLA material

2. **Machining**: The in-robot piston and catch can be machined from PTFE or 316SS for enhanced durability and chemical resistance.


## Main Assembly Steps

These instructions are structured in rough chronological order, but pages separate subsystems so you can somewhat mix/match things:

* [OT-2 Hardware Modifications](OT-2HardwareModifications.md){step}
* [Pneumatic Module Assembly](PneumaticModule.md){step}
* [Electronics Module Assembly](ElectronicsModule.md){step}
* [In-Robot Module Assembly](InRobotModule.md){step}
* [Video-UI Module Assembly](VideoUIModule.md){step}
* [Final Assembly and Commissioning](FinalAssembly.md){step}

## Instrument Interfaces
* [UV-vis: a simpler example](UVvisCell.md){step}
* [SANS flow-through "Ti cell"](SANScell.md){step}
* [SAXS capillary](SAXScell.md)

## Software Ecosystem
* [Software Overview](software.md)
* [Useful "Meta-Tools": andon and watchdog](metatools.md)

## Appendices and Reference

* [Preparing Raspberry Pi SD Cards](PrepareRaspberryPis.md)
* [Complete Parts List](Parts.yaml)
* [Bill of Materials]{BOM}