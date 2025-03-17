# Preparing Raspberry Pi SD Cards

{{BOM}}

This guide provides instructions for preparing Raspberry Pi SD cards for use in the various modules of the autonomous formulation platform. Different modules require different Pi configurations, but the basic flashing process is the same.

## Materials needed {pagestep}

* [Raspberry Pi 4B (4GB or 8GB RAM)]{Qty: 1, Cat: electronics}
* [MicroSD card (min. 64GB, high endurance)]{Qty: 1}
* [SD card reader/writer]{Qty: 1, Cat: tool}
* [Computer with internet connection]{Qty: 1, Cat: tool}
* [Raspberry Pi Imager software]{Qty: 1, Cat: software}

## Download and install the Raspberry Pi Imager {pagestep}

* Download the Raspberry Pi Imager from the [official Raspberry Pi website](https://www.raspberrypi.org/software/).
* Install the software on your computer following the standard installation process for your operating system (Windows, macOS, or Linux).

## Prepare the SD card {pagestep}

* Insert the MicroSD card into your computer's SD card reader.
* Launch the Raspberry Pi Imager software.
* Click on "CHOOSE OS" and select "Raspberry Pi OS (32-bit)" from the list. This is the standard Raspberry Pi operating system based on Debian.
* Click on "CHOOSE STORAGE" and select your MicroSD card from the list. Make sure you select the correct device to avoid overwriting data on other drives.

## Configure OS settings before writing {pagestep}

* Before clicking "WRITE", click on the gear icon (⚙️) to access advanced options.
* Configure the following settings:
  * Check "Set hostname" and enter the appropriate hostname based on the module:
    * For the loader electronics module: `afl-loader`
    * For the UI module: `afl-ui`
    * For the video module: `afl-video`
  * Check "Enable SSH" and select "Use password authentication"
  * Check "Set username and password"
    * Username: `pi`
    * Password: `[standard password]` (use your organization's standard password)
  * Check "Set locale settings"
    * Time zone: `[your time zone]`
    * Keyboard layout: `[your keyboard layout]`
  * Click "SAVE" to apply these settings.

## Write the image to the SD card {pagestep}

* Click "WRITE" to begin the process of writing the image to the SD card.
* Confirm the operation when prompted. The software will format the SD card and write the Raspberry Pi OS image to it.
* This process may take several minutes depending on the speed of your SD card and computer.
* Once the writing process is complete, the software will verify the written data to ensure integrity.

## First boot and configuration {pagestep}

* Remove the SD card from your computer and insert it into the Raspberry Pi.
* We manage the software on each Pi using Ansible.  No connection to a monitor or keyboard is required, but you must be on a network with the Pi that supports mDNS so that you can reach the pi using ssh as `pi@[hostname].local`.  
  * If this does not work, you will need to use a tool like `nmap` to find the Pi's IP address and manually create a host entry in your `/etc/hosts` file.

* Once the Pi has booted, you can connect to it using ssh as `pi@[hostname].local` with the password you set during the configuration process.
* You can now use Ansible to manage the software on the Pi.  Ansible is a configuration management tool that allows you to manage the software on the Pi from a remote computer, keeping it up to date and centralizing its management.  The below instructions are retained for reference but are not strictly needed if Ansible deployment is used.
* To run Ansible commands, you will need to have the `ansible` command installed on the computer you are using as the AFL controller.  You can install it using `pip3 install ansible`.
* See full instructions, playbooks, etc. in the `AFL-automation` repo, deploy directory.
* To provision a pi, you will need to add it to the `inventory` file in the `AFL-automation` repo, and run the `afl-pis.yaml` playbook.

## Module-specific configurations {pagestep}

### For the Loader Electronics Module (`piloader`)

* Install the required libraries for the PiPLATES modules:
  ```bash
  sudo apt update
  sudo apt install -y python3-pip
  sudo pip3 install pi-plates
  ```


### For the Video Module (`pivideo`)

* Install the Motion software stack for video capture:
  ```bash
  sudo apt update
  sudo apt install -y motion
  ```

* Set up the Motion configuration to connect to one or more USB cameras and/or RTSP network cameras (we like Amcrest cameras due to their simple UI.  Note it is a very bad idea to connect such cheap cameras to the Internet.)

## Troubleshooting {pagestep}

* If the Raspberry Pi doesn't boot:
  * Check that the SD card is properly inserted
  * Try re-flashing the SD card
  * Verify that the power supply provides sufficient current (at least 3A for Raspberry Pi 4)

* If the Raspberry Pi boots but network connectivity fails:
  * Check your network settings
  * Verify that the Wi-Fi credentials are correct
  * Try connecting via Ethernet cable

* If the module-specific software doesn't start:
  * Check the logs: `sudo journalctl -xe`
  * Verify that all required libraries are installed
  * Check file permissions on the startup scripts
