# Video-UI Module

The video-UI module is essentially a housing for two Raspberry Pi boards that provide two important support services: a local user interface at the robot (UI), and recording/archival of video streams from on-robot cameras (video).

{{BOM}}

## Prepare the components {pagestep}

* 3D print the [Video-UI module enclosure]{Qty: 1}, [Video-UI module front cover]{Qty: 1}, and [Video-UI top cover]{Qty: 1}.
* Tap the holes: 4, 4-40 holes using a [4-40 tap]{Qty: 1, Cat: tool} on the top and front that secure the cover, and 8, 2-56 holes using a [2-56 tap]{Qty: 1, Cat: tool} on the internal Pi retention threads.

## Prepare the Raspberry Pi boards {pagestep}

* Follow the instructions in the [Pi flashing appendix](PrepareRaspberryPis.md) to prepare two [SD cards (min. 64gb, high endurance)]{Qty: 2} with appropriate hostnames:
  * For the UI Pi: hostname "afl-ui" with standard password
  * For the Video Pi: hostname "afl-video" with standard password

* Install the SD cards into their respective Raspberry Pi boards.

## Assemble the module {pagestep}

* Mount the two [Raspberry Pi boards](Parts.yaml#RaspberryPi){Qty: 2} to the internal Pi retention threads using [2-56 screws](Parts.yaml#256Screw14inSS){Qty: 8}. Position the Video Pi on the left side and the UI Pi on the right side when facing the port section of the enclosure.

* Connect the [Ethernet patch cables (1 ft)]{Qty: 2} to both Pi boards and route them through the side slots in the enclosure.

* Connect the [HDMI cable (1 ft)]{Qty: 1} from the UI Pi to the touchscreen display and secure it through the top cover.

* Connect any additional peripherals needed:
  * [Wireless USB keyboard/mouse dongle]{Qty: 1} to the UI Pi if needed for setup
  * [USB storage device]{Qty: 1} to the Video Pi for extended video storage if required

## Complete the assembly {pagestep}

* Carefully route all cables to avoid pinching when the covers are installed.

* Attach the front cover to the main enclosure using [4-40 screws, 1/4" long](Parts.yaml#440Screw14inSS){Qty: 2}.

* Attach the top cover to the enclosure using [4-40 screws, 1/4" long](Parts.yaml#440Screw14inSS){Qty: 2}.

* Connect the power supplies to both Raspberry Pi boards through the access ports in the enclosure.

## Configure the software {pagestep}

* Power on both Raspberry Pi boards and ensure they boot correctly.

* On the UI Pi:
  * Configure the touchscreen interface to display the control dashboard
  * Set up the connection to the main control system

* On the Video Pi:
  * Configure the video capture software to record from the connected cameras
  * Set up the video storage and archiving system
  * Configure any required network streaming capabilities

## Test the module {pagestep}

* Verify that the UI touchscreen displays the control interface correctly and responds to touch input.

* Test the video capture functionality by connecting a camera to the capture device and ensuring that video is being recorded properly.

* Verify network connectivity between both Pi boards and the main control system.

* Test all user interface controls to ensure they correctly communicate with the rest of the system.
