# detach75-keyboard
A 75% mechanical keyboard created for my high school PLTW capstone course. On top of being a standard mechanical keyboard, there is an integrated USB 2.0 hub with a second USB data line exposed internally. This allowed a 2.4 GHz USB receiver to be soldered on and connect to a wireless number pad for expanded functionality. 

![image](https://github.com/user-attachments/assets/df199378-6ae8-4e77-bdb6-552ef614c171)

## PCB
The design and layout of the PCB would not have been possible without this [series of articles](https://www.masterzen.fr/tag/#pcb) from Masterzen. Following his process, I adapted the matrix from a 60% layout to a 75% layout and integrated the USB 2.0 hub IC onto the USB D+/- lines. The PCB is relatively basic, being only two layers and missing several elements such as ground pours. The manufactured version of the PCB had two incorrectly placed capacitors that prevented the MCU from staying on and had to be removed; the included CAD files have been corrected. 

![image](https://github.com/user-attachments/assets/f72d0fd0-c486-4dc8-9af6-4a2bd43beb79)

## Firmware
The keyboard uses the widely popular QMK firmware. QMK is the firmware of choice among keyboard enthusiasts as it is easily customizable with a rich set of features. Included is the configuration for the PCB's switch matrix as well as a basic setup of modifier keys.

To flash the PCB's MCU, first set up QMK following their guide [here](https://docs.qmk.fm/newbs_getting_started). Then, copy the contents of the Firmware directory into the QMK keyboard directory. Compile the firmware with `qmk compile -kb detach/75 -km default` and flash using QMK's [flashing guide](https://docs.qmk.fm/newbs_flashing). Use the reset push button on the underside of the PCB to initiate the ATmega bootloader; the MCU can be flashed via the USB-C port.
